# Analysis — 287. Find the Duplicate Number

## Layer 3 — Problem-solving Pattern
**Pattern:** Fast & Slow Pointers (Floyd's Cycle Detection)
Treat the array as an implicit linked list where index i points to nums[i]. The duplicate creates a cycle whose entrance is the answer.

## Layer 2 — Algorithms & Techniques
- Hash Set approach: O(n) time, O(n) space
- Floyd's Cycle Detection: O(n) time, O(1) space
- **Insight:** nums[i] is always in [1,n] so index i → nums[i] is a valid "next pointer." The duplicate value means two indices point to the same node — creating a cycle. Finding the cycle entrance (142) = finding the duplicate.

## Layer 1 — Data Structures
- Array treated as implicit linked list
- (Hash Set for the naive approach)

## Two Approaches

### Approach 1: Hash Set (intuitive)
```python
def findDuplicate(nums):
    seen = set()
    for n in nums:
        if n in seen:
            return n
        seen.add(n)
```

### Approach 2: Floyd's (O(1) space)
```python
def findDuplicate(nums):
    slow, fast = 0, 0
    while True:
        slow = nums[slow]
        fast = nums[nums[fast]]
        if slow == fast:
            break

    slow2 = 0
    while slow != slow2:
        slow = nums[slow]
        slow2 = nums[slow2]
    return slow
```

## Interview note

This problem tests whether you know Floyd's algorithm exists. Lead with the hash set solution, then offer Floyd's as the O(1) space follow-up. Being able to explain WHY it works (cycle entrance = duplicate) matters more than memorizing the code.
