# LeetCode Project

Pattern-based learning repo for coding interview prep.

## Philosophy

3 abstraction layers — study Layer 3 patterns first, that's where interview ROI is highest:

- **Layer 3 (Pattern):** Two Pointers, Sliding Window, Hash Map, Binary Search, BFS/DFS, Backtracking, DP, Heap, Topological Sort, Union Find, Trie, Monotonic Stack, Greedy, Prefix Sums
- **Layer 2 (Algorithm):** Binary search impl, Kadane's, Dijkstra, Topological sort, GCD, etc.
- **Layer 1 (Data Structure):** Array, HashMap, Heap, Tree, Graph, Trie, etc.

Approach: solve 5–10 problems of the same pattern in a row. Brain generalizes faster.

## Language

All content in this repo must be written in English — diary entries, analysis files, personal notes, and LLM-generated text. The user may speak to the LLM in any language, but all file output must be in English.

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

**Tier 1 (essential):** two_pointers (sliding_window, opposite_direction, fast_slow), hash_map, binary_search (on_array, on_answer_space), bfs_dfs, backtracking
**Tier 2:** dynamic_programming, heap_priority_queue, topological_sort, union_find, trie
**Tier 3:** monotonic_stack, bit_manipulation, greedy, prefix_sums, math
**Linked List patterns:** dummy_node, in_place_reversal, fast_slow_pointers, two_pointers

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
- `stack/` → basic, monotonic (subcategorized early because the thinking is fundamentally different — basic uses stack for LIFO order, monotonic uses stack to resolve "next greater/smaller" queries in O(n))
- `sliding_window/` → fixed_size, variable_size (subcategorized early because fixed_size windows don't need shrink logic — window size is always len(s1); variable_size windows grow and shrink based on a condition)
- `linked_list/` → in_place_reversal, dummy_node, fast_slow_pointers, two_pointers (subcategorized early because each sub-pattern uses fundamentally different pointer mechanics)

**Candidates for future subcategorization:**
- `dynamic_programming/` → 1D, 2D, interval, knapsack (DP sub-patterns differ enough to warrant early split)
- `bfs_dfs/` → bfs, dfs, topological (when problems accumulate)
- `binary_search/` → on_array, on_answer_space (when problems accumulate)
- `backtracking/` → permutations, combinations, subsets (when problems accumulate)

## Study Style

The user follows NeetCode's roadmap, so the **broad topic** (e.g. "two pointers", "stack") is decided before each session.

Within that topic, **fine-grained themes are NOT pre-decided** — they emerge organically:
1. Solve a few problems or do spaced review within the topic
2. Notice something unclear or generalizable mid-session (a subtle technique, a comparison, a "why does this work?")
3. Focus on that micro-theme — search LeetCode for similar problems, drill it, solidify it

Examples of micro-themes that have emerged:
- "When should a sliding window slide?" (from 76, 424 — within the two pointers topic)
- "3-pointer vs 2-pointer: sort costs O(n log n) but doesn't matter at O(n²)" (from 15, 16)
- "HashMap vs Set: when do you need the value?" (from 15)
- "exact match vs closest: what determines whether HashMap gives O(n)?" (from 1, 16)

The LLM should recognize when a micro-theme is forming and surface it explicitly.

## Daily Diary

File location: `diary/YYYY-MM-DD.md`

When the LLM detects that a study theme has emerged (a concept the user is drilling across multiple problems), write or append it to today's diary file automatically — without being asked.

Diary entry format:
```
## Theme: {theme title}

{2–3 sentences on what the theme is and what triggered it}

### Key insight
{the transferable principle in one sentence}

### Problems covered
- {number}. {title}
```

Create the diary file if it doesn't exist. One file per day. Append new themes if the file already exists.

At the start or end of each diary file, always include a **Problems Solved** section listing every problem solved that day:

```
## Problems Solved
- {number}. {title} ({difficulty}) — {pattern}
```

## Daily Reflection (End of Session)

At the end of each session, the user writes a reflection in English. The LLM proofreads the English and saves it to today's diary file.

Rules:
- The user writes the reflection — the LLM does NOT write it
- The LLM corrects grammar and unnatural phrasing, but preserves the user's voice and content
- Show the corrected version to the user before saving, so they can confirm
- Append to the existing diary file under a `## Reflection` section
- This is mandatory every session — if the session is ending without a reflection, remind the user

Reflection format:
```
## Reflection

{user's text, lightly corrected}
```

## Pattern Templates

File location: `patterns/{pattern_name}.md`

A pattern template is a language-agnostic pseudocode skeleton that captures the reusable structure of a Layer 3 pattern. Templates are built up incrementally as the user solves problems — not created upfront.

### When to create or update a template
- When the user explicitly asks to add a template
- When a new sub-variant emerges that doesn't fit the existing template

### Template format
```
# {Pattern Name} Template

## Pseudocode

def approach(inputs):
    # setup

    def helper(...):
        if termination_condition:
            record result
            return

        for/two-branch logic:
            choose
            explore
            unchoose

    helper(initial_state)
    return result

## Variants
- {variant name}: {one-line difference}

## When to use
- {trigger condition}
```

### LLM instructions
- Do NOT create a template file unless the user asks
- When asked, create `patterns/{pattern_name}.md` and note it in the Existing templates list below
- Update the Variants section as new sub-patterns emerge

**Existing templates:**
- `patterns/backtracking.md`

## LLM Instructions

- Do NOT write code or fill in personal_note.md unless explicitly asked
- When creating a new problem folder, create all 4 files and update index.md
- When updating needs_review to false, update both review_history.md and index.md
- When generating a weekly review, create a new file in spaced_review/ — do not overwrite existing ones
- When a study theme emerges mid-session, write it to `diary/YYYY-MM-DD.md` automatically
