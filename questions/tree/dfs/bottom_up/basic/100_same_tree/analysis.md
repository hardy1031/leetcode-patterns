# Analysis — 100. Same Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/basic
Traverse both trees simultaneously. At each step, compare structure and value. The recursive return value IS the answer (true/false) — no nonlocal needed.

## Layer 2 — Algorithms & Techniques
- Recursive DFS on two trees in parallel: O(n)
- **Insight:** Variation of basic DFS where two trees are traversed simultaneously instead of one. Base cases must handle all null combinations: both null (true), one null (false), values differ (false).

## Layer 1 — Data Structures
- Implicit call stack (recursive DFS)

## Implementation

```python
def isSameTree(self, p, q):
    if not p and not q:
        return True
    if not p or not q:
        return False
    if p.val != q.val:
        return False
    return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
```

## Complexity
- Time: O(n) where n = number of nodes in the smaller tree
- Space: O(h) where h = tree height
