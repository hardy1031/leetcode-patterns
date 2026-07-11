# Analysis: 973. K Closest Points to Origin

## Layer 3 — Problem-solving Pattern
**Pattern:** Heap / Priority Queue
Find k smallest elements → min-heap all points, pop k times.

## Layer 2 — Algorithms & Techniques
- Min-heap O(n log n) push + O(k log n) pop
- **Insight:** Push `(distance, point)` tuple so the point is recoverable after pop. Skip `sqrt` — squared distance preserves ordering and avoids floating point overhead.

## Layer 1 — Data Structures
- Min-heap of `(squared_distance, point)` tuples
