# Analysis — 530. Minimum Absolute Difference in BST

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bst — in-order traversal + prev pointer
BST in-order produces ascending order, so the minimum difference is always between adjacent nodes. Track the previous node with a `prev` pointer and compare at each step.

## Layer 2 — Algorithms & Techniques
- Iterative in-order DFS with prev pointer: O(n)
- **Insight:** No need to compare all pairs — BST in-order is sorted, so adjacent nodes always give the smallest difference. `prev` follows `current` one step behind through the in-order sequence.

## Layer 1 — Data Structures
- Explicit stack (iterative DFS)

## Implementation

```python
def getMinimumDifference(self, root):
    min_difference = float("inf")
    current = root
    prev = None
    stack = []

    while current or stack:
        while current:
            stack.append(current)
            current = current.left
        current = stack.pop()
        if prev:
            min_difference = min(abs(current.val - prev.val), min_difference)
        prev = current
        current = current.right

    return min_difference
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Contrast with 230 (Kth Smallest)
Both use iterative in-order with the same stack pattern.
- 230: counter increments at each pop, return when counter == k
- 530: `prev` pointer tracks the last visited node, compare diff at each pop
