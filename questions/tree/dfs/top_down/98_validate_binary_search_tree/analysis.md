# Analysis — 98. Validate Binary Search Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/top_down (passing state down the tree)
BST validity depends on the full path from root to each node — the valid range narrows as you descend. This requires passing inherited bounds (`min`, `max`) top-down as arguments, not derivable bottom-up.

## Layer 2 — Algorithms & Techniques
- Top-down DFS with inherited min/max bounds: O(n)
- **Insight:** Pass `(left_bound, right_bound)` as arguments to the helper. Going left tightens the upper bound (`right = node.val`); going right tightens the lower bound (`left = node.val`). The helper is necessary because the public API `isValidBST(root)` has no parameters for bounds — extra state requires a wrapper function.

## Layer 1 — Data Structures
- Implicit call stack (recursive DFS)

## Implementation

```python
def isValidBST(self, root):
    def isValid(node, left, right):
        if not node:
            return True
        if not (left < node.val < right):
            return False
        return isValid(node.left, left, node.val) and isValid(node.right, node.val, right)

    return isValid(root, float("-inf"), float("inf"))
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Contrast with 1448 (Count Good Nodes)
Both are top_down: state flows from parent to child via arguments.
- 1448 passes `max_so_far` (single bound, max path value)
- 98 passes `(left, right)` (double bounds, valid range that narrows each level)
- Both need a helper because the public method signature lacks parameters for the inherited state
