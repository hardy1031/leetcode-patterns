# Analysis: 621. Task Scheduler

## Layer 3 — Problem-solving Pattern
**Pattern:** Heap / Priority Queue + Greedy
Always process the most frequent remaining task → greedy drives maxHeap choice. Cooldown window management requires tracking when each task becomes available again.

## Layer 2 — Algorithms & Techniques
- MaxHeap + deque O(n log k) where k = unique task count
- **Insight:** Heap + deque combo — maxHeap picks the greedily best task each cycle; deque holds cooling-down tasks as `(remaining_count, available_at_time)` in FIFO order (first cooled = first re-eligible).

## Layer 1 — Data Structures
- MaxHeap of `-count` values (Python min-heap negation trick)
- Deque of `(count, available_time)` tuples for cooldown tracking
- `time` counter as the scheduling clock
