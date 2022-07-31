---
title: Leetcode Diary - Range Addition
date: 2022-07-26 13:45:27
tags:
  - leetcode
  - interview
---

# Range addition

Range addition is a common algo pattern. The problem statement will be along the line that:

> Given an array, add i1 to all values from index s1 to e1, add i2 to all values from index s2 to e2.

There is a template we can use to solve it. It requires two steps:

1. Marking the position of start and end of the addition
2. Computing a cumulative sum

## [Leetcode 370](https://leetcode.com/problems/range-addition/)

You are given an integer length and an array updates where updates[i] = [startIdxi, endIdxi, inci].

You have an array arr of length length with all zeros, and you have some operation to apply on arr. In the ith operation, you should increment all the elements arr[startIdxi], arr[startIdxi + 1], ..., arr[endIdxi] by inci.

```
Input: length = 5, updates = [[1,3,2],[2,4,3],[0,2,-2]]
Output: [-2,0,3,5,3]
```

- mark increments

  ```python
  def mark_inc(updates, length):
      # create array of all zeros as stated in the question
      # note we created one additional space to accomodate end index
      arr = [0] * (length + 1)

      for update in updates:
        # extract parameter
        start_index = udpate[0]
        end_index   = update[1]
        inc         = update[2]

        # mark increment at start and end index
        arr[start_index] += inc
        arr[end + 1]     -= inc

      return arr
  ```

- cumulative sum:

  ```python
  def calc_cumsum(inc):
    n = len(inc)
    cumsum = list(inc)
    for i in range(1,n):
      cumsum[i] += cumsum[i-1]
    return cumsum
  ```

- combining together

  ```python
  def range_sum(updates, length):
    inc = market_inc(updates, length)
    cumsum = calc_cumsum(inc)
    return cumsum
  ```
