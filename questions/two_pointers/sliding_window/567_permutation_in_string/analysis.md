# 567. Permutation in String — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Sliding Window (fixed size)
window サイズ = `len(s1)` で固定。window 内の文字カウントが s1 のカウントと一致するか確認。

## Layer 2 — Algorithms & Techniques
- Fixed-size sliding window: right を進めながら left を同時に動かす
- Character frequency comparison: `Counter` 同士を比較 O(26) = O(1)
- 全体 O(n)

## Layer 1 — Data Structures
- dict (Counter) — 文字の出現回数。set では count が消えるので不可
