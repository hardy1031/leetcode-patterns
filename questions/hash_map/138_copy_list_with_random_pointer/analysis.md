# Analysis — 138. Copy List with Random Pointer

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map
Map each original node to its copy so that random pointer targets can be resolved in O(1).

## Layer 2 — Algorithms & Techniques
- Two-pass hash map O(n) time, O(n) space
- **Insight:** random pointers can point anywhere, so you can't wire them up during node creation — you need all copies to exist first. Hash map gives O(1) lookup of "what is the copy of this node?"

## Layer 1 — Data Structures
- Hash Map {original node → copy node}
- Linked List (with random pointer)

## Solution

```python
def copyRandomList(head):
    if not head:
        return None

    node_map = {}

    # Pass 1: create all copy nodes
    current = head
    while current:
        node_map[current] = Node(current.val)
        current = current.next

    # Pass 2: wire next and random
    current = head
    while current:
        node_map[current].next = node_map.get(current.next)
        node_map[current].random = node_map.get(current.random)
        current = current.next

    return node_map[head]
```

## Why no dummy node

Dummy node solves "head might be deleted/modified" edge cases. Here, the head is never modified — `if not head: return None` handles the empty input. These are different kinds of edge cases.

## Dummy node decision guide

| Use dummy node | Skip dummy node |
|---|---|
| Head itself might be deleted (203, 82) | New head is computed dynamically (61) |
| Insertion before head is needed (21) | Problem is not about head modification (138, 876) |
| n == sz removes the head (19) | Empty input handled by simple guard |
