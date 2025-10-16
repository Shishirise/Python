# Dictionaries in Python — Complete Notes

## 1. Definition
A **dictionary** in Python is an **unordered collection** of **key-value pairs**.  
Each key must be **unique** and **immutable** (like a string, number, or tuple).  
Values can be of **any type** and **can be duplicated**.

```python
d = {'name': 'Alice', 'age': 25, 'city': 'Dallas'}
```

---

## 2. Key Properties
- **Mutable:** You can add, remove, or change items.  
- **Unordered:** Does not keep insertion order before Python 3.7 (ordered after 3.7).  
- **Keys must be unique.**  
- **Keys must be immutable.**

---

## 3. Creating Dictionaries

### a. Using `{}` brackets:
```python
student = {'name': 'John', 'age': 20, 'major': 'CS'}
```

### b. Using `dict()` constructor:
```python
student = dict(name='John', age=20, major='CS')
```

### c. From list of tuples:
```python
pairs = [('a', 1), ('b', 2)]
d = dict(pairs)
print(d)  # {'a': 1, 'b': 2}
```

---

## 4. Accessing Elements

```python
d = {'a': 10, 'b': 20, 'c': 30}
print(d['a'])         # 10
print(d.get('b'))     # 20
print(d.get('z', 0))  # 0 (default value if not found)
```

---

## 5. Modifying Dictionaries

### a. Adding new pairs:
```python
d['d'] = 40
```

### b. Updating existing values:
```python
d['a'] = 99
```

### c. Using `update()` to add multiple items:
```python
d.update({'e': 50, 'f': 60})
# or
d.update([('g', 70), ('h', 80)])
```

---

## 6. Deleting Elements

```python
del d['a']          # Remove key 'a'
d.pop('b')          # Removes and returns value for 'b'
d.popitem()         # Removes last inserted key-value pair (Python 3.7+)
d.clear()           # Removes all items
```

---

## 7. Dictionary Methods (Full List with Examples)

| Method | Description | Example |
|---------|--------------|----------|
| `clear()` | Removes all items | `d.clear()` |
| `copy()` | Returns a shallow copy | `d2 = d.copy()` |
| `fromkeys(seq, value)` | Creates new dict from sequence of keys | `dict.fromkeys(['a','b'], 0)` → `{'a':0,'b':0}` |
| `get(key, default)` | Returns value for key or default if missing | `d.get('z', 0)` |
| `items()` | Returns view object with key-value pairs as tuples | `list(d.items())` → `[('a',10),('b',20)]` |
| `keys()` | Returns view object with all keys | `list(d.keys())` |
| `values()` | Returns view object with all values | `list(d.values())` |
| `pop(key[, default])` | Removes key and returns its value | `d.pop('a')` |
| `popitem()` | Removes and returns last inserted (key, value) pair | `d.popitem()` |
| `setdefault(key[, default])` | Returns value if key exists, else inserts with default | `d.setdefault('x', 99)` |
| `update([other])` | Adds key-value pairs from another dict or iterable | `d.update({'c':3})` |

---

## 8. Looping Through a Dictionary

```python
for key in d:
    print(key, d[key])

for key, value in d.items():
    print(f"{key} → {value}")
```

---

## 9. Dictionary Comprehension

A concise way to create dictionaries.

```python
squares = {x: x**2 for x in range(5)}
print(squares)  # {0:0, 1:1, 2:4, 3:9, 4:16}
```

With condition:
```python
even_squares = {x: x**2 for x in range(10) if x % 2 == 0}
```

---

## 10. Nested Dictionaries

```python
students = {
    'Alice': {'age': 22, 'major': 'CS'},
    'Bob': {'age': 23, 'major': 'Math'}
}
print(students['Alice']['major'])  # CS
```

---

## 11. Dictionary with Tuples

```python
t = [('a', 10), ('b', 20)]
d = dict(t)
print(d)  # {'a': 10, 'b': 20}
```

---

## 12. Converting Between Lists and Dictionaries

```python
d = {'a': 1, 'b': 2, 'c': 3}
list_of_keys = list(d.keys())        # ['a', 'b', 'c']
list_of_values = list(d.values())    # [1, 2, 3]
list_of_pairs = list(d.items())      # [('a',1),('b',2),('c',3)]
```

---

## 13. Combining Two Lists into a Dictionary

```python
keys = ['name', 'age', 'city']
values = ['John', 25, 'Dallas']
d = dict(zip(keys, values))
print(d)
# {'name': 'John', 'age': 25, 'city': 'Dallas'}
```

---

## 14. Checking Existence

```python
if 'a' in d:
    print("Key exists!")
if 25 in d.values():
    print("Value exists!")
```

---

## 15. Copy vs Assignment

```python
d1 = {'a': 1, 'b': 2}
d2 = d1          # both point to same dict
d3 = d1.copy()   # creates a new copy
```

---

## Summary
- Dictionaries store key–value pairs.
- Keys must be unique and immutable.
- Values can be any data type.
- Support many useful methods (`get`, `update`, `items`, etc.).
- Common for storing structured or lookup-based data.
