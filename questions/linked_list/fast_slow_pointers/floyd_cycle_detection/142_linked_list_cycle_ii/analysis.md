# Analysis — 142. Linked List Cycle II

## Layer 3 — Problem-solving Pattern
**Pattern:** Floyd's Cycle Detection
141 detects whether a cycle exists. 142 finds WHERE the cycle begins.

## Layer 2 — Algorithms & Techniques
- Floyd's Cycle Detection + second pointer from head O(n) time, O(1) space
- **Insight:** After slow and fast meet, a second pointer starting from head will meet slow exactly at the cycle entrance. This is proven by F = C - h (see proof below).

## Layer 1 — Data Structures
- Singly Linked List

## Solution

```python
def detectCycle(head):
    slow, fast = head, head

    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            break
    else:
        return None  # no cycle

    slow2 = head
    while slow != slow2:
        slow = slow.next
        slow2 = slow2.next
    return slow
```

## Why slow2 from head meets slow at the cycle entrance

```
Variables:
  F = distance from head to cycle entrance
  h = distance from entrance to meeting point
  C = cycle length

slow traveled:  F + h
fast traveled:  F + h + C  (one extra loop)
fast = 2 × slow:
  2(F + h) = F + h + C
  F = C - h

After the meeting point:
  slow needs C - h = F more steps to reach the entrance
  slow2 starts from head, needs F steps to reach the entrance
  → they meet at the cycle entrance
```
