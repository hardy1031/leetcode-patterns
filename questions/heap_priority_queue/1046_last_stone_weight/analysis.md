# Analysis: 1046. Last Stone Weight

## Layer 3 — Problem-solving Pattern
**Pattern:** Heap / Priority Queue
Repeatedly extract the two maximums → max-heap.

## Layer 2 — Algorithms & Techniques
- Max-heap (simulated with negation) O(n log n)
- **Insight:** Python's `heapq` is min-heap only — negate all values to simulate max-heap. Push remainder as negative too, or heap order breaks.

## Layer 1 — Data Structures
- Min-heap with negated values (simulates max-heap)

## Key trap
When pushing the remainder back, must negate:
```python
heapq.heappush(stones, -(first - second))  # NOT (first - second)
```
