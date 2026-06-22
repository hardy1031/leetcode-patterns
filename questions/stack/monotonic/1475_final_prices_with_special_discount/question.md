# 1475. Final Prices With a Special Discount in a Shop

You are given an integer array `prices` where `prices[i]` is the price of the ith item in a shop.

If you buy the ith item, you receive a discount equal to `prices[j]` where `j` is the minimum index such that `j > i` and `prices[j] <= prices[i]`. If no such `j` exists, no discount is applied.

Return an array `answer` where `answer[i]` is the final price after discount.

## Examples

**Example 1:**
```
Input: prices = [8,4,6,2,3]
Output: [4,2,4,2,3]
```

**Example 2:**
```
Input: prices = [1,2,3,4,5]
Output: [1,2,3,4,5]
```

**Example 3:**
```
Input: prices = [10,1,1,6]
Output: [9,0,1,6]
```

## Constraints
- `1 <= prices.length <= 500`
- `1 <= prices[i] <= 1000`

## Links
- [LeetCode](https://leetcode.com/problems/final-prices-with-a-special-discount-in-a-shop/)
