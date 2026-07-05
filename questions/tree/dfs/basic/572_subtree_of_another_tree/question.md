# 572. Subtree of Another Tree

**Difficulty:** Easy
**Pattern:** tree/dfs/basic
**LeetCode:** https://leetcode.com/problems/subtree-of-another-tree/
**NeetCode:** https://neetcode.io/problems/subtree-of-a-binary-tree

## Problem

Given the roots of two binary trees `root` and `subRoot`, return true if there is a subtree of `root` with the same structure and node values as `subRoot`, and false otherwise.

## Examples

```
Input: root = [3,4,5,1,2], subRoot = [4,1,2]
Output: true

Input: root = [3,4,5,1,2,null,null,null,null,0], subRoot = [4,1,2]
Output: false
```

## Constraints

- `1 <= number of nodes in root <= 2000`
- `1 <= number of nodes in subRoot <= 1000`
- `-10^4 <= Node.val <= 10^4`
