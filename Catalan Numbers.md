Catalan numbers are a sequence of whole numbers that show up in a surprising number of counting problems. The sequence begins 1, 1, 2, 5, 14, 42, 132, 429, and so on.

**The formula**

The nth Catalan number is:

C(n) = (2n)! / ((n+1)! · n!)

It can also be written as C(n) = (1/(n+1)) · (2n choose n), or built up with the recurrence C(n+1) = Σ C(i)·C(n−i) for i from 0 to n, starting from C(0) = 1.

**What they count**

The reason they matter is that many different-looking problems all have the same answer:

- **Balanced parentheses:** the number of valid ways to arrange n pairs of parentheses. For n = 3 there are 5: ((())), (()()), (())(), ()(()), ()()().
- **Binary trees:** the number of structurally different binary trees with n nodes.
- **Triangulations:** the number of ways to cut a convex polygon with n+2 sides into triangles using non-crossing diagonals.
- **Lattice paths:** the number of paths from (0,0) to (n,n) using only right and up steps that never go above the diagonal.
- **Non-crossing handshakes:** the number of ways 2n people around a table can pair up for handshakes without any arms crossing.
- **Stack sequences:** the number of valid push/pop orderings, and the number of ways to fully parenthesize a product of n+1 factors (for example, how to group a·b·c·d).

**Why the recurrence makes sense**

Take balanced parentheses. Every valid string starts with "(", which is matched by some ")". What sits inside that pair is a valid string of i pairs, and what follows is a valid string of the remaining n−i pairs. Summing over all choices of i gives exactly the recurrence above. The same split-into-two-independent-parts logic applies to trees and triangulations, which is why they share the sequence.

**Growth**

Catalan numbers grow roughly like 4ⁿ / (n^(3/2) · √π), so they increase quickly, by a factor approaching 4 each step.

If you'd like, I can walk through a specific example, such as deriving the lattice path version or computing C(4) by hand.



The key to using Catalan numbers is to recognize a particular kind of counting problem:

You are counting the number of valid arrangements, where the arrangements are constrained in some way.

The formula is

$$ \boxed{C_n=\frac{1}{n+1}\binom{2n}{n}} $$

The challenge in an exam is usually not calculating $C_n$. It is identifying whether the problem counts Catalan objects and what value of $n$ to use.

## 1. How to recognize a Catalan-number problem

Look for constraints such as:

- A path must not cross a diagonal boundary.
- Pairs must not cross each other.
- A polygon must be divided into triangles without crossing diagonals.
- Drops or closing operations must never exceed pickups or opening operations.
- Elements must be rearranged through a single stack.

These problems look different, but they share a common mathematical structure: the choices must remain valid at every intermediate step.

## 2. Apply the idea to your five cases

[Decrypting Catalan Numbers - Akshat Chaudhary](https://images.openai.com/static-rsc-4/sEX8AFJW-nzst_nctaWcwofAJNaVXL9rGC_fvPiJpGY6iOev3dOlVMfZIHU-5aqmJdrMrUndkNZQsSN1Lc0vy7bi2zTQdBAYen1IQCoBloHX3xs-y_1y1-xC5vN2zaR1fY4C4FhLZ-dRgWXdTorRhU3_lB8xyK_ziLxMh9GxwKo?purpose=inline)

A. Monotone grid paths

From $(0,0)$ to $(n,n)$

You can move only right or up. There are $n$ right moves and $n$ up moves, giving $2n$ moves in total.

- Unrestricted: any order of these moves is allowed.

  $$ \binom{2n}{n} $$
- Restricted: the path must stay on or below the diagonal $y=x$.

  $$ C_n=\frac{1}{n+1}\binom{2n}{n} $$

Exam clue: a diagonal-boundary restriction changes the binomial count into a Catalan count.

[ملف:Chord diagrams K6 matchings.svg - المعرفة](https://images.openai.com/static-rsc-4/7vk4PlNmFtGAMiMRU0BIUAMeLjLsB4ZWJYlgLgqygC51lRyNUgkyuqWMhYMJ8VpRAhxWstJEYliPzeKL1YIzxzeMVnssO84_1F4hEiijYLxLDpJBMIgRP7Te86NWw-2mmOGSx4qip74ub-wP4XiJ559egfa9fsNFy-uITw7G1K0?purpose=inline)

B. Non-crossing pairings of points on a circle

Given $2n$ points on a circle, pair every point with exactly one other point using straight chords, with no chords crossing.

The number of pairings is

$$ C_n $$

For 12 points: $2n=12$, so $n=6$.

$$ C_6=\frac{1}{7}\binom{12}{6} =\boxed{132} $$

Exam clue: pairing points with no crossings. Use half the number of points as the Catalan index.

[LearnMathOnline](https://images.openai.com/static-rsc-4/ImK_hDyqiBZeTv36YYXG2y8WFEJ1G7E8rmfoeUVnGE-SUfVOWNx2ioJCt-C8aNPredEyAp5GVf1DvPVSaU97240tYHwDYMf239FtDbnDQpYnHMzJ9CXCaWyYuLEByi8KR1TpRY_l5HfHnkzxnfjf2Wjhn85CHvCKPXaBiMzIe1Y?purpose=inline)

C. Triangulations of a convex polygon

Divide a convex polygon into triangles using non-crossing diagonals.

For a polygon with $n$ vertices, the number of triangulations is

$$ C\_{n-2} $$

For a hexagon: $n=6$, so the index is $6-2=4$.

$$ C_4=\frac{1}{5}\binom{8}{4} =\boxed{14} $$

Exam clue: triangulating a polygon. Subtract 2 from the number of sides before selecting the Catalan number.

[combinatorics - Number of Lattice Paths from $(0,0)$ to $(n, n)$ without going over $y=x$ - Mathematics Stack Exchange](https://images.openai.com/static-rsc-4/cHKI22IBnL4_B5wpTXwRnx92S3N-X9Fu_uhrtzVOa0cnu3XIUVn276HUsDS9wT97zFDqisaUpiU5Clp1TAE3wNjgMVUHu4Z7l0m-UPinjsb7BFPtjkX3xQzg97_dl_yv2hmrBaSX8r9lxegzjCN3iNOr7aRL-zQleXAK3i0O59s?purpose=inline)

D. Dyck paths and balanced pickup/drop logs

A Dyck path has $n$ up-steps and $n$ down-steps, with the path never crossing its permitted diagonal boundary.

Similarly, in a pickup/drop sequence, every drop must have a previous unmatched pickup. The number of valid sequences is

$$ C_n $$

For 4 pickups and 4 drops:

$$ C_4=\boxed{14} $$

Exam clue: equal numbers of opening/closing or pickup/drop operations, with no invalid prefix.

[개념적으로 접근하는 자료구조 - 스택(Stack) - DevMinGeonPark | BLEX](https://images.openai.com/static-rsc-4/-MFtzi-6q3w8T5jZj1yDq6SIn6ObdZA_-bJt9V_eVrWYrmIL-apZyPZ-r-fRE5WVMHDW25EBcV8R2f0-wFyk0DKmmv9q4DZPZYwZxJWoBM5NjqRpeAxnJABANj88OPJ-N3fBlC98mMIC8YjyDA8PpSucyHY11SBKh9aRBjIK2YQ?purpose=inline)

E. Stack-sortable permutations

A fixed input order is passed through a single stack. Push and pop operations can vary, but LIFO must be respected.

The number of distinct possible outputs from $n$ distinct input elements is

$$ C_n $$

For `A B C D`:

$$ C_4=\boxed{14} $$

Exam clue: a fixed input sequence, one stack, and all possible output permutations.

## 3. Your exam cheat sheet

| Problem wording                                     | What to calculate   |
| --------------------------------------------------- | ------------------- |
| Paths from $(0,0)$ to $(n,n)$, unrestricted | $\binom{2n}{n}$ |
| Same paths, staying on/below diagonal               | $C_n$           |
| Non-crossing pairings of $2n$ points            | $C_n$           |
| Triangulations of an $n$-sided polygon          | $C\_{n-2}$      |
| Balanced pickup/drop sequences of $n$ pairs     | $C_n$           |
| Stack-sortable outputs of $n$ elements          | $C_n$           |

## 4. The most useful way to remember it

Catalan numbers begin:

$$ \boxed{1,\ 1,\ 2,\ 5,\ 14,\ 42,\ 132,\ 429,\ldots} $$

These are $C_0,C_1,C_2,\ldots,C_7$.

Before applying the formula, ask yourself three questions:

1. What am I counting? Paths, pairings, triangulations, sequences, or stack outputs?
2. What is $n$? Number of pairs, number of elements, or polygon sides minus two?
3. Is there a restriction that must hold throughout? For example, no crossings or no drops before pickups.

One important distinction: not every problem involving a restriction uses Catalan numbers. The arrangement must have the appropriate Catalan structure. In particular, unrestricted grid paths use a binomial coefficient, not a Catalan number.
