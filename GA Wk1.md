Here are the answers with the reasoning behind each one.

---

# Case Study 1

## Q1

**From 16 speakers, select and arrange 5.**

* Selection **and** order matter.
* Use **permutations**.

[
P(n,r)=\frac{n!}{(n-r)!}
]

[
P(16,5)=\frac{16!}{11!}
]

✅ **Answer:** **(P(16,5))**

---

## Q2

**Choose 4 items from 12. Order doesn't matter.**

Use combinations.

[
C(12,4)=\frac{12!}{4!8!}
]

✅ **Answer:** **(C(12,4))**

---

## Q3

**6-character passcode using 10 digits. Repetition allowed.**

Each position has 10 choices.

```
10 × 10 × 10 × 10 × 10 × 10
```

[
=10^6
]

✅ **Answer:** **(10^6)**

---

## Q4

**Assign 3 demos to 3 of 9 slots. Order matters.**

This is a permutation.

[
P(9,3)=9\times8\times7
]

✅ **Answer:** **(P(9,3))**

---

## Q5

**Gold, Silver, Bronze to 3 different teams from 11.**

Awards are different.

Gold ≠ Silver ≠ Bronze.

Order matters.

[
P(11,3)
]

✅ **Answer:** **(P(11,3))**

---

## Q6

Which uses **combinations**?

* Ranking → order matters ❌
* Arranging speakers → order matters ❌
* Selecting posters → order doesn't matter ✅
* Assigning offices → president ≠ secretary ❌

✅ **Answer:** **Selecting 6 posters from 20 posters**

---

## Q7

**8 mentors. Two particular mentors must NOT sit together.**

Total arrangements

[
8!
]

Treat the two mentors as one block:

```
(AB), C,D,E,F,G,H
```

Now there are

[
7!
]

arrangements.

Inside the block:

```
AB
BA
```

Two possibilities.

Invalid

[
2\times7!
]

Valid

[
8!-2\times7!
]

✅ **Answer:** **(8!-2\cdot7!)**

---

## Q8

Why exactly half satisfy A before B?

Every arrangement

```
A ... B
```

has a unique partner

```
B ... A
```

obtained by swapping A and B.

Thus half have A before B.

✅ **Answer:**

**Each order with A before B pairs with exactly one order with B before A**

---

## Q9

Badge

```
LLLDD
```

Letters repeat

Digits repeat

Choices

[
26^3\times10^2
]

✅ **Answer:** **(26^3\cdot10^2)**

---

## Q10

Choose independently

* 2 seniors from 7
* 3 juniors from 9

Multiply.

[
C(7,2)\times C(9,3)
]

✅ **Answer:** **(C(7,2)\cdot C(9,3))**

---

# Case Study 2

## Q11

From

[
(0,0)\rightarrow(4,4)
]

Need

* 4 Right
* 4 Up

Choose positions of Rights.

Total

[
C(8,4)
]

✅ **Answer:** **(C(8,4))**

---

## Q12

Stay on or below the diagonal.

This is the classic Catalan problem.

✅ **Answer:** **Catalan numbers**

---

## Q13

Books

```
A B C D
```

through one stack.

Test each sequence.

### CABD

Possible:

```
Push A
Push B
Push C
Pop C
Pop A?
```

Cannot.

After popping C,

B is above A.

Must pop B first.

Impossible.

The remaining options are stack permutations.

✅ **Answer:** **CABD**

---

## Q14

12 circular points

Pair without crossings.

This is exactly Catalan.

Since

[
2n=12
]

[
n=6
]

Answer

[
C_6
]

✅ **Answer:** **Catalan number (C_6)**

---

## Q15

Hexagon

6 sides.

Triangulations

[
C_{n-2}
]

[
C_4
]

✅ **Answer:** **Catalan number (C_4)**

---

## Q16

5 pickups

5 drops

Drops never exceed pickups.

Definition of a Dyck path.

✅ **Answer:** **Dyck paths**

---

## Q17

Which grows faster?

Eventually

[
n!>2^n
]

because factorial multiplies by larger and larger numbers.

Example

```
10! = 3,628,800

2^10 = 1024
```

✅ **Answer:** **(n!)**

---

## Q18

7 tasks.

Two specified tasks consecutive.

Treat them as one block.

Objects become

```
(Block),5 others
```

Total

```
6!
```

Inside block

```
BS
SB
```

Two ways.

Answer

[
2\times6!
]

✅ **Answer:** **(2\cdot6!)**

---

## Q19

LEVEL

Letters

```
L = 2
E = 2
V = 1
```

Total letters

5

Distinct arrangements

[
\frac{5!}{2!\times2!}
=\frac{120}{4}
=30
]

✅ **Answer:** **30**

---

## Q20

8 distinct robots around a circle.

Rotations are identical.

Circular permutations

[
(n-1)!
]

[
7!
]

✅ **Answer:** **(7!)**

---

# Final Answer Key

| Q  | Answer                                                          |
| -- | --------------------------------------------------------------- |
| 1  | (P(16,5))                                                       |
| 2  | (C(12,4))                                                       |
| 3  | (10^6)                                                          |
| 4  | (P(9,3))                                                        |
| 5  | (P(11,3))                                                       |
| 6  | Selecting 6 posters from 20                                     |
| 7  | (8!-2\cdot7!)                                                   |
| 8  | Each arrangement with A before B pairs with one with B before A |
| 9  | (26^3\cdot10^2)                                                 |
| 10 | (C(7,2)\cdot C(9,3))                                            |
| 11 | (C(8,4))                                                        |
| 12 | Catalan numbers                                                 |
| 13 | **CABD**                                                        |
| 14 | Catalan number (C_6)                                            |
| 15 | Catalan number (C_4)                                            |
| 16 | Dyck paths                                                      |
| 17 | (n!)                                                            |
| 18 | (2\cdot6!)                                                      |
| 19 | 30                                                              |
| 20 | (7!)                                                            |

### Quick identification rules for exams

* **Order matters, no repetition:** Permutation (P(n,r))
* **Order doesn't matter:** Combination (C(n,r))
* **Repetition allowed:** (n^r)
* **Shortest grid paths:** (\binom{m+n}{m})
* **Stay below/on diagonal:** Catalan numbers
* **Non-crossing pairings:** Catalan numbers
* **Polygon triangulations:** (C_{n-2})
* **Balanced pickup/drop (or balanced parentheses):** Dyck paths
* **Circular arrangements:** ((n-1)!)
* **Repeated letters:** (\dfrac{n!}{n_1!n_2!\cdots})
