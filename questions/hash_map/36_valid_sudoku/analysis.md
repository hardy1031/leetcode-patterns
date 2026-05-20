# 36. Valid Sudoku — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map
行・列・ブロックそれぞれで重複チェックが必要 → 各グループの要素の頻度を数える

## Layer 2 — Algorithms & Techniques
- Frequency counting with hash map O(81) = O(1)
- 2D → 1D index conversion for blocks: `block_idx = (row//3)*3 + (col//3)`

## Layer 1 — Data Structures
- dict (hash map) — 各グループの数字の出現回数
- list of lists — rows, columns, blocks をそれぞれ9グループに分けて保持
