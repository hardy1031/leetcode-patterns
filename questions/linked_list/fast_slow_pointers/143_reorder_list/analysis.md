# Analysis — 143. Reorder List

## Layer 3 — Problem-solving Pattern
**Pattern:** Fast & Slow Pointers + In-Place Reversal + Merge
3つのlinked listパターンの合わせ技。

## Layer 2 — Algorithms & Techniques
- Fast & Slow Pointers（中間点を見つける）O(n)
- In-Place Reversal（後半をリバース）O(n)
- Alternating Merge（2リストを交互にマージ）O(n)
- **Insight:** indexがないlinked listの「真ん中」はfast/slowで O(n)で見つける。後半をリバースしてから交互マージすることで、前から後ろへの1方向操作に変換できる。

## Layer 1 — Data Structures
- Singly Linked List

## Solution

```python
def reorderList(head):
    # Step 1: 中間点を見つける（fast/slow）
    slow, fast = head, head.next
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next

    # Step 2: 後半をリバース
    second = slow.next
    slow.next = None  # 前半と後半を切り離す
    prev = None
    while second:
        tmp = second.next
        second.next = prev
        prev = second
        second = tmp

    # Step 3: 交互マージ（tempポインタが必要）
    first, second = head, prev
    while second:
        tmp1, tmp2 = first.next, second.next
        first.next = second
        second.next = tmp1
        first = tmp1
        second = tmp2
```

## Step 3 の注意点

マージ時に`first.next`と`second.next`を先に保存しないと、ポインタを繋ぎ替えた後に次のノードを失う。
