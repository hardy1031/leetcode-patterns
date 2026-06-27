# Analysis: 21. Merge Two Sorted Lists

## Layer 3 — Problem-solving Pattern
**Pattern:** Linked List — Dummy Node Builder
Building a new linked list by selecting nodes from existing lists. Dummy node avoids special-casing the head.

## Layer 2 — Algorithms & Techniques
- Dummy node + two-pointer merge O(n+m) time, O(1) space
- **Insight:** Dummy node lets you start appending before the final head is known — `dummy.next` becomes the answer. Remaining nodes attach in one line (`curr.next = list1 or list2`) since both lists are already sorted.

## Layer 1 — Data Structures
- Dummy node (sentinel)
- `curr` pointer to track tail of built list

## Template

```python
dummy = ListNode(0)
curr = dummy

while list1 and list2:
    if list1.val <= list2.val:
        curr.next = list1
        list1 = list1.next
    else:
        curr.next = list2
        list2 = list2.next
    curr = curr.next

curr.next = list1 or list2  # attach remainder

return dummy.next
```

## Pattern distinction

| Pattern | Use when |
|---------|---------|
| 3-pointer reversal (206) | Modifying an existing list in place |
| Dummy node builder (21) | Assembling a new list from existing nodes |
