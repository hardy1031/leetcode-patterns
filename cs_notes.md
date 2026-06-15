# CS Notes

Fundamental computer science concepts encountered during LeetCode study.

---

## Python String Slice is O(k)

Slicing a string `s[i:j]` costs O(k) where k = j - i.

**Why:** A Python string object looks like this in memory:

```
[ type info | ref count | length | encoding | a | b | c | d | e | f ]
↑ object start                               ↑ character data (contiguous)
```

The variable `s` holds a pointer to the start of this object.
To do `s[2:5]`, Python must allocate a *new* object and copy `c`, `d`, `e` into it.

**Why not O(1)?** You might think: just change the length field and offset the start pointer.
That would work (it's what C++ `string_view` and Rust `&str` do), but Python's string object
has no "offset" field — it always starts from the beginning of the character data.
Adding an offset field to every string object would cost memory for the common case
to benefit the slice case. Python chose simplicity.

**Contrast with O(1) slice languages:**
- C++ `string_view` — stores pointer + length, no copy
- Rust `&str` — same, references original memory
- Go string slice — internally shares the same backing array

**Practical impact:**
```python
s[:gcd(len(s1), len(s2))]  # O(n) — copies characters
```

---

## Python is Slower than C/Rust — Why

| Reason | Impact |
|--------|--------|
| Everything is an object | Even `int 1` = 28 bytes on heap vs 4 bytes in C |
| Dynamic type checking | Every `a + b` checks types at runtime |
| Immutable strings | Slices always copy → O(k) |
| GIL | Only 1 thread runs Python bytecode at a time |

NumPy/Pandas are fast because their internals are C — Python just provides the syntax.
