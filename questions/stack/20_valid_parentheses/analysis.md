## Layer 3 — Problem-solving Pattern
**Pattern:** Stack
閉じ括弧が来たとき「直前に開いた括弧」と対応しているか確認する必要がある。直前 = LIFOなのでStackが自然。

## Layer 2 — Algorithms & Techniques
- Stack push/pop: O(n)
- **Insight:** 開き括弧をpush、閉じ括弧が来たらstackのtopと対応するか確認してpop。最後にstackが空なら有効。

## Layer 1 — Data Structures
- Stack（Pythonでは `list` で代用、`append` / `pop`）
- HashMap（閉じ括弧 → 対応する開き括弧のマッピング）
