# Analysis: 451. Sort Characters By Frequency

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map + Bucket Sort
347. Top K Frequent Elements と同じ2段階構造。

## Layer 2 — Algorithms & Techniques
- Step 1: Hash Map で各文字の frequency をカウント → O(n)
- Step 2: Bucket Sort で frequency を index とした配列に振り分け → O(n)
- 末尾から bucket をスキャンして文字を繰り返し連結 → O(n)
- 合計: O(n)

## Layer 1 — Data Structures
- String (input)
- Hash Map (char → frequency)
- Bucket array (index = frequency, value = list of chars)
