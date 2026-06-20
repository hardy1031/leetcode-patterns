# leetcode-patterns

A pattern-driven LeetCode study repository designed around an **AI-assisted learning workflow**.

## AI-Assisted Workflow

This repo is built with the assumption that an AI (Claude) is a collaborator in every study session — not just a hint machine, but an active part of how problems are analyzed, reviewed, and retained.

**Why:** AI can explain *why* a pattern applies, generate targeted review quizzes, and give instant feedback on reasoning — things that static resources can't do. The repo structure is designed to make that collaboration as frictionless as possible.

**Key files for AI context:**

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Instructs the AI on repo structure, conventions, and how to behave |
| `AGENTS.md` | Concise rules for AI agents — read alongside CLAUDE.md |
| `questions/index.md` | Master index of all problems — AI reads this first |
| `analysis.md` (per problem) | Layer 1/2/3 breakdown the AI uses to generate quiz questions |
| `review_history.md` (per problem) | `needs_review` flag the AI uses to prioritize spaced review |

**Typical session:**
1. Solve a problem, discuss the pattern with AI
2. AI helps write `analysis.md` (Layer 1/2/3 breakdown)
3. AI writes to `diary/YYYY-MM-DD.md` when a study theme emerges
4. Each week, ask AI to generate a spaced review quiz from `questions/index.md`

---

## Philosophy

Instead of solving problems randomly, this repo groups problems by **Layer 3 patterns** — the high-level problem-solving strategies that interviewers actually test:

> Solve 5–10 problems of the same pattern in a row. Your brain generalizes faster.

### The 3 Layers

| Layer | Focus | Examples |
|-------|-------|---------|
| **Layer 3 (Pattern)** | Problem-solving strategy | Two Pointers, Sliding Window, Stack, Hash Map, BFS/DFS, DP |
| **Layer 2 (Algorithm)** | Concrete technique | Binary search, Kadane's, Dijkstra, GCD |
| **Layer 1 (Data Structure)** | Underlying structure | Array, HashMap, Heap, Tree, Graph |

Study Layer 3 first — that's where interview ROI is highest.

## Structure

```
questions/
└── {pattern}/                        # e.g. stack/, hash_table/
    └── two_pointers/                 # subcategorized when 5+ problems with distinct sub-patterns
        ├── sliding_window/
        ├── opposite_direction/
        └── fast_slow/
    └── {number}_{problem}/
        ├── question.md               # Problem statement
        ├── analysis.md               # Layer 1/2/3 breakdown
        ├── personal_note.md          # Personal insights
        └── review_history.md         # Study dates + needs_review flag
spaced_review/
└── week_NN_YYYY-MM-DD.md             # Weekly review quizzes
diary/
└── YYYY-MM-DD.md                     # Daily study themes (auto-written by AI)
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
| **1 (Essential)** | two_pointers (sliding_window, opposite_direction, fast_slow), hash_table, binary_search, bfs_dfs, backtracking, stack |
| **2** | dynamic_programming, heap_priority_queue, topological_sort, union_find, trie |
| **3** | monotonic_stack, bit_manipulation, greedy, prefix_sums, math |
