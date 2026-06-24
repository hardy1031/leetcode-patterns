# Analysis: 74. Search a 2D Matrix

## Layer 3 — Problem-solving Pattern
**Pattern:** Binary Search
The two constraints (each row sorted, first element of row > last of previous row) make the entire matrix one continuous sorted sequence → binary search once over m*n elements.

## Layer 2 — Algorithms & Techniques
- Binary search O(log(m*n))
- **Insight:** Treat 2D matrix as virtual 1D array using index math — no need to flatten. Convert 1D mid index to 2D with `row = mid // n`, `col = mid % n`. Divide by n (columns), not m (rows).

## Layer 1 — Data Structures
- Two pointers (left=0, right=m*n-1) on virtual 1D array

## Index conversion
```
row = mid // n   ← how many full rows fit before mid
col = mid % n    ← remainder = position within the row
```
