# 46. Permutations — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Backtracking
At each step, try every remaining unused element. Use a set to track what's available. When the set is empty, all elements are placed — record the result.

## Layer 2 — Algorithms & Techniques
- Backtracking O(n × n!)
- **Insight:** Unlike combinations, order matters — [2,5] and [5,2] are different permutations. So instead of `range(i, len(nums))` (forward-only), iterate over all remaining elements in a set. Remove on choose, add back on unchoose.

## Layer 1 — Data Structures
- Set (`num_set`) for O(1) remove/add of remaining elements
- List (`current`) mutated in-place, copied at leaf nodes
