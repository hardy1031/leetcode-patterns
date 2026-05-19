# Analysis: 274. H-Index

## Layer 3 — Problem-solving Pattern
**Pattern:** Bucket Sort
h-index は定義上 n を超えない → bucket の index に citation を n でキャップして使う

## Layer 2 — Algorithms & Techniques
- bucket[min(c, n)] += 1 で各 citation を論文数として記録 → O(n)
- 右から累積スキャン: total += bucket[i]、total >= i になった最大の i が h-index → O(n)
- 合計: O(n)

## Layer 1 — Data Structures
- Array (input)
- Bucket array, length n+1 (index = citation値をnでキャップ, value = 論文数)
