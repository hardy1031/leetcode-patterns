# Analysis: 853. Car Fleet

## Layer 3 — Problem-solving Pattern
**Pattern:** Monotonic Stack
Sort cars by position descending (closest to target first), convert each car to arrival time, then use a stack to count fleets — a car joins the fleet ahead if its time <= the top of the stack.

## Layer 2 — Algorithms & Techniques
- Sort by position descending O(n log n)
- Monotonic stack on arrival times O(n)
- **Insight:** Convert position+speed into a single value (arrival time) so fleet merging becomes a simple comparison. Process front-to-back so stack top always represents the nearest fleet ahead — if a car is slower (higher time), it can never catch up → new fleet.

## Layer 1 — Data Structures
- Stack (arrival times)
- zip + sorted to pair position and speed
