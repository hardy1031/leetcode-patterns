# 853. Car Fleet

There are `n` cars traveling to the same destination on a one-lane highway.

You are given two arrays `position` and `speed`, both of length `n`.
- `position[i]` is the position of the ith car (in miles)
- `speed[i]` is the speed of the ith car (in miles per hour)

A car cannot pass another car ahead of it — it can only catch up and drive at the same speed. A car fleet is a set of cars driving at the same position and speed. If a car catches up to a fleet exactly at the destination, it joins that fleet.

Return the number of car fleets that arrive at the destination.

## Examples

**Example 1:**
```
Input: target = 10, position = [1,4], speed = [3,2]
Output: 1
```

**Example 2:**
```
Input: target = 10, position = [4,1,0,7], speed = [2,2,1,1]
Output: 3
```

## Constraints
- `n == position.length == speed.length`
- `1 <= n <= 1000`
- `0 < target <= 1000`
- `0 < speed[i] <= 100`
- `0 <= position[i] < target`
- All values of position are unique

## Links
- [LeetCode](https://leetcode.com/problems/car-fleet/)
- [NeetCode](https://neetcode.io/problems/car-fleet)
