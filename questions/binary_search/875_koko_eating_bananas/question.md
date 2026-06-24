# 875. Koko Eating Bananas

You are given an integer array `piles` where `piles[i]` is the number of bananas in the ith pile, and an integer `h` representing the number of hours you have to eat all the bananas.

Each hour, you may choose a pile and eat `k` bananas from it. If the pile has fewer than `k` bananas, you finish the pile but cannot eat from another pile that hour.

Return the minimum integer `k` such that you can eat all the bananas within `h` hours.

## Examples

**Example 1:**
```
Input: piles = [1,4,3,2], h = 9
Output: 2
```

**Example 2:**
```
Input: piles = [25,10,23,4], h = 4
Output: 25
```

## Constraints
- `1 <= piles.length <= 1000`
- `piles.length <= h <= 10^6`
- `1 <= piles[i] <= 10^9`

## Links
- [LeetCode](https://leetcode.com/problems/koko-eating-bananas/)
- [NeetCode](https://neetcode.io/problems/eating-bananas)
