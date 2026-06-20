## Layer 3 — Problem-solving Pattern
**Pattern:** Stack
演算子が来たとき「直前の2つのオペランド」が必要。直前 = LIFOなのでStackが自然。

## Layer 2 — Algorithms & Techniques
- Stack push/pop: O(n)
- **Insight:** 数値はpush、演算子が来たら2つpopして計算してpushし直す。最後にstackに残った1つが答え。

## Layer 1 — Data Structures
- Stack（Pythonでは `list`）
