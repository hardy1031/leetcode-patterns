# Analysis — 203. Remove Linked List Elements

## Layer 3 — Problem-solving Pattern
**Pattern:** Dummy Node
Dummy node unifies deletion logic regardless of whether the target is at the head or in the middle.

## Layer 2 — Algorithms & Techniques
- Linear scan with conditional deletion O(n) time, O(1) space
- **Insight:** Do NOT advance current when a deletion happens — consecutive duplicates require re-checking the same position after each removal.

## Layer 1 — Data Structures
- Singly Linked List
- Dummy node (handles head deletion without special-casing)

## Solution

```python
def removeElements(head, val):
    dummy = ListNode(0, head)
    current = dummy
    while current.next:
        if current.next.val == val:
            current.next = current.next.next  # delete, don't advance
        else:
            current = current.next
    return dummy.next
```

## Common Mistake

Advancing `current` after every iteration causes consecutive matching nodes to be skipped:
```python
# WRONG
if current.next.val == val:
    current.next = current.next.next
current = current.next  # skips the new current.next
```
