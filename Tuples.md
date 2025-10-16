# Tuples in Python — Complete Notes

## 1. Definition
A **tuple** is an **ordered, immutable sequence** of elements.
It can contain **values of any type** (numbers, strings, lists, other tuples, etc.).
Defined by **commas**, usually inside parentheses.

```python
t = ('a', 'b', 'c', 'd', 'e')
t1 = 'a', 'b', 'c', 'd', 'e'    # also valid
t2 = ('a',)                     # single-element tuple — note the comma!
```

`t3 = ('a')` → *Not a tuple*, it's a string.

---

## 2. Key Properties
- **Immutable** → You can’t modify, add, or remove items after creation.
- **Indexed and Ordered** → Access elements using indices (`t[0]`, `t[-1]`).
- **Can contain duplicates**.

---

## 3. Tuple Creation Methods
```python
t = tuple([1, 2, 3])    # from list
t = tuple('abc')        # from string
```

---

## 4. Tuple Packing and Unpacking
You can assign multiple values at once.

```python
addr = 'tina.johnson@mwsu.edu'
uname, domain = addr.split('@')  # split returns list → unpacked into 2 vars

print(uname)   # tina.johnson
print(domain)  # mwsu.edu
```

---

## 5. Returning Multiple Values from Functions
A function can return a **tuple** to send back multiple values.

```python
def divmod_custom(x, y):
    return x // y, x % y    # returns a tuple (quotient, remainder)

t = divmod_custom(7, 3)
print(t)     # (2, 1)

quot, rem = divmod_custom(7, 3)
print(quot, rem)  # 2 1
```

---

## 6. Useful Built-in Functions with Tuples

| Function | Description | Example |
|-----------|--------------|----------|
| `len(t)` | Returns number of elements | `len((1,2,3)) → 3` |
| `max(t)` | Returns maximum value | `max((1,3,5,2)) → 5` |
| `min(t)` | Returns minimum value | `min((1,3,5,2)) → 1` |
| `sum(t)` | Adds numeric values | `sum((1,2,3)) → 6` |
| `sorted(t)` | Returns a sorted list | `sorted((3,1,2)) → [1,2,3]` |

---

## 7. zip() Function
Combines multiple sequences into tuples.

```python
s = 'abc'
t = [0, 1, 2]
zipped = list(zip(s, t))
print(zipped)
# [('a', 0), ('b', 1), ('c', 2)]
```
If sequences have different lengths, result matches **shortest sequence**.

---

## 8. Dictionaries and Tuples

### a. `.items()`
- Returns a list (or in Python 3, a view) of **(key, value)** tuples.

```python
d = {'a': 0, 'b': 1, 'c': 2}
t = d.items()
print(list(t))  # [('a', 0), ('b', 1), ('c', 2)]
```

### b. `.update()`
- Takes a **list of tuples** and adds/updates key-value pairs.

```python
d = {'a': 5, 'b': 10, 'c': 15, 'd': 20}
d.update([('e', 25), ('f', 30)])
print(d)
# {'a': 5, 'b': 10, 'c': 15, 'd': 20, 'e': 25, 'f': 30}
```

---

## 9. Other Tuple-Related Functions

| Function | Purpose | Example |
|-----------|----------|----------|
| `enumerate()` | Returns index and value as tuples | `list(enumerate(['a','b'])) → [(0,'a'), (1,'b')]` |
| `tuple()` | Converts iterable to tuple | `tuple('abc') → ('a','b','c')` |
| `*args` | Collects variable-length arguments into a tuple | `def func(*args): print(args)` |

---

## 10. When to Use Tuples
When you need **fixed** data that shouldn’t change.  
When you want to use sequence items as **dictionary keys** (since tuples are hashable).  
For **returning multiple values** from functions.

---

## Summary
- Tuples are immutable lists.
- Created using commas, often with parentheses.
- Can unpack or pack values easily.
- Commonly used with dictionary methods (`items()`, `update()`).
- Work with built-ins like `zip()`, `max()`, `min()`, and `enumerate()`.
