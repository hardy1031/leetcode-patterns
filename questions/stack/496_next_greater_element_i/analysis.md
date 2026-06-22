# Analysis: 496. Next Greater Element I

## Layer 3 — Problem-solving Pattern
**Pattern:** Monotonic Stack
Precompute the next greater element for every element in nums2, then look up nums1's elements in the result.

## Layer 2 — Algorithms & Techniques
- Monotonic decreasing stack on nums2 O(n)
- HashMap lookup for nums1 O(m)
- **Insight:** Decompose into two steps — (1) run monotonic stack on nums2 to build a next_greater hashmap, (2) look up each nums1 element. The two-array framing is a distraction; the hard part is just "next greater in nums2."

## Layer 1 — Data Structures
- Stack (values)
- HashMap (value → next greater value)
