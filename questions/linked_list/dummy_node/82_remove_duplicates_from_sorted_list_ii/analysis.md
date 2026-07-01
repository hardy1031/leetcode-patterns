# Analysis — 82. Remove Duplicates from Sorted List II

## Layer 3 — Problem-solving Pattern
**Pattern:** Dummy Node
Like 203, but the update logic branches on whether a duplicate was detected — prev only advances when the current node is confirmed unique.

## Layer 2 — Algorithms & Techniques
- Linear scan with conditional deletion O(n) time, O(1) space
- **Insight:** Split into two cases: (1) duplicate detected — skip all nodes with that value, set prev.next = current.next, do NOT advance prev; (2) no duplicate — safely advance prev. Mixing both cases into one update path causes the last duplicate to survive.

## Layer 1 — Data Structures
- Singly Linked List
- Dummy node (head itself may be a duplicate)

## Solution

```python
def deleteDuplicates(head):
    dummy = ListNode(0, head)
    prev = dummy
    current = head

    while current:
        if current.next and current.val == current.next.val:
            # skip all nodes with this value
            while current.next and current.val == current.next.val:
                current = current.next
            prev.next = current.next
            current = prev.next
        else:
            prev = current
            current = current.next

    return dummy.next
```

## Comparison with 203

| | 203 | 82 |
|---|---|---|
| What to remove | nodes matching a given val | all nodes with any duplicate val |
| prev advances | always (unless deleted) | only when no duplicate detected |
