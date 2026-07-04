# Analysis — 146. LRU Cache

## Layer 3 — Problem-solving Pattern
**Pattern:** Doubly Linked List + HashMap
The constraint is O(1) for both get and put. A HashMap gives O(1) lookup, but you also need O(1) reordering by recency — that requires a doubly linked list so any node can be removed and reinserted in O(1).

## Layer 2 — Algorithms & Techniques
- HashMap (key → Node): O(1) lookup
- Doubly Linked List (ordered by recency): O(1) remove and insert
- **Insight:** Singly linked list is not enough — `remove(node)` needs `node.prev`, which only a doubly linked list provides. The combination of HashMap + doubly linked list is the canonical O(1) LRU pattern.

## Layer 1 — Data Structures
- `dict` (HashMap): key → Node reference
- Doubly Linked List with sentinel nodes (left = LRU end, right = MRU end)

## Implementation

```python
class Node:
    def __init__(self, key, val):
        self.key = key
        self.val = val
        self.prev = self.nxt = None

class LRUCache:
    def __init__(self, capacity):
        self.capacity = capacity
        self.left, self.right = Node(0, 0), Node(0, 0)
        self.left.nxt = self.right
        self.right.prev = self.left
        self.cache = {}

    def insert(self, node):           # always insert at MRU end (before right)
        self.right.prev.nxt = node
        node.prev = self.right.prev
        node.nxt = self.right
        self.right.prev = node

    def remove(self, node):
        node.prev.nxt = node.nxt
        node.nxt.prev = node.prev

    def get(self, key):
        if key in self.cache:
            self.remove(self.cache[key])
            self.insert(self.cache[key])
            return self.cache[key].val
        return -1

    def put(self, key, value):
        if key in self.cache:
            self.remove(self.cache[key])
        self.cache[key] = Node(key, value)
        self.insert(self.cache[key])
        if len(self.cache) > self.capacity:
            lru = self.left.nxt
            self.remove(lru)
            del self.cache[lru.key]
```

## Complexity
- Time: O(1) for both `get` and `put`
- Space: O(capacity)

## Sentinel nodes
`left` and `right` are dummy boundary nodes with no real data. They eliminate edge cases (empty list, insert at boundary) by ensuring `right.prev` and `left.nxt` always point to a valid node.
This is the doubly linked list equivalent of the dummy head node used in singly linked list problems.
