# 538. Convert BST to Greater Tree

**Difficulty:** Medium
**Pattern:** tree/bst (reverse in-order traversal)

## Problem

Given the root of a Binary Search Tree, convert it to a Greater Tree such that every key of the original BST is changed to the original key plus the sum of all keys greater than the original key in BST.

## Examples

**Example 1:**
```
Input: root = [4,1,6,0,2,5,7,null,null,null,3,null,null,null,8]
Output: [30,36,21,36,35,26,15,null,null,null,33,null,null,null,8]
```

**Example 2:**
```
Input: root = [0,null,1]
Output: [1,null,1]
```

## Constraints

- `0 <= number of nodes <= 100`
- `-10^4 <= Node.val <= 10^4`
- All values are unique.

## Links

- [LeetCode](https://leetcode.com/problems/convert-bst-to-greater-tree/)
- [NeetCode](https://neetcode.io/problems/convert-bst-to-greater-tree)
