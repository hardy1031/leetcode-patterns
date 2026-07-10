# Analysis — 703. Kth Largest Element in a Stream

## Layer 3 — Problem-solving Pattern
**Pattern:** heap_priority_queue — min-heap of fixed size k
To efficiently track the k largest elements in a stream, maintain a min-heap of exactly size k. The heap top is always the kth largest.

## Layer 2 — Algorithms & Techniques
- Min-heap of size k: O(n log k) init, O(log k) per add
- **Insight:** Use a min-heap (not max-heap) of size k. The top of a min-heap is the smallest among the k elements — which is exactly the kth largest overall. When the heap exceeds size k, pop the top (discard the smallest), keeping only the top-k largest. This is the canonical "top-k" heap pattern.

## Layer 1 — Data Structures
- Min-heap (`heapq` in Python, which is a min-heap by default)

## Implementation

```python
class KthLargest:
    def __init__(self, k, nums):
        self.minHeap, self.k = nums, k
        heapq.heapify(self.minHeap)
        while len(self.minHeap) > k:
            heapq.heappop(self.minHeap)

    def add(self, val):
        heapq.heappush(self.minHeap, val)
        if len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)
        return self.minHeap[0]
```

## Complexity
- Init: O(n log k) — heapify is O(n), then pop down to size k
- add: O(log k)
- Space: O(k)

## Why min-heap and not max-heap?
A max-heap of size k would give the largest at the top — but you'd need to search inside the heap to find the kth largest, which is O(k). A min-heap of size k always has the kth largest at the top in O(1).
