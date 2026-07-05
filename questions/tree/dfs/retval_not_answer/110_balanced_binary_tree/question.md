# 110. Balanced Binary Tree

**Difficulty:** Easy
**Pattern:** tree/dfs/path_problems
**LeetCode:** https://leetcode.com/problems/balanced-binary-tree/
**NeetCode:** https://neetcode.io/problems/balanced-binary-tree

## Problem

Given a binary tree, return true if it is height-balanced and false otherwise.

A height-balanced binary tree is one where the left and right subtrees of every node differ in height by no more than 1.

## Examples

```
Input: root = [1,2,3,null,null,4]
Output: true

Input: root = [1,2,3,null,null,4,null,5]
Output: false

Input: root = []
Output: true
```

## Constraints

- `0 <= number of nodes <= 1000`
- `-1000 <= Node.val <= 1000`
