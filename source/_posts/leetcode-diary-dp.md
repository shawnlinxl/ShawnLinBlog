---
title: Leetcode Diary - Dynamic Programming
date: 2022-06-29 15:22:23
tags: leetcode
---

# Dynamic Programming

## Min/Max Path to Reach a Target

Given a target, find the minimum/maximum path to reach the target.

```
routes[i] = min(routes[i-1], routes[i-2], ..., routes[i-k]) + cost[i]
```

### [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A subarray is a contiguous part of an array.

```
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
```

- trick: if previous sum + current num <= current num, then we can start over the subarray from current num since carrying the history doesn't make sense.
  ```
  dp[i] = max(dp[i-1] + nums[i], nums[i])
  max_sum = max(dp[i], max_sum)
  ```
- we don't have to keep a record of all dp[i]'s. We just need the current rolling sum.
- Time O(n), Space O(1)

### [152. Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)

Given an integer array nums, find a contiguous non-empty subarray within the array that has the largest product, and return the product.

```
Input: nums = [2,3,-2,4]
Output: 6
```

https://leetcode.com/problems/longest-increasing-subsequence/discuss/74824/JavaPython-Binary-search-O(nlogn)-time-with-explanation/206357

### [300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)

Given an integer array nums, return the length of the longest strictly increasing subsequence.

A subsequence is a sequence that can be derived from an array by deleting some or no elements without changing the order of the remaining elements. For example, [3,6,2,7] is a subsequence of the array [0,3,1,6,2,2,7].

- Defining the "states" of DP is very important for this question
  - if we define as length of longest sequence of subarrays, it is hard to solve
  - instead, we should define as longest sequence of subarrays that include the "last" entry, then it's easy to solve

### [198. House Robber](https://leetcode.com/problems/house-robber/)

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given an integer array nums representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.

```
Input: nums = [1,2,3,1]
Output: 4
```

- Recognize that max_profit(n) = max(max_profit(n-2)+profit(n), max_profit(n-1))

### [213. House Robber II](https://leetcode.com/problems/house-robber-ii/)

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and it will automatically contact the police if two adjacent houses were broken into on the same night.

- Similar to previous question. Note that first and last house cannot be robbed together. So break the series down to

  - 0..n-1
  - 1..n

  and compute two standard house robber problems, then take their max.

### [322. Coin Change](https://leetcode.com/problems/coin-change)

You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

```
Input: coins = [1,2,5], amount = 11
Output: 3
```

## Distinct Ways

Given a target, find a number of distinct ways to reach the target.

```python
routes[i] = routes[i-1] + routes[i-2] + ... + routes[i-k]
```

### [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

```
Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

- bottom-up
  - since there are two ways to move: step 1 step up for step 2 steps up, to reach step n, you can either:
    - step 1 step up from the n-1'th step
    - step 2 steps up from the n-2'th step
  - therefore, you can build the number of ways to reach step n from bottom up:
    - 1 way to reach 1st and 2nd step each
    - number of ways to reach step i = step(i-1) + step(i-2)
    - keep running unti we reach step n
  - important to cache the result of last 2 steps. You can choose to cache result for all intermdiate steps (easy to code) but that will consume more space.
  - Time O(n), Space O(1)
- top-down
  - similar to bottom up, but essentially it's recursion with a memoise array to record already computed data

### [303. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

Given an integer array nums, handle multiple queries of the following type:

Calculate the sum of the elements of nums between indices left and right inclusive where left <= right.

```
Input
["NumArray", "sumRange", "sumRange", "sumRange"]
[[[-2, 0, 3, -5, 2, -1]], [0, 2], [2, 5], [0, 5]]
Output
[null, 1, -1, -3]
```

- compute cumulative sum of input nums array, add a 0 at index 0: cumsum[i+1] = cumsum[i] + nums[i]
- sumRange(left, right) = cumsum[right+1] - cumsum[left]

### [494. Target Sum](https://leetcode.com/problems/target-sum/)

You are given an integer array nums and an integer target.

You want to build an expression out of nums by adding one of the symbols '+' and '-' before each integer in nums and then concatenate all the integers.

For example, if nums = [2, 1], you can add a '+' before 2 and a '-' before 1 and concatenate them to build the expression "+2-1".
Return the number of different expressions that you can build, which evaluates to target.

- Top Down Approach:
  - Recognize given nums and target, the recursion state is
    ```python
    dp[nums][target] = dp[nums[0:(n-1)]][target-nums[n]] + dp[nums[0:(n-1)]][target+nums[n]]
    ```
  - The initial state for nums of length 1 is
    ```python
    nums[0] == target + nums[0] == -target
    ```
  - Cache the intermediate steps smartly
    - Note: Python can use tuple (int_i,int_j) as key for dictionary
