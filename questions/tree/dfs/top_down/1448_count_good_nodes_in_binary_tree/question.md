# 1448. Count Good Nodes in Binary Tree

**Difficulty:** Medium
**Pattern:** tree/dfs/top_down
**LeetCode:** https://leetcode.com/problems/count-good-nodes-in-binary-tree/
**NeetCode:** https://neetcode.io/problems/count-good-nodes-in-binary-tree

## Problem

A node `x` is considered good if no node on the path from root to `x` has a value greater than `x`. Return the number of good nodes in the tree.

## Examples

```
Input: root = [2,1,1,3,null,1,5]
Output: 3

Input: root = [1,2,-1,3,4]
Output: 4
```

## Constraints

- `1 <= number of nodes <= 100`
- `-100 <= Node.val <= 100`
