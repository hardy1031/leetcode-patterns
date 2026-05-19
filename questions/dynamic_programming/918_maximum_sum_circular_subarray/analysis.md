# Analysis: 918. Maximum Sum Circular Subarray

## Layer 3 — Problem-solving Pattern
**Pattern:** Dynamic Programming (Kadane's Algorithm variant)
Two cases: (1) max subarray doesn't wrap → standard Kadane's; (2) wraps → total - min_subarray.

## Layer 2 — Algorithms & Techniques
- Kadane's Algorithm O(n)
- Insight: max circular = total - min subarray (inversion trick)

## Layer 1 — Data Structures
- Array (circular)
