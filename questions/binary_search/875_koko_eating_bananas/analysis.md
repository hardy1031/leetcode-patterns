# Analysis: 875. Koko Eating Bananas

## Layer 3 — Problem-solving Pattern
**Pattern:** Binary Search on Answer Space
Not searching for a value in an array — searching for the minimum valid value in the answer space [1, max(piles)].

## Layer 2 — Algorithms & Techniques
- Binary search on answer space O(log(max(piles)))
- Linear scan to compute hours for a given k O(n)
- Total: O(n log(max(piles)))
- **Insight:** The answer space [1..max(piles)] is monotonic — larger k always means fewer hours. This means there's a clean NG/OK boundary, and binary search finds the leftmost OK. Track the best valid answer and keep searching left.

## Layer 1 — Data Structures
- Two pointers (left=1, right=max(piles)) on answer space
- No extra data structures needed

## Template for "minimum k" problems

```python
result = right
while left <= right:
    mid = (left + right) // 2
    if feasible(mid):
        result = mid      # valid, but try smaller
        right = mid - 1
    else:
        left = mid + 1    # not valid, need larger
return result
```

## Key difference from array binary search

| Array binary search | Answer space binary search |
|--------------------|-----------------------------|
| Search index in sorted array | Search value in [min..max] range |
| Target is given | "Feasibility" function defines the boundary |
| Return index | Return the boundary value |
