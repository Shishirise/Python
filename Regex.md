#  Complete Regular Expressions (Regex) Guide

Regex (Regular Expressions) are patterns used to **search**, **extract**, and **validate** text.
This guide covers everything — from matching **characters** to full **strings**, step by step.

---

## 1️⃣ What is Regex?

Regex is a sequence of special characters that define a **search pattern**.
You can use it to find words, numbers, symbols, or specific text formats in strings.

Example:
```python
import re
re.findall(r"cat", "The cat sat on the mat.")
# ✅ Matches: ['cat']
```

---

## 2️⃣ Basic Character Matching

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|------------|------------------|------|
| `a` | Exact character “a” | `a` | `b` | Finds literal “a” |
| `.` | Any one character (except newline) | `a`, `1`, `@` | `\n` | Dot = any single char |
| `^` | Beginning of string | `^cat` → “cat” | “the cat” | Must start with “cat” |
| `$` | End of string | `cat$` → “my cat” | “cat food” | Must end with “cat” |

---

## 3️⃣ Character Sets `[ ]`

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `[abc]` | One of `a`, `b`, or `c` | `a`, `b` | `d` | Matches any one inside brackets |
| `[^abc]` | Not `a`, `b`, or `c` | `x`, `y`, `z` | `a` | `^` inside brackets means NOT |
| `[a-z]` | Lowercase letters | `a`, `m`, `z` | `A` | Range from a to z |
| `[A-Z]` | Uppercase letters | `A`, `M` | `a` | Range from A to Z |
| `[0-9]` | Any digit | `5`, `7` | `a` | Matches numbers only |
| `[a-z0-9]` | Lowercase + digits | `a`, `5` | `A`, `@` | Combined range |

---

## 4️⃣ Shorthand Character Classes

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `\d` | Digit | `0` | `A` | Equivalent to `[0-9]` |
| `\D` | Non-digit | `A`, `@` | `1` | Opposite of `\d` |
| `\w` | Word char (A–Z, a–z, 0–9, _) | `A`, `_`, `3` | `@` | Letters/numbers/underscore |
| `\W` | Non-word | `@`, `#` | `A` | Opposite of `\w` |
| `\s` | Whitespace | `' '`, `\t`, `\n` | `A` | Matches space/tab/newline |
| `\S` | Non-whitespace | `A`, `1` | `' '` | Opposite of `\s` |

---

## 5️⃣ Quantifiers — Repetition Rules

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `a?` | 0 or 1 `a` | `''`, `a` | `aa` | Optional one time |
| `a*` | 0 or more `a` | `''`, `a`, `aa` | `b` | Repeats any times |
| `a+` | 1 or more `a` | `a`, `aa` | `''` | Must appear once |
| `a{3}` | Exactly 3 `a`s | `aaa` | `aa` | Fixed count |
| `a{2,4}` | Between 2–4 `a`s | `aa`, `aaa` | `a`, `aaaaa` | Range count |
| `a{2,}` | 2 or more `a`s | `aa`, `aaa` | `a` | No upper limit |

---

## 6️⃣ Grouping and Capturing `( )`

Parentheses group parts of the pattern and extract them separately.

Example:
```python
import re
text = "My number is 334-222-1111"
pattern = r"(\d{3})-(\d{3})-(\d{4})"
print(re.findall(pattern, text))
# ✅ [('334', '222', '1111')]
```

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `(abc)` | Captures “abc” | `abc` | `ab` | Exact group |
| `(\d{3})-(\d{3})-(\d{4})` | Phone number | `334-222-1111` | `3342221111` | Dashes required |
| `(?:abc)` | Non-capturing | `abc` | — | Grouped but not extracted |

---

## 7️⃣ Boundaries and Anchors

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `^word` | At start | `word here` | `a word` | Must start the line |
| `word$` | At end | `hi word` | `word up` | Must end line |
| `\bword\b` | Whole word | `word` | `sword`, `wording` | Word boundaries only |

---

## 8️⃣ Alternation (OR) `|`

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `cat|dog` | Either cat or dog | `cat`, `dog` | `cow` | OR condition |

---

## 9️⃣ Escaping Special Characters

| Pattern | Meaning | ✅ Matches | ❌ Doesn’t Match | Why |
|----------|----------|-------------|------------------|------|
| `\.` | Literal dot | `file.txt` | `filext` | Escapes the special meaning |
| `\\` | Backslash | `\` | `\` | Escapes itself |
| `\?` | Literal question mark | `?` | `a` | Escapes quantifier |

---

## 🔟 Full String Examples

### ✅ Example 1 — Phone Numbers
```python
pattern = r"(\d{3})-(\d{3})-(\d{4})"
# ✅ Matches: 334-222-1111
# ❌ Doesn't match: 3342221111
```

### ✅ Example 2 — Emails
```python
pattern = r"([\w._%+-]+)@([\w.-]+)\.([A-Za-z]{2,})"
# ✅ Matches: test@gmail.com, user123@msutexas.edu
# ❌ Doesn't match: test@, hello@site
```

### ✅ Example 3 — Words Ending with "ing"
```python
pattern = r"\b\w+ing\b"
# ✅ running, eating, playing
# ❌ ring (inside word), ingly
```

---

## 1️⃣1️⃣ Summary Table — All Common Regex Symbols

| Symbol | Meaning |
|---------|----------|
| `.` | Any single character (except newline) |
| `^` | Start of string |
| `$` | End of string |
| `*` | 0 or more times |
| `+` | 1 or more times |
| `?` | 0 or 1 time |
| `{n}` | Exactly n times |
| `{n,}` | At least n times |
| `{n,m}` | Between n and m times |
| `[abc]` | One of a, b, or c |
| `[^abc]` | Anything except a, b, or c |
| `( )` | Capturing group |
| `(?: )` | Non-capturing group |
| `|` | OR (either) |
| `\d` | Digit [0-9] |
| `\D` | Not a digit |
| `\w` | Word char [A-Za-z0-9_] |
| `\W` | Not a word char |
| `\s` | Whitespace |
| `\S` | Non-whitespace |
| `\b` | Word boundary |

---

## ✅ Tips for Practice
- Always prefix regex in Python with `r"pattern"` to make it **raw string**.
- Test your regex live on [https://regex101.com](https://regex101.com)
- Use `re.findall()` to get all matches.
- Use `re.search()` to find the first match.
- Use `re.sub()` to replace matches.

---

**Created for:** Shishir Adhikari  
**Purpose:** Complete beginner-to-advanced regex guide covering both character and string-level matching, with full examples and explanation tables.
