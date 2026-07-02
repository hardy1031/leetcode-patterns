# 138. Copy List with Random Pointer

**Difficulty:** Medium
**Pattern:** hash_map

## Problem

You are given the head of a linked list of length n. Unlike a singly linked list, each node contains an additional pointer random, which may point to any node in the list, or null.

Create a deep copy of the list. None of the pointers in the new list should point to nodes in the original list.

## Examples

**Example 1:**
```
Input:  head = [[3,null],[7,3],[4,0],[5,1]]
Output: [[3,null],[7,3],[4,0],[5,1]]
```

**Example 2:**
```
Input:  head = [[1,null],[2,2],[3,2]]
Output: [[1,null],[2,2],[3,2]]
```

## Constraints

- `0 <= n <= 100`
- `-100 <= Node.val <= 100`
- `random` is null or points to some node in the linked list

## Links

- [LeetCode](https://leetcode.com/problems/copy-list-with-random-pointer/)
- [NeetCode](https://neetcode.io/problems/copy-linked-list-with-random-pointer)
