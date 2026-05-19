# leetcode-patterns

A pattern-driven LeetCode study repository designed around an **AI-assisted learning workflow**.

## AI-Assisted Workflow

This repo is built with the assumption that an AI (Claude) is a collaborator in every study session — not just a hint machine, but an active part of how problems are analyzed, reviewed, and retained.

**Why:** AI can explain *why* a pattern applies, generate targeted review quizzes, and give instant feedback on reasoning — things that static resources can't do. The repo structure is designed to make that collaboration as frictionless as possible.

**Key files for AI context:**

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Instructs the AI on repo structure, conventions, and how to behave (e.g. don't fill in `personal_note.md` unless asked) |
| `questions/index.md` | Master index of all problems — AI reads this first to understand what's been studied and what needs review |
| `analysis.md` (per problem) | Layer 1/2/3 breakdown the AI uses to generate quiz questions |
| `review_history.md` (per problem) | `needs_review` flag the AI uses to prioritize spaced review |

**Typical session:**
1. Solve a problem, discuss the pattern with AI
2. AI helps write `analysis.md` (Layer 1/2/3 breakdown)
3. Each week, ask AI to generate a spaced review quiz from `questions/index.md`

---

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
