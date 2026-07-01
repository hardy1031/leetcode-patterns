# Analysis — 61. Rotate List

## Layer 3 — Problem-solving Pattern
**Pattern:** Linked List Two Pointers (gap technique)
Same gap idea as 19, but the cut point is determined by length - k instead of n from end.

## Layer 2 — Algorithms & Techniques
- Find tail + length in one pass, then walk to new tail O(n) time, O(1) space
- **Insight:** Rotating right by k is equivalent to cutting at position (length - k) from the head. k % length handles k > length. dummy node does not help here since the new head is dynamic.

## Layer 1 — Data Structures
- Singly Linked List

## Solution

```python
def rotateRight(head, k):
    if not head:
        return head

    tail = head
    length = 1
    while tail.next:
        tail = tail.next
        length += 1

    k = k % length
    if k == 0:
        return head

    new_tail = head
    for _ in range(length - k - 1):
        new_tail = new_tail.next

    new_head = new_tail.next
    new_tail.next = None
    tail.next = head
    return new_head
```

## Why no dummy node

The new head changes position based on k, so a dummy node pointing to the original head provides no benefit. The `if not head` guard is still necessary.
