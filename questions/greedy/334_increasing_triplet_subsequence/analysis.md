# Analysis: 334. Increasing Triplet Subsequence

## Layer 3 — Problem-solving Pattern
**Pattern:** Greedy
Track running first and second minimums; if any element exceeds second, return true.

## Layer 2 — Algorithms & Techniques
- Greedy single pass O(n)
- Two-variable state: first = smallest seen, second = smallest seen after first

## Layer 1 — Data Structures
- Array (input)
