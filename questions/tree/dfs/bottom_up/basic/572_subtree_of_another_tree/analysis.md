# Analysis — 572. Subtree of Another Tree

## Layer 3 — Problem-solving Pattern
**Pattern:** tree/dfs/basic (with embedded isSameTree helper)
Traverse root to find candidate nodes, then call isSameTree at each match. Combines two basic DFS problems: tree traversal + same tree check.

## Layer 2 — Algorithms & Techniques
- BFS/DFS over root + isSameTree at each candidate: O(n × m)
- **Insight:** Reuse the isSameTree pattern (100) as a helper. The outer traversal finds candidates by value match; isSameTree confirms full structural equality. O(n+m) is possible via serialization + KMP but not worth the complexity in interviews.

## Layer 1 — Data Structures
- `deque` for BFS traversal of root
- Implicit call stack for recursive isSameTree

## Implementation

```python
from collections import deque

def isSubtree(self, root, subRoot):
    def isSameTree(r1, r2):
        if not r1 and not r2:
            return True
        if not r1 or not r2:
            return False
        if r1.val != r2.val:
            return False
        return isSameTree(r1.left, r2.left) and isSameTree(r1.right, r2.right)

    queue = deque([root])
    while queue:
        node = queue.popleft()
        if node.val == subRoot.val and isSameTree(node, subRoot):
            return True
        if node.left: queue.append(node.left)
        if node.right: queue.append(node.right)
    return False
```

## Complexity
- Time: O(n × m)
- Space: O(n) for BFS queue + O(m) for isSameTree call stack

## Common mistake
Writing `if r1.val == r2.val: return True` instead of `if r1.val != r2.val: return False`. The former returns True after matching a single node without checking the full subtree.
