# 424. Longest Repeating Character Replacement — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Sliding Window
window 内で最も多い文字以外を置換すれば均一になる → `window_size - max_count <= k` が valid 条件。

## Layer 2 — Algorithms & Techniques
- Variable-size sliding window: invalid になったら left を縮める
- Key insight: `(right - left + 1) - max_count <= k`

## Layer 1 — Data Structures
- dict — window 内の各文字の frequency
- int (max_count) — window 内の最頻出文字の count（dict から毎回取り出せないので変数で保持）
