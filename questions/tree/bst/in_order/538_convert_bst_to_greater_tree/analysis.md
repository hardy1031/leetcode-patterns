# Analysis — 538. Convert BST to Greater Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bst — reverse in-order traversal (right → root → left)
Visiting in reverse in-order gives nodes in descending order. Accumulating a running sum and adding it to each node gives the "sum of all greater nodes" at every step.

## Layer 2 — Algorithms & Techniques
- Iterative reverse in-order DFS with running sum: O(n)
- **Insight:** Reverse in-order = descending order for BST. A single `right_sum` variable accumulates as you visit nodes from largest to smallest. After updating `current.val += right_sum`, set `right_sum = current.val` (the new cumulative value) — not `right_sum += current.val`, which would double-count the added sum.

## Layer 1 — Data Structures
- Explicit stack (iterative DFS)

## Implementation

```python
def convertBST(self, root):
    current = root
    stack = []
    right_sum = 0

    while current or stack:
        while current:
            stack.append(current)
            current = current.right       # go right first (reverse in-order)
        current = stack.pop()
        current.val += right_sum
        right_sum = current.val           # cumulative sum = updated node value
        current = current.left

    return root
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Contrast with 230 and 530
All three use the same iterative stack pattern — only the traversal direction and the action at each node differ:
- 230: in-order (left first), counter → return at k
- 530: in-order (left first), `prev` pointer → compare adjacent diff
- 538: **reverse** in-order (right first), running sum → update node value in-place
