# Analysis — 102. Binary Tree Level Order Traversal

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/bfs
Process nodes level by level using a queue. The key mechanic is snapshotting `len(queue)` before the inner loop to process exactly one level per outer iteration.

## Layer 2 — Algorithms & Techniques
- BFS with level batching: O(n)
- **Insight:** Before processing each level, record `q_len = len(queue)`. Loop exactly `q_len` times to consume that level's nodes while their children (next level) are being added. Without this snapshot, you cannot distinguish where one level ends and the next begins.

## Layer 1 — Data Structures
- `deque` as BFS queue

## Implementation

```python
from collections import deque

def levelOrder(self, root):
    if not root:
        return []
    queue = deque([root])
    result = []
    while queue:
        level = []
        for _ in range(len(queue)):   # snapshot current level size
            node = queue.popleft()
            level.append(node.val)
            if node.left: queue.append(node.left)
            if node.right: queue.append(node.right)
        result.append(level)
    return result
```

## Complexity
- Time: O(n)
- Space: O(n) for queue + result

## Edge case
`root = None` → return `[]` before initializing the queue. Without this guard, `deque([None])` causes `NoneType` error on `node.val`.
