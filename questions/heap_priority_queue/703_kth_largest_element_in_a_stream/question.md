# 703. Kth Largest Element in a Stream

**Difficulty:** Easy
**Pattern:** heap_priority_queue

## Problem

Design a class to find the kth largest integer in a stream of values, including duplicates.

Implement:
- `constructor(int k, int[] nums)` — initializes with integer k and stream nums
- `int add(int val)` — adds val to the stream and returns the kth largest integer

## Examples

**Example 1:**
```
Input:
["KthLargest", [3, [1, 2, 3, 3]], "add", [3], "add", [5], "add", [6], "add", [7], "add", [8]]
Output:
[null, 3, 3, 3, 5, 6]
```

## Constraints

- `1 <= k <= 1000`
- `0 <= nums.length <= 1000`
- `-1000 <= nums[i], val <= 1000`
- There will always be at least k integers in the stream when searching.

## Links

- [LeetCode](https://leetcode.com/problems/kth-largest-element-in-a-stream/)
- [NeetCode](https://neetcode.io/problems/kth-largest-integer-in-a-stream)
