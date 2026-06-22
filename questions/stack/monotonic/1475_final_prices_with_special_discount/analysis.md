# Analysis: 1475. Final Prices With a Special Discount in a Shop

## Layer 3 — Problem-solving Pattern
**Pattern:** Monotonic Stack
Find the next smaller-or-equal element to the right for each index — same structure as Daily Temperatures but with `<=` instead of `>`.

## Layer 2 — Algorithms & Techniques
- Monotonic non-decreasing stack O(n)
- **Insight:** "Next smaller/equal element" is the mirror of "next greater element." Stack holds unanswered indices; when a price arrives that resolves waiting indices, pop and apply discount. O(n²) nested loop also works at n=500, but stack generalizes to large n.

## Layer 1 — Data Structures
- Stack (indices)
- Result array (copy of prices, updated in place)
