# Analysis — 230. Kth Smallest Element in a BST

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bst — in-order traversal
In-order traversal (left → root → right) of a BST produces nodes in ascending sorted order. The kth smallest is simply the kth node visited.

## Layer 2 — Algorithms & Techniques
- Iterative in-order DFS with explicit stack: O(h + k)
- **Insight:** BST property `left < root < right` directly maps to in-order traversal order. Use an explicit stack to simulate the call stack: push all left children first, then pop and process, then move to right. Stop as soon as the kth node is reached — no need to traverse the rest.

## Layer 1 — Data Structures
- Explicit stack (iterative DFS)

## Implementation

```python
def kthSmallest(self, root, k):
    n = 0
    stack = []
    current = root

    while current or stack:
        while current:
            stack.append(current)
            current = current.left
        current = stack.pop()
        n += 1
        if n == k:
            return current.val
        current = current.right
```

## Complexity
- Time: O(h + k) where h = tree height
- Space: O(h) for the stack

## Key property to remember
**BST in-order = sorted ascending.** This is the foundational property that makes in-order traversal useful for BST problems. Pre/in/post-order:
- pre-order: root → left → right
- in-order: left → root → right  ← BST sorted order
- post-order: left → right → root
