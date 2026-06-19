# 76. Minimum Window Substring — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Sliding Window (variable-size)
tの全文字を含む最小windowを求める → validになったらleftを縮め、invalidになったらrightを広げる。

## Layer 2 — Algorithms & Techniques
- Variable-size sliding window: valid中はleftを縮め続ける
- Frequency dict comparison: target_windowとcurrent_windowを比較してvalid判定
- **Insight:** valid判定をhave/need整数カウンタで管理するとO(1)になる（毎回dict比較するとO(n)）

## Layer 1 — Data Structures
- dict (target_window) — tの各文字の必要数
- dict (current_window) — window内の各文字の現在数
