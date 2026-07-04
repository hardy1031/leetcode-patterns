# Analysis — 543. Diameter of Binary Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/path_problems
The diameter at any node = left height + right height. To find the global maximum, visit every node and record this sum. The recursive function returns height (not diameter) because height is what can be built up from children.

## Layer 2 — Algorithms & Techniques
- Post-order DFS: O(n)
- **Insight:** The recursive return value and the answer are different things. Recursion returns height (bottom-up buildable); the answer (diameter) is recorded as a side effect at each node via `nonlocal`. This separation — return value vs. side effect — is the defining pattern of path_problems.

## Layer 1 — Data Structures
- Implicit call stack (recursive DFS)
- `nonlocal` variable to persist answer across recursive calls

## Implementation

```python
def diameterOfBinaryTree(self, root):
    max_diameter = 0
    def dfs(node):
        nonlocal max_diameter
        if not node:
            return 0
        left = dfs(node.left)
        right = dfs(node.right)
        max_diameter = max(max_diameter, left + right)
        return 1 + max(left, right)
    dfs(root)
    return max_diameter
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height

## Key distinction from basic DFS
In basic DFS (invert, max depth), the recursive return value IS the answer.
In path_problems, the recursive return value is a helper metric (height); the real answer is updated as a side effect.
