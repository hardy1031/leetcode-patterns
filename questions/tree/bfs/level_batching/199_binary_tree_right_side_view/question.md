# 199. Binary Tree Right Side View

**Difficulty:** Medium
**Pattern:** tree/bfs/level_batching
**LeetCode:** https://leetcode.com/problems/binary-tree-right-side-view/
**NeetCode:** https://neetcode.io/problems/binary-tree-right-side-view

## Problem

Given the root of a binary tree, return only the values of the nodes visible from the right side, ordered from top to bottom.

## Examples

```
Input: root = [1,2,3,null,4,null,5]
Output: [1,3,5]

Input: root = [1,2,3,4,null,null,null,5]
Output: [1,3,4,5]

Input: root = [1,null,2]
Output: [1,2]

Input: root = []
Output: []
```

## Constraints

- `0 <= number of nodes <= 100`
- `-100 <= Node.val <= 100`
