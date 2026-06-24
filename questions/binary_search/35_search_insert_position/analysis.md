# Analysis: 35. Search Insert Position

## Layer 3 — Problem-solving Pattern
**Pattern:** Binary Search
Sorted array + O(log n) → binary search. Twist: return insertion index when not found.

## Layer 2 — Algorithms & Techniques
- Binary search O(log n)
- **Insight:** Same template as 704, but `return left` instead of `return -1`. When the loop ends (`left > right`), `left` always points to the first element greater than target — exactly where target would be inserted.

## Layer 1 — Data Structures
- Two pointers (left, right) on sorted array

## Why `return left` works

When target is not found, the loop ends with `left > right`. At that moment:
- `left` = index of the first element greater than target
- This is exactly the insertion position

```
nums = [1, 3, 5, 6], target = 2
After loop: left=1, right=0
nums[1] = 3 → 2 would be inserted at index 1 ✓
```
