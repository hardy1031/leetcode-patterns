# Analysis: 206. Reverse Linked List

## Layer 3 — Problem-solving Pattern
**Pattern:** Linked List (Iterative Pointer Manipulation)
Traverse once, reversing each pointer in place.

## Layer 2 — Algorithms & Techniques
- Iterative pointer reversal O(n) time, O(1) space
- **Insight:** Three-pointer pattern — save next before cutting, then reverse the link. Order matters: save → reverse → advance. Never use recursive (O(n) call stack vs O(1) iterative).

## Layer 1 — Data Structures
- Three pointers: `prev`, `curr`, `next_node`

## Template (memorize the 4-step order)

```python
prev = None
curr = head

while curr:
    next_node = curr.next  # 1. save next
    curr.next = prev       # 2. reverse link
    prev = curr            # 3. advance prev
    curr = next_node       # 4. advance curr

return prev
```
