# Analysis: 153. Find Minimum in Rotated Sorted Array

## Layer 3 — Problem-solving Pattern
**Pattern:** Binary Search (modified — search space reduction)
Not just "is target here?" but "which half contains the minimum?"

## Layer 2 — Algorithms & Techniques
- Binary search O(log n)
- Condition: if mid > right, minimum is in right half; else in left half

## Layer 1 — Data Structures
- Array (sorted, rotated)
