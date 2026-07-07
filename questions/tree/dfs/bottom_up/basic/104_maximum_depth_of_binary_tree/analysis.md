# Analysis — 104. Maximum Depth of Binary Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** DFS (tree traversal)
Traverse every node while tracking depth. At each leaf, update the max depth seen so far.

## Layer 2 — Algorithms & Techniques
- Recursive DFS: O(n)
- Iterative DFS with stack carrying `(node, depth)` pairs: O(n)
- BFS with level-order counting: O(n)
- **Insight:** DFS iterative is cleaner than BFS here — carry depth with each node in the stack as a tuple `(node, depth)`, so no need to batch-process levels.

## Layer 1 — Data Structures
- Implicit call stack (recursive)
- Explicit stack of `(TreeNode, int)` tuples (iterative DFS)

## Implementations

**Recursive:**
```python
def maxDepth(self, root):
    if not root:
        return 0
    return max(self.maxDepth(root.left), self.maxDepth(root.right)) + 1
```

**Iterative DFS:**
```python
def maxDepth(self, root):
    if not root:
        return 0
    stack = [(root, 1)]
    max_depth = 0
    while stack:
        node, depth = stack.pop()
        max_depth = max(max_depth, depth)
        if node.left: stack.append((node.left, depth + 1))
        if node.right: stack.append((node.right, depth + 1))
    return max_depth
```

## Complexity
- Time: O(n)
- Space: O(h) where h = tree height
