# AGENTS.md

Instructions for AI agents (Claude, Codex, etc.) working in this repo.

## What this repo is

A pattern-driven LeetCode study repo. Problems are organized by Layer 3 pattern (Two Pointers, Stack, Hash Map, etc.). The primary workflow is: solve problems, write analysis, do weekly spaced review.

## Files to read first

| File | Why |
|------|-----|
| `CLAUDE.md` | Full repo rules, folder structure, study style, diary instructions |
| `questions/index.md` | Master index of all problems — read before adding a problem or generating a review |

## Folder structure

```
questions/
└── {pattern}/                        # e.g. stack/, two_pointers/sliding_window/
    └── {number}_{problem_name}/
        ├── question.md               # Problem statement + links
        ├── analysis.md               # Layer 3 / Layer 2 / Layer 1 breakdown
        ├── personal_note.md          # Personal insights — human writes this
        └── review_history.md         # needs_review flag + study dates
spaced_review/
└── week_NN_YYYY-MM-DD.md             # Weekly quiz files (LLM-generated)
diary/
└── YYYY-MM-DD.md                     # Daily study themes (LLM writes when theme emerges)
```

## Rules

- Do NOT write code unless explicitly asked
- Do NOT fill in `personal_note.md` unless explicitly asked
- When adding a problem: create all 4 files + add a row to `questions/index.md`
- When updating `needs_review` to false: update both `review_history.md` and `questions/index.md`
- When generating a weekly review: create a new file in `spaced_review/` — never overwrite existing ones
- When a study theme emerges mid-session: write it to `diary/YYYY-MM-DD.md` automatically

## analysis.md format

```
## Layer 3 — Problem-solving Pattern
**Pattern:** {pattern name}
{one-line explanation of why this pattern applies}

## Layer 2 — Algorithms & Techniques
- {algorithm name}: {complexity}
- **Insight:** {the key idea in one sentence}

## Layer 1 — Data Structures
- {data structure}
```

## review_history.md format

```
needs_review: true

## History
- June 19, 2026
```

## questions/index.md row format

```
| {#} | {Problem Name} | {pattern/subfolder} | {Easy/Medium/Hard} | {true/false} | {Month DD, YYYY} |
```
