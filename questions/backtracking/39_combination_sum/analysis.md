# 39. Combination Sum — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Backtracking
Try each number from index i onward, adding it to current. Recurse with the same i (same element can be reused). Prune when sum exceeds target.

## Layer 2 — Algorithms & Techniques
- Backtracking O(n^(t/m)) where t=target, m=min element
- **Insight:** `range(i, len(nums))` prevents duplicates like [2,5] and [5,2] — by never going back to a lower index, each combination is generated in exactly one order. `range(len(nums))` would allow backtracking to earlier indices, producing reordered duplicates.

## Layer 1 — Data Structures
- List (`current`) mutated in-place, copied when sum == target
- Implicit call stack for recursion
