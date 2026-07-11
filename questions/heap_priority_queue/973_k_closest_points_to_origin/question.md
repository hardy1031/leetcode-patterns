# 973. K Closest Points to Origin

You are given a 2-D array `points` where `points[i] = [xi, yi]` represents the coordinates of a point on an X-Y plane, and an integer `k`.

Return the `k` closest points to the origin `(0, 0)`.

The distance between two points is the Euclidean distance: `sqrt((x1-x2)^2 + (y1-y2)^2)`.

You may return the answer in any order.

## Examples

**Example 1:**
```
Input: points = [[0,2],[2,2]], k = 1
Output: [[0,2]]
```

**Example 2:**
```
Input: points = [[0,2],[2,0],[2,2]], k = 2
Output: [[0,2],[2,0]]
```

## Constraints
- `1 <= k <= points.length <= 1000`
- `-100 <= points[i][0], points[i][1] <= 100`

## Links
- [LeetCode](https://leetcode.com/problems/k-closest-points-to-origin/)
- [NeetCode](https://neetcode.io/problems/k-closest-points-to-origin)
