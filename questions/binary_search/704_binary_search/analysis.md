# Analysis: 704. Binary Search

## Layer 3 — Problem-solving Pattern
**Pattern:** Binary Search
Sorted array + O(log n) requirement → binary search directly on the array.

## Layer 2 — Algorithms & Techniques
- Binary search O(log n)
- **Insight:** Standard template problem — the goal is to internalize the template (`left <= right`, `mid+1`/`mid-1`) so corner cases never require thought.

## Layer 1 — Data Structures
- Two pointers (left, right) on sorted array

## Template (memorize this)

```python
left, right = 0, len(nums) - 1

while left <= right:
    mid = (left + right) // 2
    if nums[mid] == target:
        return mid
    elif nums[mid] < target:
        left = mid + 1
    else:
        right = mid - 1

return -1
```

### Three rules that eliminate all corner cases
| Rule | Why |
|------|-----|
| `left <= right` | When `left == right`, one element remains — must check it |
| `mid + 1` / `mid - 1` | mid is already checked, exclude it to avoid infinite loop |
| Compute mid inside the loop | left/right change every iteration |
