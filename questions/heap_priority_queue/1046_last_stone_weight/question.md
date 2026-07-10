# 1046. Last Stone Weight

You are given an array of integers `stones` where `stones[i]` is the weight of the ith stone.

On each turn, choose the two heaviest stones and smash them together. If they are equal, both are destroyed. If not, the smaller one is destroyed and the larger one has its weight reduced by the smaller one's weight.

Return the weight of the last remaining stone, or `0` if no stones remain.

## Examples

**Example 1:**
```
Input: stones = [2,7,4,1,8,1]
Output: 1
```

**Example 2:**
```
Input: stones = [1]
Output: 1
```

## Constraints
- `1 <= stones.length <= 30`
- `1 <= stones[i] <= 1000`

## Links
- [LeetCode](https://leetcode.com/problems/last-stone-weight/)
- [NeetCode](https://neetcode.io/problems/last-stone-weight)
