## Layer 3 — Problem-solving Pattern
**Pattern:** Two Pointers (Opposite Direction)
低い方のbarがボトルネック。高い方を動かしても面積は改善しないので、常に低い方を動かす。

## Layer 2 — Algorithms & Techniques
- Two pointers opposite direction O(n)
- area = (right - left) * min(height[left], height[right])
- 移動判断: height[left] < height[right] → left++、それ以外 → right--

## Layer 1 — Data Structures
- Array
