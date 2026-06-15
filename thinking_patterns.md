# Thinking Patterns

A collection of meta-level problem-solving patterns — not algorithms or data structures,
but ways of *framing* a problem that unlock the solution.

---

## Subtract from Total

**When to use:**
The thing you want is "part of the whole", and the complement (what you exclude) is easier to optimize.

**Signs:**
- The range/subset you want is discontinuous or has a complex shape
- The part you *exclude* is contiguous and simple
- The total sum/size is fixed or already known

**Examples:**
- 918 (Maximum Sum Circular Subarray): `total - min_subarray` → max wraparound subarray
  - Wraparound is hard to bound directly; the middle portion to exclude is a normal subarray
- 424 (Longest Repeating Character Replacement): `window_size - max_count` → characters that need replacing
  - Easier to track the dominant character than enumerate what to replace
