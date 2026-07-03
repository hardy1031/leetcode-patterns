# Analysis — 2. Add Two Numbers

## Layer 3 — Problem-solving Pattern
**Pattern:** Dummy Node
Same structure as 21 (Merge Two Sorted Lists) — traverse both lists simultaneously and build a new list node-by-node using a dummy head.

## Layer 2 — Algorithms & Techniques
- Parallel traversal with carry O(max(m,n)) time, O(max(m,n)) space
- **Insight:** Dummy node generalizes to list construction, not just deletion. Carry must be checked after the loop ends — if carry=1 remains, append one final node.

## Layer 1 — Data Structures
- Singly Linked List
- Dummy node (clean head for the result list)

## Solution

```python
def addTwoNumbers(l1, l2):
    dummy = ListNode(0)
    current = dummy
    carry = 0

    while l1 or l2 or carry:
        v1 = l1.val if l1 else 0
        v2 = l2.val if l2 else 0

        total = v1 + v2 + carry
        carry = total // 10
        current.next = ListNode(total % 10)
        current = current.next

        if l1: l1 = l1.next
        if l2: l2 = l2.next

    return dummy.next
```
