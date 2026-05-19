# Analysis: 75. Sort Colors

## Layer 3 — Problem-solving Pattern
**Pattern:** Bucket Sort
値が 0, 1, 2 の3種類のみ → range が固定 → Bucket Sort で O(n)

## Layer 2 — Algorithms & Techniques
- Bucket Sort: freqMap で各色のカウント → bucket を順に展開 → O(n)
- Dutch National Flag (one-pass): 3 pointer (low, mid, high) で O(n) かつ O(1) space
- `nums[:] = result` で in-place 書き換え（`nums = result` は NG）

## Layer 1 — Data Structures
- Array (input, in-place modification required)
- Hash Map または固定長カウント配列 (freq[0], freq[1], freq[2])
