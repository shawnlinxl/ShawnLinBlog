---
title: Leetcode Diary: Arrays
date: 2022-06-29 10:51:10
tags: leetcode
---

# Leetcode Patterns

## Arrays

### Missing Numbers, Duplicated Numbers

Strategies:

- sort
- hashtable
- inplace marking (negative number)
- binary search
- math

**[217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)**

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

```
Input: nums = [1,2,3,1]
Output: true
```

- brute force: two loops, j > i
- sort, then compare element-wise. Time O(nlogn), Space O(1)
- hashtable, loop through elements and add to set. Check if element is already in the set. Time O(n), Space O(n).

**[268. Missing Number](https://leetcode.com/problems/missing-number/)**:

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

```
Input: nums = [3,0,1]
Output: 2
```

- brute force: for each possible value, loop through the array. Time O(n^2), Space O(1)
- sort, and compare if idx == nums[idx]. Time O(nlogn), Space O(1)
- convert array to hashtable, then loop through all possible values to see which is missing from set. Time O(n), Space O(n)
- math: sum of possible values - sum of array values. Time O(n), Space O(1)

**[448. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/)**

Given an array nums of n integers where nums[i] is in the range [1, n], return an array of all the integers in the range [1, n] that do not appear in nums.

```
Input: nums = [4,3,2,7,8,2,3,1]
Output: [5,6]
```

- brute force: for each possible value in 1 to n, loop through the array. Time O(n^2), Space O(1)
- create hashtable, then loop through all possible values to see which is missing from set. Time O(n), Space O(n)
- similar to hashtable, but edit inplace: because the expected values are 1 to n for an array of n elements, we can treat the values as indices:

  - for each value in nums, mark nums[value-1] = -nums[value-1]
  - if value is already negative, don't change it
  - loop through and note the indices still with positive values, these indices are the missing values

  Time O(n), Space O(1)

**[136. Single Number](https://leetcode.com/problems/single-number/)**

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

```
Input: nums = [2,2,1]
Output: 1
```

- hashtable: use dict to represent value:count. Find element with count == 1. Time O(n), Space O(n)
- sort, then compare with left and right elements. If both are not equal, then this element only appeared once. Time O(nlogn), Space O(1)
- math: 2 \* set(nums) - nums. Time O(n), Space O(1)

**[287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)**

Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one repeated number in nums, return this repeated number. The number can be repeated multiple times.

You must solve the problem without modifying the array nums and uses only constant extra space.

```
Input: nums = [1,3,4,2,2]
Output: 2
```

- sort, then compare to nums[i] and nums[i+1] to check for equal. Time O(nlogn), Space O(1). Violates no modification precondition.
- add to hashtable as we loop through, and check whether number is already in hashtable. Time O(n), Space O(n). Violates constant space precondition.
- inplace operation to use position as hashtable: flip nums[value] negative if it is positive. If nums[value] is already negative then we know it's duplicated. Time O(n), Space O(n). Violates no modification precondition.
- binary search: use this [template](https://leetcode.com/discuss/general-discussion/786126/python-powerful-ultimate-binary-search-template-solved-many-problems)

  ```python
  def binary_search(array) -> int:
    def condition(value) -> bool:
        pass

    left, right = min(search_space), max(search_space) # could be [0, n], [1, n] etc. Depends on problem
    while left < right:
        mid = left + (right - left) // 2
        if condition(mid):
            right = mid
        else:
            left = mid + 1
    return left
  ```

  The condition here is the duplicate is less than or equal to x. We can check this by checking if in the array, there are more than x numbers that are less than or equal to x. Time complexity O(nlogn), space complexity O(1)

- Floyd's Tortoise and Hare **to come back**

**[442. Find All Duplicates in an Array](https://leetcode.com/problems/find-all-duplicates-in-an-array/)**

Given an integer array nums of length n where all the integers of nums are in the range [1, n] and each integer appears once or twice, return an array of all the integers that appears twice.

You must write an algorithm that runs in O(n) time and uses only constant extra space.

```
Input: nums = [4,3,2,7,8,2,3,1]
Output: [2,3]
```

- sort, and compare nums[i] == nums[i+1]. Time O(nlogn) Space O(1)
- hastable, store seen elements in a map. Time O(n) Space
- flip signs in place: first time seen value = x, flip nums[x] negative. if then need to flip again, means this number is repeated and add that to return list

### Spatial Operations

Spatial Operations includes dealing with 2D matrices: rotation, value manipulation, reading matrices in specific orders, and others.

**[2022. Convert 1D Array Into 2D Array](https://leetcode.com/problems/convert-1d-array-into-2d-array/)**

You are given a 0-indexed 1-dimensional (1D) integer array original, and two integers, m and n. You are tasked with creating a 2-dimensional (2D) array with m rows and n columns using all the elements from original.

The elements from indices 0 to n - 1 (inclusive) of original should form the first row of the constructed 2D array, the elements from indices n to 2 \* n - 1 (inclusive) should form the second row of the constructed 2D array, and so on.

Return an m x n 2D array constructed according to the above procedure, or an empty 2D array if it is impossible.

```
Input: original = [1,2,3,4], m = 2, n = 2
Output: [[1,2],[3,4]]
```

- Python: Slicing. Key is to understand the start and end index for each 2D row in the 1D array. Start will be row_idx in, end will be row_idx in + n.
  `return [ original[i*n:(i+1)*n] for i in range(m) ] if len(original) == m*n else []`

**[73. Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)**

Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.

```
Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
```

- Make exact copy of the matrix, then set values of this new matrix based on where the zeros are in the old matrix. Time O(mn), Space O(mn)
- Use two vectors of size m and n to keep track of which rows and columns to set to 0. Time O(mn), Space O(m+n)
- Instead of using two vectors, we can use the first column and first row inplace to keep track of which row/column to set to 0. Space O(1).
  Important to note, the first cell mat[0][0] is shared by the first column and first row. Therefore, we should mandate this cell to either only control zero'ing out the first row, or the first column, but not both. If we choose this to zero out the first row, then we will use one additional space for recording whether to zero out the first column.

### Others

**[238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)**

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

```
Input: nums = [1,2,3,4]
Output: [24,12,8,6]
```

- compute product of all elements, then divide by the number in place. Time O(n), Space O(1). Note, the problem states that "you must write an algorithm that runs in O(n) time and without using the division operation". This solution violates the prerequisite.
- compute cumulative product to the left and right of the number, then combine these two numbers. Time O(n), Space O(n).
