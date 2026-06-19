## Layer 3 — Problem-solving Pattern
**Pattern:** Two Pointers (Opposite Direction)
3Sumと同じく、sortしてanchor + left/rightの構造。「一致」ではなく「最小距離」を追う。

## Layer 2 — Algorithms & Techniques
- Sort + Two Pointers: O(n²)
- **Insight:** 3Sumの変種 — `sum == target` の代わりに `abs(sum - target)` の最小値を記録し続ける。`current_sum > target` / `< target` でポインタを動かすロジックは全く同じ。

## Layer 1 — Data Structures
- Array（sorted）
- 単一変数 `closest_sum`（最小距離を持つsumを保持）
