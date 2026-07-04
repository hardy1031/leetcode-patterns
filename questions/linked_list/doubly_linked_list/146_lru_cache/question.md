# 146. LRU Cache

**Difficulty:** Medium
**Pattern:** linked_list/doubly_linked_list
**LeetCode:** https://leetcode.com/problems/lru-cache/
**NeetCode:** https://neetcode.io/problems/lru-cache

## Problem

Implement the `LRUCache` class:

- `LRUCache(int capacity)` — Initialize the LRU cache with positive size `capacity`.
- `int get(int key)` — Return the value if the key exists, otherwise return `-1`.
- `void put(int key, int value)` — Update the value if the key exists. Otherwise, add the key-value pair. If capacity is exceeded, evict the least recently used key.

Both `get` and `put` must run in **O(1)** average time complexity.

## Example

```
Input:
["LRUCache", [2], "put", [1,10], "get", [1], "put", [2,20], "put", [3,30], "get", [2], "get", [1]]

Output:
[null, null, 10, null, null, 20, -1]

Explanation:
LRUCache(2)     → capacity = 2
put(1, 10)      → cache: {1=10}
get(1)          → 10
put(2, 20)      → cache: {1=10, 2=20}
put(3, 30)      → evict key=1 (LRU), cache: {2=20, 3=30}
get(2)          → 20
get(1)          → -1 (evicted)
```

## Constraints

- `1 <= capacity <= 100`
- `0 <= key <= 1000`
- `0 <= value <= 1000`
- At most `2 * 10^5` calls to `get` and `put`
