# Analysis: 238. Product of Array Except Self

## Layer 3 — Problem-solving Pattern
**Pattern:** Prefix Sums (prefix/suffix product)
answer[i] = prefix_product[i] * suffix_product[i]

## Layer 2 — Algorithms & Techniques
- Two-pass prefix/suffix build O(n)
- Can optimize to O(1) extra space by combining into single output array

## Layer 1 — Data Structures
- Array (prefix products, suffix products, output)
