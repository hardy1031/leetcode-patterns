# Analysis: 1456. Maximum Number of Vowels in a Substring of Given Length

## Layer 3 — Problem-solving Pattern
**Pattern:** Fixed-size Sliding Window
Window size is always k — slide one step at a time with a for loop.

## Layer 2 — Algorithms & Techniques
- Fixed-size sliding window O(n)
- **Insight:** Since window size is fixed, left = i - k always. No need to track left explicitly — just remove s[i-k] when i >= k. A for loop suffices; no inner while needed.

## Layer 1 — Data Structures
- Integer counter (no dict/Counter needed — just track vowel count)
- Set for O(1) vowel lookup

## Fixed-size template (no Counter needed for simple counts)
```python
cur = 0
for i in range(len(s)):
    if i - k >= 0 and s[i-k] in vowels:
        cur -= 1          # remove left
    if s[i] in vowels:
        cur += 1          # add right
    max_count = max(max_count, cur)
```
