# Analysis: 347. Top K Frequent Elements

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map + Bucket Sort
2段階: ① frequency を数える → ② frequency の多い順に上位 k 個を取り出す

## Layer 2 — Algorithms & Techniques
- Step 1: Hash Map で各要素の frequency を O(n) でカウント
- Step 2: Bucket Sort で frequency をインデックスとした配列に振り分け → O(n) で降順スキャン
- 合計: O(n)
- 比較: `sorted()` を使うと Step 2 が O(n log n) になる

## Layer 1 — Data Structures
- Array (input)
- Hash Map (element → frequency)
- Bucket array (index = frequency, value = list of elements)
