# Analysis: 739. Daily Temperatures

## Layer 3 — Problem-solving Pattern
**Pattern:** Monotonic Stack
Each element waits for the next greater element to its right. Elements that haven't found their answer are held in a stack; when a larger value arrives, it resolves all smaller waiting elements at once.

## Layer 2 — Algorithms & Techniques
- Monotonic decreasing stack O(n)
- **Insight:** Stack stores indices of "unanswered" days in decreasing temperature order. A new temperature pops all stack entries it beats, resolving multiple answers in one pass — each element is pushed and popped at most once, giving O(n).

## Layer 1 — Data Structures
- Stack (indices)
- Result array (initialized to 0)
