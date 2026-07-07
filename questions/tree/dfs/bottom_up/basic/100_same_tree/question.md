# 100. Same Tree

**Difficulty:** Easy
**Pattern:** tree/dfs/basic
**LeetCode:** https://leetcode.com/problems/same-tree/
**NeetCode:** https://neetcode.io/problems/same-binary-tree

## Problem

Given the roots of two binary trees `p` and `q`, return true if the trees are equivalent, otherwise return false. Two binary trees are equivalent if they share the exact same structure and the nodes have the same values.

## Examples

```
Input: p = [1,2,3], q = [1,2,3]
Output: true

Input: p = [4,7], q = [4,null,7]
Output: false

Input: p = [1,2,3], q = [1,3,2]
Output: false
```

## Constraints

- `0 <= number of nodes in both trees <= 100`
- `-100 <= Node.val <= 100`
