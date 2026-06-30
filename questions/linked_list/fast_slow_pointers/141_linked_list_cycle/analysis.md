# Analysis — 141. Linked List Cycle

## Layer 3 — Problem-solving Pattern
**Pattern:** Fast & Slow Pointers (Floyd's Cycle Detection)
サイクルがあれば必ずfastがslowに追いつく。

## Layer 2 — Algorithms & Techniques
- Floyd's Cycle Detection O(n) time, O(1) space
- **Insight:** fastが2ステップ、slowが1ステップ進むと、サイクル内で相対速度1で近づくため必ず衝突する。サイクルがなければfastがNoneに達して終了。

## Layer 1 — Data Structures
- Singly Linked List

## Solution

```python
def hasCycle(head):
    slow, fast = head, head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```
