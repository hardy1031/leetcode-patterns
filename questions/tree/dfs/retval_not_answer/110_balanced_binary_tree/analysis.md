# Analysis — 110. Balanced Binary Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/path_problems
Check balance at every node using height computed bottom-up. Same structure as diameter: the recursive function returns height (a helper metric), while the real answer (is_balanced) is tracked as a side effect via `nonlocal`.

## Layer 2 — Algorithms & Techniques
- Post-order DFS: O(n)
- **Insight:** Return height from the recursive function (bottom-up buildable), and update a `nonlocal` boolean when `abs(left - right) > 1`. Early-exit optimization: if already unbalanced, skip remaining nodes with `if not result: return 0`.

## Layer 1 — Data Structures
- Implicit call stack (recursive DFS)
- `nonlocal` boolean to persist result across recursive calls

## Implementation

```python
def isBalanced(self, root):
    result = True
    def dfs(node):
        nonlocal result
        if not node or not result:
            return 0
        left = dfs(node.left)
        right = dfs(node.right)
        if abs(left - right) > 1:
            result = False
        return max(left, right) + 1
    dfs(root)
    return result
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Relation to 543
Identical structure to Diameter of Binary Tree — both use `nonlocal` to track the answer while the recursive function returns height. The condition checked at each node differs: `left + right` (diameter) vs `abs(left - right) > 1` (balance).
