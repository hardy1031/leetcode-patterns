# 98. Validate Binary Search Tree

**Difficulty:** Medium
**Pattern:** tree/dfs/top_down

## Problem

Given the root of a binary tree, return `true` if it is a valid binary search tree, otherwise return `false`.

A valid binary search tree satisfies the following constraints:
- The left subtree of every node contains only nodes with keys **less than** the node's key.
- The right subtree of every node contains only nodes with keys **greater than** the node's key.
- Both the left and right subtrees are also binary search trees.

## Examples

**Example 1:**
```
Input: root = [2,1,3]
Output: true
```

**Example 2:**
```
Input: root = [1,2,3]
Output: false
Explanation: Root is 1 but its left child is 2, which is greater than 1.
```

## Constraints

- `1 <= number of nodes <= 1000`
- `-1000 <= Node.val <= 1000`

## Links

- [LeetCode](https://leetcode.com/problems/validate-binary-search-tree/)
- [NeetCode](https://neetcode.io/problems/valid-binary-search-tree)
