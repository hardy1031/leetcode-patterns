# 211. Design Add and Search Words Data Structure

**Difficulty:** Medium

## Problem

Design a data structure that supports adding new words and searching for existing words.

Implement the `WordDictionary` class:
- `void addWord(word)` Adds word to the data structure.
- `bool search(word)` Returns true if there is any string in the data structure that matches word or false otherwise. word may contain dots '.' where dots can be matched with any letter.

## Example

```
Input:
["WordDictionary","addWord","addWord","addWord","search","search","search","search"]
[[],["day"],["bay"],["may"],["say"],["day"],[".ay"],["b.."]]

Output:
[null, null, null, null, false, true, true, true]
```

## Constraints
- `1 <= word.length <= 20`
- `word` in `addWord` consists of lowercase English letters.
- `word` in `search` consists of '.' or lowercase English letters.
- There will be at most 2 dots in word for search queries.
- At most 10,000 calls will be made to `addWord` and `search`.

## Links
- [LeetCode](https://leetcode.com/problems/design-add-and-search-words-data-structure/)
- [NeetCode](https://neetcode.io/problems/design-word-search-data-structure)
