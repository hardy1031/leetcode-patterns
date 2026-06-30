# Analysis — 876. Middle of the Linked List

## Layer 3 — Problem-solving Pattern
**Pattern:** Fast & Slow Pointers
Fast moves 2x speed of slow. When fast reaches the end, slow is at the middle.

## Layer 2 — Algorithms & Techniques
- Fast & Slow Pointers O(n) time, O(1) space
- **Insight:** Fast/slow is the standard template for finding the middle of a linked list without an index. Both start at head — for even-length lists this returns the second middle, which is the correct behavior for this problem and for splitting a list in half (143).

## Layer 1 — Data Structures
- Singly Linked List

## Solution

```python
def middleNode(head):
    slow, fast = head, head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow
```

## Notes

- `fast=head` (not `head.next`) returns the second middle for even-length lists.
- This template is reused as Step 1 in 143 (Reorder List).
