# 142. Linked List Cycle II

**Difficulty:** Medium
**Pattern:** linked_list/fast_slow_pointers/floyd_cycle_detection

## Problem

Given the head of a linked list, return the node where the cycle begins. If there is no cycle, return null.

## Examples

**Example 1:**
```
Input:  head = [3,2,0,-4], pos = 1
Output: tail connects to node index 1
```

**Example 2:**
```
Input:  head = [1,2], pos = 0
Output: tail connects to node index 0
```

**Example 3:**
```
Input:  head = [1], pos = -1
Output: no cycle
```

## Constraints

- `0 <= Number of nodes <= 10^4`
- `-10^5 <= Node.val <= 10^5`
- `pos` is -1 or a valid index in the linked list

## Links

- [LeetCode](https://leetcode.com/problems/linked-list-cycle-ii/)
- [NeetCode](https://neetcode.io/problems/linked-list-cycle-ii)
