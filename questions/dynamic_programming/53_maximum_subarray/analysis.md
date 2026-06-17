# Analysis — 53. Maximum Subarray

## Layer 3 — Problem-solving Pattern
**Pattern:** Dynamic Programming (Kadane's)
Contiguous subarray + max sum → Kadane's is the canonical O(n) solution.

## Layer 2 — Algorithms & Techniques
- Kadane's Algorithm O(n) time, O(1) space
- **Insight:** DP + greedy — `current` = max subarray ending at i; greedily restart when `current < 0`. `best` tracks max across all i, covering every possible subarray in one pass.

## Layer 1 — Data Structures
- Array (in-place scan, no auxiliary structure needed)
