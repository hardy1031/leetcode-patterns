# Analysis: 49. Group Anagrams

## Layer 3 — Problem-solving Pattern
**Pattern:** Hash Map (grouping by canonical key)
Sort each string → use sorted string as key → group originals by key.

## Layer 2 — Algorithms & Techniques
- Sorting each string: O(k log k) per string, total O(n·k log k)
- Alternative: character count tuple as key → O(n·k)

## Layer 1 — Data Structures
- Array of strings (input)
- Hash Map (key: sorted string or char count tuple, value: list of anagrams)
