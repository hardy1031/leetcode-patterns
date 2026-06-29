# Analysis — 92. Reverse Linked List II

## Layer 3 — Problem-solving Pattern
**Pattern:** In-Place Reversal (Linked List)
206（全体リバース）の部分適用。区間を切り出してリバースし、前後を再接続する。

## Layer 2 — Algorithms & Techniques
- 3-pointer reversal (prev / curr / next) O(n)
- **Insight:** 92 = 206の基本リバース + 「leftまで歩く」 + 「再接続」の3ステップ。基本リバースのコードは206と全く同じ。

## Layer 1 — Data Structures
- Singly Linked List
- Dummy node（left=1のエッジケースを統一処理）

## Solution

```python
def reverseBetween(head, left, right):
    dummy = ListNode(0, head)
    left_prev = dummy
    curr = head
    count = 0

    # Step 1: leftまで歩く
    while count < left - 1:
        count += 1
        left_prev = curr
        curr = curr.next

    # Step 2: 206と同じ3-pointer reversal
    prev = None
    while count < right:
        count += 1
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node

    # Step 3: 再接続
    left_prev.next.next = curr   # 旧leftノードをright+1に繋ぐ
    left_prev.next = prev        # left_prevをrightノードに繋ぐ

    return dummy.next
```

## Reconnection Logic

```
リバース前: ... -> left_prev -> [left -> ... -> right] -> right+1 -> ...
リバース後: prev=right, curr=right+1, left_prev.next=left(まだ変更前)

left_prev.next.next = curr   →  left.next = right+1
left_prev.next = prev        →  left_prev.next = right
```
