---
title: Use memoise to speed up your R plumber API
date: 2018-12-05 22:26:41
tags: R
---

`plumber` is a new R package for building web API in R and exposing your R functions to other applications. You can learn more about `plumber` from their [official documentation](https://www.rplumber.io/).

If a function is called multiple times with the same input, you can often speed things up by keeping a cache of known answers that it can retrieve. This is called [memoisation](http://en.wikipedia.org/wiki/Memoization). The `memoise` package provides a simple syntax for caching.

Because API calls are often repeated, performance of `plumber` can be greatly improved by caching its result. Here's a simple example:


##### API Script

`add_api.R`

```r
library(memoise)


# Define function ---------------------------------------------------------
add <- function(a, b) {
  # Wait 1 second
  Sys.sleep(1)
  
  return(a + b)
}

# Memoisize function ------------------------------------------------------
add_mem <- memoise(add)


# Define API --------------------------------------------------------------
#* Return the sum of two numbers
#* @param a The first number to add
#* @param b The second number to add
#* @get /add
function(a, b){
  add(as.numeric(a), as.numeric(b))
}

#* Return the sum of two numbers, use memoise cached results when applicable
#* @param a The first number to add
#* @param b The second number to add
#* @get /addWithMemoise
function(a, b){
  add_mem(as.numeric(a), as.numeric(b))
}
```

##### Start API server
```r
plumber::plumb(file = "add_api.R")$run(port=50000)
```

##### Speed comparison

We can use the following script to test the speed difference of with and without memoise.

```r
# With memoise
for (i in 1:5) {
  cat(
    paste0("Time elapsed in request #", i, " with memoise:"),
    httr::GET("http://localhost:50000/addWithMemoise?a=1&b=1")$times["total"],
    "\n"
  )
}

# Without memoise
for (i in 1:5) {
  cat(
    paste0("Time elapsed in request #", i, " without memoise:"),
    httr::GET("http://localhost:50000/add?a=1&b=1")$times["total"],
    "\n"
  )
}
```

##### Output

As shown below, when using the API call that's using memoise, only in the first time Sys.sleep takes effect. All other runs go straight to retrieve the cached result, and hence result in the 1 second time difference.

The API call without memoise waited 1 second for all the requests before returning the result.

```sh
Time elapsed in request #1 with memoise: 1.012968 
Time elapsed in request #2 with memoise: 0.069301 
Time elapsed in request #3 with memoise: 0.004383 
Time elapsed in request #4 with memoise: 0.00457 
Time elapsed in request #5 with memoise: 0.013691 

Time elapsed in request #1 without memoise: 1.024764 
Time elapsed in request #2 without memoise: 1.04967 
Time elapsed in request #3 without memoise: 1.019524 
Time elapsed in request #4 without memoise: 1.008734 
Time elapsed in request #5 without memoise: 1.011595 
```
