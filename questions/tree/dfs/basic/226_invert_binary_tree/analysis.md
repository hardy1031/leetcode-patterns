# Analysis — 226. Invert Binary Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** DFS / BFS (tree traversal)
Visit every node and swap its left and right children. Order does not matter — swapping top-down or bottom-up both produce the correct result.

## Layer 2 — Algorithms & Techniques
- Recursive DFS: O(n)
- Iterative BFS (queue): O(n)
- **Insight:** The operation at each node is just `node.left, node.right = node.right, node.left` — the traversal method is interchangeable. Recursive DFS is the most concise.

## Layer 1 — Data Structures
- Implicit call stack (recursive)
- `deque` as queue (BFS iterative)

## Implementations

**Recursive:**
```python
def invertTree(self, root):
    if not root:
        return None
    root.left, root.right = root.right, root.left
    self.invertTree(root.left)
    self.invertTree(root.right)
    return root
```

**BFS iterative:**
```python
from collections import deque
def invertTree(self, root):
    if not root:
        return None
    queue = deque([root])
    while queue:
        node = queue.popleft()
        node.left, node.right = node.right, node.left
        if node.left: queue.append(node.left)
        if node.right: queue.append(node.right)
    return root
```

## Complexity
- Time: O(n)
- Space: O(h) recursive (h = height), O(n) BFS worst case
