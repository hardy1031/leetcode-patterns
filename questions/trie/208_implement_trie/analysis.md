# 208. Implement Trie (Prefix Tree) — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Trie
Each inserted word shares prefixes with others by walking a tree of single characters from root. `search` and `startsWith` differ only in whether the final node must have `is_end=True`.

## Layer 2 — Algorithms & Techniques
- Trie traversal O(m) per operation, where m = word length
- **Insight:** The char lives in the dict key, not in the node — each node only needs `children: dict[str, TrieNode]` and `is_end: bool`; the parent's key already encodes what character this node represents.

## Layer 1 — Data Structures
- TrieNode with `children` dict and `is_end` boolean
- Tree (26-ary at most, not binary)
