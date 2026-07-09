# 105. Construct Binary Tree from Preorder and Inorder Traversal

**Difficulty:** Medium
**Pattern:** tree/construction

## Problem

Given two integer arrays `preorder` and `inorder`:
- `preorder` is the preorder traversal of a binary tree
- `inorder` is the inorder traversal of the same tree

Rebuild the binary tree and return its root.

## Examples

**Example 1:**
```
Input: preorder = [1,2,3,4], inorder = [2,1,3,4]
Output: [1,2,3,null,null,null,4]
```

**Example 2:**
```
Input: preorder = [1], inorder = [1]
Output: [1]
```

## Constraints

- `1 <= inorder.length <= 1000`
- `inorder.length == preorder.length`
- `-1000 <= preorder[i], inorder[i] <= 1000`
- All values are unique.

## Links

- [LeetCode](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)
- [NeetCode](https://neetcode.io/problems/binary-tree-from-preorder-and-inorder-traversal)
