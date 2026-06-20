# 150. Evaluate Reverse Polish Notation

**Difficulty:** Medium

## Problem

You are given an array of strings `tokens` that represents an arithmetic expression in Reverse Polish Notation.

Evaluate the expression. Return an integer that represents the value of the expression.

- The valid operators are `'+'`, `'-'`, `'*'`, and `'/'`.
- Each operand may be an integer or another expression.
- Division between two integers always truncates toward zero.
- There will not be any division by zero.
- The answer and all intermediate calculations can be represented in a 32-bit integer.

## Examples

**Example 1:**
```
Input: tokens = ["2","1","+","3","*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9
```

**Example 2:**
```
Input: tokens = ["4","13","5","/","+"]
Output: 6
Explanation: (4 + (13 / 5)) = 6
```

**Example 3:**
```
Input: tokens = ["10","6","9","3","+","-11","*","/","*","17","+","5","+"]
Output: 22
```

## Constraints
- 1 <= tokens.length <= 10⁴
- tokens[i] is '+', '-', '*', '/', or a string representing an integer in [-200, 200]

## Links
- [LeetCode](https://leetcode.com/problems/evaluate-reverse-polish-notation/)
- [NeetCode](https://neetcode.io/problems/evaluate-reverse-polish-notation)
