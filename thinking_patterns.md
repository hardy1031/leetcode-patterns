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

---

## Subarray Sum/Product Extremes → Kadane's

**When to use:**
Problem asks for max or min sum (or product) of a contiguous subarray.

**Signs:**
- "subarray" (contiguous) is mentioned
- Looking for max/min aggregate (sum, product)
- O(n) solution is expected

**Core idea:**
At each index, decide: extend the current subarray, or restart fresh?
`current = max(nums[i], current + nums[i])`
Restart only when carrying forward makes things worse (`current < 0`).

**Why it covers all subarrays in O(n):**
- `current` = max sum of subarrays **ending at index i**
- `best` = max of all `current` values seen so far

Every possible subarray ends at some index i.
So: all subarrays = (subarrays ending at i=0) ∪ (ending at i=1) ∪ ... ∪ (ending at i=n-1)
`current` finds the best in each group; `best` finds the best across all groups.
→ equivalent to comparing every subarray, but in O(n).

**Variants:**
- Max sum subarray → standard Kadane's (53)
- Max sum circular subarray → Kadane's twice: `max(kadane_max, total - kadane_min)` (918)
- Max product subarray → track both min and max (negative × negative flips sign) (152)
- Max absolute sum → `kadane_max + abs(kadane_min)` (1749)

---

## "First element to the right that beats me" → Monotonic Stack

**Trigger:**
For each element, find the first element to its right that is greater (or smaller).

**Why the target being different per element matters:**
Each element has its own unique answer → many elements are unresolved at the same time → you need a structure that holds multiple waiting states. That's why HashMap, two pointers, and greedy all fail:

| Structure | Why it fails |
|-----------|-------------|
| HashMap / Set | No positional info — can't tell which waiting element is closest to the right |
| Two Pointers | Can't hold multiple in-progress states |
| Greedy | Makes one local choice — can't track multiple waiting elements |

**Why stack specifically:**
1. Holds multiple unresolved elements
2. LIFO — checks the most recently added (closest) element first
3. Descending invariant → if current element can't resolve the top, it can't resolve anything below → early stop

**"Closest" = positional order matters:**
```
nums2 = [1, 4, 2, 3]
```
When `3` arrives, `1`, `4`, `2` are all waiting.
- `2`'s answer is `3` (first greater to its right)
- `1`'s answer is `4` (not `3` — `4` was closer)

A set `{1, 4, 2}` loses this positional info. The stack preserves it.

**Examples:** 739 (Daily Temperatures), 496 (Next Greater Element), 1475 (Final Prices)
