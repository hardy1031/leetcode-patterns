# 3. Longest Substring Without Repeating Characters — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Sliding Window
window 内に duplicate がないよう left/right を管理。1 pointer だと戻る必要が生じるため sliding window が必要。

## Layer 2 — Algorithms & Techniques
- Sliding window with set: right を進めて duplicate があれば left を縮める
- 両ポインタとも右にしか動かない → O(n)

## Layer 1 — Data Structures
- set — window 内の文字の membership tracking
