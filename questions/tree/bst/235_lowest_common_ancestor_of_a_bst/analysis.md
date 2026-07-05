# Analysis — 235. Lowest Common Ancestor of a BST

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bst
Exploit BST ordering: if current is between p and q (inclusive), it must be the LCA. No need to visit both subtrees — the BST property tells you which direction to go.

## Layer 2 — Algorithms & Techniques
- Iterative BST traversal: O(h) where h = height
- **Insight:** Label the two nodes as `small` and `big`. The LCA is the first node where `small.val <= current.val <= big.val`. This covers three cases: current equals small, current equals big, or current splits the two nodes across left and right subtrees.

## Layer 1 — Data Structures
- No extra data structure — pointer walk down the BST

## Implementation

```python
def lowestCommonAncestor(self, root, p, q):
    small, big = (p, q) if p.val < q.val else (q, p)
    current = root
    while current:
        if current.val < small.val:
            current = current.right
        elif current.val > big.val:
            current = current.left
        else:
            return current
    return -1
```

## Complexity
- Time: O(h) — O(log n) balanced, O(n) worst case
- Space: O(1)

## Common mistake
Using `if` instead of `elif` for the three branches. With `if`, after `current = current.right`, Python continues evaluating the remaining `if` conditions on the updated `current` in the same iteration, causing incorrect behavior.
