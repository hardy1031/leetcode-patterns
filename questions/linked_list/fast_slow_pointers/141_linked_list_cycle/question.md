# 141. Linked List Cycle

**Difficulty:** Easy
**Pattern:** linked_list/fast_slow_pointers

## Problem

Given the beginning of a linked list head, return true if there is a cycle in the linked list. Otherwise, return false.

There is a cycle in a linked list if at least one node in the list can be visited again by following the next pointer.

## Examples

**Example 1:**
```
Input: head = [1,2,3,4], index = 1
Output: true
```

**Example 2:**
```
Input: head = [1,2], index = -1
Output: false
```

## Constraints

- `0 <= Length of the list <= 1000`
- `-1000 <= Node.val <= 1000`
- `index` is -1 or a valid index in the linked list

## Links

- [LeetCode](https://leetcode.com/problems/linked-list-cycle/)
- [NeetCode](https://neetcode.io/problems/linked-list-cycle-detection)
