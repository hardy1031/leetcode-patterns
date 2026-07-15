# 78. Subsets — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Backtracking
At each index, make a binary choice: include or exclude the element. Recurse both branches until i >= len(nums), then record the current state.

## Layer 2 — Algorithms & Techniques
- Backtracking O(n × 2^n)
- **Insight:** Include/exclude binary tree — call backtrack(i+1) twice: once after appending (include), once after popping (exclude). Every leaf of the recursion tree is a valid subset. Because i always increases, no duplicates are generated.

## Layer 1 — Data Structures
- List (`current`) mutated in-place, copied at leaf nodes
- Implicit call stack for recursion
