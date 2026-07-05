# Analysis — 199. Binary Tree Right Side View

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bfs/level_batching
Process nodes level by level. For each level, the rightmost node is `queue[-1]` before the inner loop runs — snapshot it before consuming the level.

## Layer 2 — Algorithms & Techniques
- BFS with level batching: O(n)
- **Insight:** Before processing each level with `for _ in range(len(queue))`, the queue holds exactly that level's nodes in left-to-right order. So `queue[-1].val` is always the rightmost node of the current level — grab it before the loop modifies the queue.

## Layer 1 — Data Structures
- `deque` as BFS queue

## Implementation

```python
def rightSideView(self, root):
    if not root:
        return []
    queue = deque([root])
    result = []
    while queue:
        result.append(queue[-1].val)      # rightmost of current level
        for _ in range(len(queue)):
            node = queue.popleft()
            if node.left: queue.append(node.left)
            if node.right: queue.append(node.right)
    return result
```

## Complexity
- Time: O(n)
- Space: O(n)

## Relation to 102
Same level batching structure as Level Order Traversal. The only difference is what you record per level: all values (102) vs. just the rightmost value (199).
