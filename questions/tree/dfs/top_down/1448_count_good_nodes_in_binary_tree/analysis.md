# Analysis — 1448. Count Good Nodes in Binary Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/top_down
Pass the maximum value seen on the path so far as an argument down the tree. Each node checks against this inherited state to determine if it is good.

## Layer 2 — Algorithms & Techniques
- Top-down DFS with inherited state: O(n)
- **Insight:** The "good" condition depends on the entire path from root to the current node — information that flows top-down, not bottom-up. Pass `max_so_far` as a parameter; each recursive call updates it before passing to children. The return value (count) still propagates bottom-up, but the decision-making uses the top-down state.

## Layer 1 — Data Structures
- Implicit call stack (recursive DFS)

## Implementation

```python
def goodNodes(self, root):
    def dfs(node, max_val):
        if not node:
            return 0
        max_val = max(node.val, max_val)
        left = dfs(node.left, max_val)
        right = dfs(node.right, max_val)
        return left + right + (1 if node.val >= max_val else 0)
    return dfs(root, root.val)
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Contrast with bottom_up
In bottom_up DFS, information flows from children to parent via return values.
In top_down DFS, information flows from parent to children via function arguments.
This problem uses both: `max_val` flows down as an argument, counts flow up as return values.
