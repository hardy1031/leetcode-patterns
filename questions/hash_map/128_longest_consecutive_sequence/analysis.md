# 128. Longest Consecutive Sequence — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map (Set)
各数字が「sequence の先頭か」を O(1) で判定 → set で membership check

## Layer 2 — Algorithms & Techniques
- Set lookup: `num-1 not in set` で sequence の起点を特定 O(1)
- Linear scan from each start: 起点からカウント
- 全体 O(n)（各要素は最大2回参照される）

## Layer 1 — Data Structures
- set — O(1) membership lookup のための index
