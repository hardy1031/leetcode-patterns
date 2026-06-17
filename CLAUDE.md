# LeetCode Project

Pattern-based learning repo for coding interview prep.

## Philosophy

3 abstraction layers — study Layer 3 patterns first, that's where interview ROI is highest:

- **Layer 3 (Pattern):** Two Pointers, Sliding Window, Hash Map, Binary Search, BFS/DFS, Backtracking, DP, Heap, Topological Sort, Union Find, Trie, Monotonic Stack, Greedy, Prefix Sums
- **Layer 2 (Algorithm):** Binary search impl, Kadane's, Dijkstra, Topological sort, GCD, etc.
- **Layer 1 (Data Structure):** Array, HashMap, Heap, Tree, Graph, Trie, etc.

Approach: solve 5–10 problems of the same pattern in a row. Brain generalizes faster.

## Folder Structure

```
LeetCode/
├── CLAUDE.md
├── questions/
│   ├── index.md                        # Master index — read this first
│   └── two_pointers/                   # two pointers family
│       ├── sliding_window/             # e.g. 3, 567
│       ├── opposite_direction/         # e.g. Two Sum sorted, Valid Palindrome
│       └── fast_slow/                  # e.g. Linked List Cycle
│   └── {pattern_name}/                 # other Layer 3 patterns (e.g. hash_map)
│       └── {number}_{problem_name}/
│           ├── question.md             # Problem statement + links
│           ├── analysis.md             # Layer 1/2/3 breakdown
│           ├── personal_note.md        # Personal insights
│           └── review_history.md       # Study dates + needs_review flag
└── spaced_review/
    └── week_NN_YYYY-MM-DD.md           # Weekly review quizzes (LLM-generated)
```

## Pattern Tiers (priority order)

**Tier 1 (essential):** two_pointers (sliding_window, opposite_direction, fast_slow), hash_map, binary_search, bfs_dfs, backtracking
**Tier 2:** dynamic_programming, heap_priority_queue, topological_sort, union_find, trie
**Tier 3:** monotonic_stack, bit_manipulation, greedy, prefix_sums, math

## Rules

### Adding a new problem
1. Identify the primary Layer 3 pattern → use that as the folder name
2. Create 
3. Create the 4 files below
4. Add a row to 

### question.md
- Problem title, description, examples, constraints
- Links to LeetCode and NeetCode

### analysis.md
Template:
```
## Layer 3 — Problem-solving Pattern
**Pattern:** {pattern name}
{one-line explanation of why this pattern applies}

## Layer 2 — Algorithms & Techniques
- {algorithm name} {complexity}
- **Insight:** {why this algorithm/combination works here — e.g. "DP + greedy: dp[i] depends only on dp[i-1] so collapse to one variable", "binary search on answer space not index", "two-pass greedy"}

## Layer 1 — Data Structures
- {data structure}
```

**Insight is mandatory.** Name the key algorithmic idea or combination in one sentence (e.g. "DP + greedy", "monotonic stack for next greater element", "sliding window with freq map"). This is the transferable pattern to recall at interview time.

### personal_note.md
- Critical insights only, extremely concise
- Written by human; LLM does not fill this in unless asked

### review_history.md
```
needs_review: true   # set to false when fully mastered (ask LLM to update)

## History
- May 18, 2026       # first study date
- May 25, 2026       # review dates appended here
```

### questions/index.md
- One row per problem
- Always keep  and 
wtmp begins Tue 27 Jan 2026 17:15:20 PST columns in sync with 
- LLM reads this file first when generating spaced reviews

## Spaced Review (Weekly)

Ask: "今週のreviewを作って"

LLM will:
1. Read 
2. Prioritize  problems
3. Read each problem's 
4. Generate a quiz file at 

Quiz format per problem:
- Problem title + link
- "What is the Layer 3 pattern? Layer 2 technique? Layer 1 data structure?"
- Link for problems worth coding immediately

## Folder Subcategorization Policy

Subcategorize a pattern folder only when:
- There are 5+ problems in the folder, AND
- Problems clearly fall into distinct sub-patterns that are easy to confuse

**Already subcategorized:**
- `two_pointers/` → sliding_window, opposite_direction, fast_slow (subcategorized early because the 3 sub-patterns are fundamentally different)

**Candidates for future subcategorization:**
- `dynamic_programming/` → 1D, 2D, interval, knapsack (DP sub-patterns differ enough to warrant early split)
- `bfs_dfs/` → bfs, dfs, topological (when problems accumulate)
- `binary_search/` → on_array, on_answer_space (when problems accumulate)
- `backtracking/` → permutations, combinations, subsets (when problems accumulate)

## LLM Instructions

- Do NOT write code or fill in personal_note.md unless explicitly asked
- When creating a new problem folder, create all 4 files and update index.md
- When updating needs_review to false, update both review_history.md and index.md
- When generating a weekly review, create a new file in spaced_review/ — do not overwrite existing ones
