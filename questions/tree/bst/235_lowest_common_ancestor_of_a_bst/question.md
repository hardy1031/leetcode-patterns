# 235. Lowest Common Ancestor of a Binary Search Tree

**Difficulty:** Medium
**Pattern:** tree/bst
**LeetCode:** https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/
**NeetCode:** https://neetcode.io/problems/lowest-common-ancestor-in-bst

## Problem

Given a BST where all node values are unique, and two nodes `p` and `q`, return the lowest common ancestor (LCA). The LCA is the lowest node that has both `p` and `q` as descendants (a node can be a descendant of itself).

## Examples

```
Input: root = [5,3,8,1,4,7,9,null,2], p = 3, q = 8
Output: 5

Input: root = [5,3,8,1,4,7,9,null,2], p = 3, q = 4
Output: 3  (3 is an ancestor of itself)
```

## Constraints

- `2 <= number of nodes <= 100`
- `-100 <= Node.val <= 100`
- `p != q`
- Both `p` and `q` exist in the BST
