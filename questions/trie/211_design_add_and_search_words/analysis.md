# 211. Design Add and Search Words Data Structure — Analysis

## Layer 3 — Problem-solving Pattern
**Pattern:** Trie + DFS/Backtracking
Standard Trie insert; search uses DFS to handle wildcard '.' by branching into all children.

## Layer 2 — Algorithms & Techniques
- Trie traversal O(m) for normal search, O(26^d * m) worst case with d dots
- **Insight:** DFS for wildcard — when '.' is encountered, fan out to all children with `if dfs(i+1, child): return True`; the iterative approach breaks down because you need to try multiple branches and backtrack on failure.

## Layer 1 — Data Structures
- TrieNode with `children: dict[str, TrieNode]` and `is_end: bool`
- Implicit call stack for DFS recursion
