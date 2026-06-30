# Analysis — 19. Remove Nth Node From End of List

## Layer 3 — Problem-solving Pattern
**Pattern:** Linked List Two Pointers (gap technique)
Fix a gap of n between fast and slow. When fast reaches the end, slow is at the node just before the target.

## Layer 2 — Algorithms & Techniques
- Two Pointers with fixed gap O(n) time, O(1) space
- **Insight:** "nth from end" has no direct index in a linked list. Moving fast n steps ahead creates a gap so that when fast hits the tail, slow lands exactly one node before the deletion target — enabling single-pass removal.

## Layer 1 — Data Structures
- Singly Linked List
- Dummy node (handles edge case where head itself is removed, i.e. n == sz)

## Solution

```python
def removeNthFromEnd(head, n):
    dummy = ListNode(0, head)
    fast = dummy
    slow = dummy

    for _ in range(n):
        fast = fast.next

    while fast.next:
        fast = fast.next
        slow = slow.next

    slow.next = slow.next.next
    return dummy.next
```

## Why dummy node

When n == sz (remove the head), slow would need to point to a node before head. The dummy node provides that anchor without special-casing.
