# While Loops: Exam Questions & Answers

## Simple Counting Loop
**Question:**
Write a `while` loop that prints numbers from 1 to 10.

**Answer:**
```python
count = 1
while count <= 10:
    print(count)
    count += 1
```
**Output:**
```
1
2
3
4
5
6
7
8
9
10
```

**Explanation:** Loop runs until count > 10; `count += 1` increases it each iteration.

---

##  Sum of Numbers Using While
**Question:**
Use a while loop to find the sum of numbers from 1 to 50.

**Answer:**
```python
num = 1
total = 0
while num <= 50:
    total += num
    num += 1
print("Sum =", total)
```
**Output:**
```
Sum = 1275
```

**Explanation:** `total` accumulates the sum, `num` increases until 50.

---

## 3️Input Validation Loop
**Question:**
Ask the user to enter a number greater than 0. Keep asking until they enter correctly.

**Answer:**
```python
num = int(input("Enter a number > 0: "))
while num <= 0:
    print("Invalid input!")
    num = int(input("Enter a number > 0: "))
print("You entered:", num)
```

**Explanation:** Loop continues as long as input is invalid.

---

## 4️Infinite Loop with Break
**Question:**
Write a while loop that prints numbers 1 to 5 using `break`.

**Answer:**
```python
count = 1
while True:
    print(count)
    if count == 5:
        break
    count += 1
```
**Output:**
```
1
2
3
4
5
```

**Explanation:** `while True:` creates an infinite loop; `break` stops it.

---

##  While Loop with Continue
**Question:**
Print all numbers from 1 to 10, but skip multiples of 3.

**Answer:**
```python
num = 1
while num <= 10:
    if num % 3 == 0:
        num += 1
        continue
    print(num)
    num += 1
```
**Output:**
```
1
2
4
5
7
8
10
```

**Explanation:** `continue` skips multiples of 3.

---

## Factorial Using While Loop
**Question:**
Calculate factorial of 5 using a while loop.

**Answer:**
```python
n = 5
factorial = 1
while n > 0:
    factorial *= n
    n -= 1
print("Factorial =", factorial)
```
**Output:**
```
Factorial = 120
```

**Explanation:** Multiply factorial by `n` each iteration, decrease `n` until 0.

---

## Reverse Counting
**Question:**
Print numbers from 10 down to 1.

**Answer:**
```python
num = 10
while num >= 1:
    print(num)
    num -= 1
```
**Output:**
```
10
9
8
7
6
5
4
3
2
1
```

**Explanation:** Decrease counter each iteration.

---

##Exam Tips
1. Initialize counter before the loop.
2. Ensure the loop has a stopping condition.
3. Use `break` for special exit conditions.
4. `continue` skips the current iteration but loop continues.
5. Always update the counter to avoid infinite loops.

