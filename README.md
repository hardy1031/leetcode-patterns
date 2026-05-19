# leetcode-patterns

A pattern-driven LeetCode study repository for efficient coding interview preparation.

## Philosophy

Instead of solving problems randomly, this repo groups problems by **Layer 3 patterns** — the high-level problem-solving strategies that interviewers actually test:

> Solve 5–10 problems of the same pattern in a row. Your brain generalizes faster.

### The 3 Layers

| Layer | Focus | Examples |
|-------|-------|---------|
| **Layer 3 (Pattern)** | Problem-solving strategy | Two Pointers, Sliding Window, Hash Map, BFS/DFS, Backtracking, DP |
| **Layer 2 (Algorithm)** | Concrete technique | Binary search impl, Kadane's, Dijkstra, GCD |
| **Layer 1 (Data Structure)** | Underlying structure | Array, HashMap, Heap, Tree, Graph |

Study Layer 3 first — that's where interview ROI is highest.

## Structure

```
questions/
└── {pattern}/                      # e.g. hash_map/, two_pointers_sliding_window/
    └── {number}_{problem}/
        ├── question.md             # Problem statement
        ├── analysis.md             # Layer 1/2/3 breakdown
        ├── personal_note.md        # Personal insights (gitignored)
        └── review_history.md       # Study dates + needs_review flag
spaced_review/
└── week_NN_YYYY-MM-DD.md           # Weekly review quizzes
```

## Spaced Review

Each problem tracks review history in `review_history.md`:

```
needs_review: true

## History
- May 18, 2026   # first study
- May 25, 2026   # reviewed
```

Problems marked `needs_review: true` are prioritized in weekly review quizzes, which quiz you on the pattern, algorithm, and data structure — not just the solution.

## Pattern Tiers

| Tier | Patterns |
|------|---------|
| **1 (Essential)** | two_pointers_sliding_window, hash_map, binary_search, bfs_dfs, backtracking |
| **2** | dynamic_programming, heap_priority_queue, topological_sort, union_find, trie |
| **3** | monotonic_stack, bit_manipulation, greedy, prefix_sums, math |
