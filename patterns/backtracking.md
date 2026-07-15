# Backtracking Template

## Core Pseudocode

```
def backtrack(choices, current_state):
    if termination_condition:
        result.append(current_state.copy())
        return

    for choice in choices:
        current_state.append(choice)   # choose
        backtrack(next_choices, ...)   # explore
        current_state.pop()            # unchoose ← this is the backtrack
```

## The 3 things to define for any backtracking problem

| Concept | Question to ask | Example (Permutations) |
|---|---|---|
| `current_state` | What am I building up? | the permutation so far |
| `choices` | What can I pick from at this step? | remaining unused elements |
| `termination_condition` | When is current_state complete? | no elements left |

## Variants

### Binary-choice (no for loop) — Subsets
Each element has exactly 2 options: include or exclude.
```
backtrack(i):
    if i >= len(nums):
        record current_state
        return
    current_state.append(nums[i])
    backtrack(i + 1)             # include
    current_state.pop()
    backtrack(i + 1)             # exclude
```
choices = {include, exclude} → always 2, so no for loop needed.

### Forward-only for loop — Combination Sum
choices = elements from index i onward (no going back → no reordered duplicates).
```
for j in range(i, len(nums)):
    current_state.append(nums[j])
    backtrack(j, ...)            # j not j+1: same element can repeat
    current_state.pop()
```

### All-remaining for loop — Permutations
choices = all unused elements (order matters → must try every remaining element).
```
for choice in list(remaining_set):
    current_state.append(choice)
    remaining_set.remove(choice)
    backtrack(remaining_set)
    current_state.pop()
    remaining_set.add(choice)
```

## Choosing the right variant

| Order matters? | Elements reusable? | Variant |
|---|---|---|
| No | No | Binary-choice or forward-only |
| No | Yes | Forward-only (`range(i, ...)`, recurse with same i) |
| Yes | No | All-remaining (set) |
