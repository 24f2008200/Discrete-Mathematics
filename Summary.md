Absolutely. I went through the assignment file as a whole and treated the **assignment questions themselves as the strongest indicator of what you are expected to know for the exam**. The material progresses from counting and sets through logic, relations/functions, graph theory, generating functions, recurrence relations, asymptotic analysis, and finally chromatic polynomials, partitions, and groups. DM

One important observation: **Assignment 12 is already in the file but is marked “Assignment not submitted.”** Since it is clearly part of the course material and your exam is next week, I would study it too. It introduces chromatic polynomials, integer partitions, Euler's partition identity, groups, subgroups, and Lagrange's theorem. DM

# Discrete Mathematics Exam Revision Pack

## 1. What the assignments are really testing

| Topic | What you should be able to do | Priority |
|---|---|---:|
| **Counting / Permutations / Combinations** | Decide whether order matters, repetition, restrictions | ⭐⭐⭐⭐⭐ |
| **Inclusion–Exclusion & Sets** | Venn problems, exactly one/two/all, complements | ⭐⭐⭐⭐⭐ |
| **Propositional Logic** | Translate English → logic, implication, equivalence, tautology | ⭐⭐⭐⭐⭐ |
| **Relations** | Reflexive, symmetric, antisymmetric, transitive, equivalence, partial order | ⭐⭐⭐⭐⭐ |
| **Functions** | Injective, surjective, bijective, composition, inverse | ⭐⭐⭐⭐⭐ |
| **Graph Theory** | Degree, paths, cycles, bridges, cut vertices, Euler/Hamilton | ⭐⭐⭐⭐⭐ |
| **Graph properties** | Bipartite, colouring, adjacency matrix, complement, isomorphism | ⭐⭐⭐⭐ |
| **Generating Functions** | Build factors and extract coefficients | ⭐⭐⭐⭐ |
| **Recurrence Relations** | Form recurrence, calculate terms, characteristic equation | ⭐⭐⭐⭐⭐ |
| **Asymptotic Analysis** | Big-O and growth-rate comparison | ⭐⭐⭐⭐ |
| **Stars and Bars** | Integer solutions with/without restrictions | ⭐⭐⭐⭐⭐ |
| **Derangements / Onto functions** | Apply formulas and inclusion-exclusion | ⭐⭐⭐⭐ |
| **Catalan / Dyck paths** | Recognize Catalan structures | ⭐⭐⭐ |
| **Chromatic Polynomial** | Paths, cycles, complete graphs | ⭐⭐⭐ |
| **Partitions** | Distinct/odd partitions and generating functions | ⭐⭐⭐ |
| **Groups** | Group axioms, identity, inverse, subgroup, Lagrange | ⭐⭐⭐⭐ |

The early assignments repeatedly distinguish permutation from combination, unrestricted repetition, restricted arrangements, circular arrangements, Catalan structures, and related counting patterns. DM

---

# 2. Formula Cheat Sheet

This is the part I'd keep beside you during your final revision.

## A. Basic Counting

### Multiplication principle

If a task has:

- \(n_1\) choices for step 1
- \(n_2\) choices for step 2
- ...
- \(n_k\) choices for step \(k\)

then

$$
\boxed{n_1n_2\cdots n_k}
$$

Example:

3 letters followed by 2 digits, repetition allowed:

$$
26^3 10^2
$$

---

### Addition principle

If choices are mutually exclusive:

$$
\boxed{n_1+n_2+\cdots+n_k}
$$

---

## B. Permutations

Order matters:

$$
\boxed{{}^nP_r=\frac{n!}{(n-r)!}}
$$

Example:

Choose and arrange 5 speakers from 16:

$$
{}^{16}P_5
$$

This exact distinction appears repeatedly in Assignment 1. DM

---

## C. Combinations

Order does **not** matter:

$$
\boxed{{n\choose r}=\frac{n!}{r!(n-r)!}}
$$

Useful relationship:

$$
\boxed{{}^nP_r={n\choose r}r!}
$$

### Exam trick

Ask:

> **If I swap two selected objects, does it create a new outcome?**

- Yes → permutation
- No → combination

---

# 3. Special Arrangement Formulas

### All \(n\) distinct objects in a line

$$
\boxed{n!}
$$

### Two specific objects must be together

Treat them as one block:

$$
\boxed{2(n-1)!}
$$

For \(n=7\):

$$
2(6!)
$$

### Two specific objects must NOT be together

$$
\boxed{n!-2(n-1)!}
$$

This exact "total minus bad arrangements" idea occurs in Assignment 1. DM

---

## Circular arrangements

For \(n\) distinct objects around a circle, rotations considered identical:

$$
\boxed{(n-1)!}
$$

If reflections are also considered identical, the usual necklace/bracelet treatment changes, so check the wording.

For 8 robots:

$$
7!
$$

---

# 4. Repeated Objects

If there are \(n\) objects with repetitions

$$
n_1,n_2,\ldots,n_k
$$

then distinct arrangements:

$$
\boxed{\frac{n!}{n_1!n_2!\cdots n_k!}}
$$

Example: LEVEL

- L appears 2 times
- E appears 2 times
- V appears once

$$
\frac{5!}{2!2!}=30
$$

Exactly the type used in the assignment. DM

---

# 5. Inclusion–Exclusion

## Two sets

$$
\boxed{|A\cup B|=|A|+|B|-|A\cap B|}
$$

## Three sets

$$
\boxed{
|A\cup B\cup C|=
|A|+|B|+|C|
-|A\cap B|-|A\cap C|-|B\cap C|
+|A\cap B\cap C|
}
$$

### Memory pattern

$$
\boxed{+\quad-\quad+}
$$

Singles → add

Pairs → subtract

Triple → add

The assignments explicitly test this repeatedly. DM

---

## Exactly two of three sets

$$
\boxed{
\text{Exactly 2}=
|A\cap B|+|A\cap C|+|B\cap C|
-3|A\cap B\cap C|
}
$$

## Only \(A\)

$$
\boxed{
|A\text{ only}|=
|A|-|A\cap B|-|A\cap C|+|A\cap B\cap C|
}
$$

## None

$$
\boxed{
|\text{None}|=|U|-|A\cup B\cup C|
}
$$

---

# 6. Set Identities

### Difference

$$
\boxed{A-B=A\cap B'}
$$

### De Morgan's laws

$$
\boxed{(A\cup B)'=A'\cap B'}
$$

$$
\boxed{(A\cap B)'=A'\cup B'}
$$

Very important. Assignment 2 directly tests these. DM

### Subset and complements

If

$$
A\subseteq B
$$

then

$$
\boxed{B'\subseteq A'}
$$

Notice the direction **reverses**.

---

# 7. Number of Subsets

For a set containing \(n\) elements:

$$
\boxed{2^n}
$$

Non-empty subsets:

$$
\boxed{2^n-1}
$$

Example:

9 mentors:

$$
2^9=512
$$

non-empty:

$$
2^9-1=511
$$

---

# 8. Propositional Logic

## Basic operators

| Symbol | Meaning |
|---|---|
| \(\neg P\) | NOT |
| \(P\land Q\) | AND |
| \(P\lor Q\) | OR |
| \(P\to Q\) | IF \(P\), THEN \(Q\) |
| \(P\leftrightarrow Q\) | iff / equivalent |

Assignment 3 heavily tests translation between English rules and these logical forms. DM

---

## The most important implication fact

$$
\boxed{P\to Q\equiv \neg P\lor Q}
$$

And:

$$
\boxed{P\to Q\equiv \neg Q\to\neg P}
$$

The second is the **contrapositive**.

### Don't confuse:

$$
P\to Q
$$

with

$$
Q\to P
$$

The latter is the **converse**, and is not generally equivalent.

---

## Implication truth table

| \(P\) | \(Q\) | \(P\to Q\) |
|---|---|---|
| T | T | T |
| T | F | **F** |
| F | T | T |
| F | F | T |

Only one situation makes implication false:

$$
\boxed{P=T,\ Q=F}
$$

This "false antecedent makes implication true" was explicitly tested. DM

---

# 9. Tautology / Contradiction / Contingency

### Tautology

Always true.

$$
\boxed{P\lor\neg P}
$$

### Contradiction

Always false.

$$
\boxed{P\land\neg P}
$$

### Contingency

Sometimes true, sometimes false.

Example:

$$
P\to Q
$$

The assignments explicitly distinguish these three categories. DM

---

# 10. Important Rules of Inference

### Modus Ponens

$$
P\to Q
$$

$$
P
$$

Therefore:

$$
\boxed{Q}
$$

### Modus Tollens

$$
P\to Q
$$

$$
\neg Q
$$

Therefore:

$$
\boxed{\neg P}
$$

### Disjunctive syllogism

$$
P\lor Q
$$

$$
\neg P
$$

Therefore:

$$
\boxed{Q}
$$

Assignment 3 directly tests Modus Ponens and Modus Tollens. DM

---

# 11. Relations

A relation on \(A\) is a subset of:

$$
\boxed{A\times A}
$$

If

$$
|A|=n
$$

then

$$
|A\times A|=n^2
$$

Therefore number of possible binary relations:

$$
\boxed{2^{n^2}}
$$

For a 4-element set:

$$
2^{16}=65536
$$

The assignment asks exactly this kind of question. DM

---

## Four properties

### Reflexive

Every element relates to itself:

$$
\boxed{(a,a)\in R\quad\forall a}
$$

Matrix:

$$
\boxed{\text{all diagonal entries are 1}}
$$

### Symmetric

$$
\boxed{aRb\Rightarrow bRa}
$$

Matrix:

$$
\boxed{M=M^T}
$$

### Antisymmetric

If

$$
aRb\text{ and }bRa
$$

then

$$
\boxed{a=b}
$$

For distinct \(a,b\), you cannot have both directions.

### Transitive

$$
aRb,\ bRc\Rightarrow aRc
$$

---

# 12. Equivalence Relation

Must be:

$$
\boxed{\text{Reflexive + Symmetric + Transitive}}
$$

Think:

> **"Same group / same category"**

Examples in your assignment:

- same study circle
- same serving counter

These naturally create equivalence classes. DM

---

## Equivalence class

$$
\boxed{[a]=\{x\in A:xRa\}}
$$

Equivalence relations correspond to **partitions**.

### Very important relationship

$$
\boxed{\text{Equivalence relation}\longleftrightarrow\text{Partition}}
$$

---

# 13. Partial Order

Must be:

$$
\boxed{\text{Reflexive + Antisymmetric + Transitive}}
$$

Memory trick:

| Relation | Properties |
|---|---|
| Equivalence | R + S + T |
| Partial order | R + A + T |

The badge-dependency relation in Assignment 4 is explicitly a partial order. DM

---

# 14. Functions

A function

$$
f:A\to B
$$

means:

> **Every element of \(A\) gets exactly one output in \(B\).**

### Well-defined

Every input has exactly one output.

---

## Injective

Different inputs produce different outputs:

$$
\boxed{f(a)=f(b)\Rightarrow a=b}
$$

Think:

> **No two arrows collide.**

---

## Surjective

Every element of the codomain gets hit:

$$
\boxed{\forall b\in B,\exists a\in A:f(a)=b}
$$

Think:

> **Nothing in the codomain is left unused.**

---

## Bijective

Both:

$$
\boxed{\text{Injective + Surjective}}
$$

A function has an inverse exactly when it is bijective.

Assignment 5 repeatedly tests this distinction. DM

---

# 15. Composition

If

$$
f:A\to B,\quad g:B\to C
$$

then:

$$
\boxed{g\circ f:A\to C}
$$

and

$$
\boxed{(g\circ f)(x)=g(f(x))}
$$

**Read from right to left.**

If

$$
f:\text{Learner}\to\text{Path}
$$

$$
g:\text{Path}\to\text{Dashboard}
$$

$$
h:\text{Dashboard}\to\text{Status}
$$

then:

$$
\boxed{h\circ g\circ f:\text{Learner}\to\text{Status}}
$$

---

# 16. Counting Integer Solutions

## Stars and Bars

Number of non-negative integer solutions to

$$
x_1+x_2+\cdots+x_k=n
$$

is

$$
\boxed{{n+k-1\choose k-1}}
$$

Example:

$$
x+y+z=12
$$

gives

$$
{14\choose2}
$$

---

### Positive integer solutions

For

$$
x_1+\cdots+x_k=n,\qquad x_i\ge1
$$

number:

$$
\boxed{{n-1\choose k-1}}
$$

---

# 17. Upper Bounds + Inclusion–Exclusion

For restrictions such as:

$$
x\le4
$$

count unrestricted solutions and subtract violations:

$$
x\ge5
$$

Set:

$$
x'=x-5
$$

Then solve again.

With several restrictions, use inclusion-exclusion.

This exact technique appears in the counting assignment. DM

---

# 18. Derangements

A derangement is a permutation where **nobody gets their original position**.

Notation:

$$
\boxed{D_n}
$$

Formula:

$$
\boxed{
D_n=n!\sum_{k=0}^{n}\frac{(-1)^k}{k!}
}
$$

Equivalent:

$$
D_n
=
n!
\left(
1-\frac1{1!}+\frac1{2!}-\cdots+\frac{(-1)^n}{n!}
\right)
$$

Important values:

$$
D_1=0
$$

$$
D_2=1
$$

$$
D_3=2
$$

$$
D_4=9
$$

The assignment explicitly asks \(D_4=9\). DM

---

# 19. Onto Functions

Number of onto functions from an \(m\)-element set to an \(n\)-element set:

$$
\boxed{
\sum_{k=0}^{n}
(-1)^k
{n\choose k}
(n-k)^m
}
$$

This is basically **inclusion-exclusion applied to missing outputs**.

---

# 20. Catalan Numbers

$$
\boxed{
C_n=\frac{1}{n+1}{2n\choose n}
}
$$

First few:

$$
1,1,2,5,14,42,132,\ldots
$$

Your assignments use Catalan numbers for:

- restricted grid paths
- non-crossing pairings
- polygon triangulations
- Dyck paths

Examples:

### Grid path

From \((0,0)\) to \((n,n)\), unrestricted:

$$
\boxed{{2n\choose n}}
$$

Restricted to one side of the diagonal:

$$
\boxed{C_n}
$$

### Polygon triangulation

For an \(n\)-gon:

$$
\boxed{C_{n-2}}
$$

Thus a hexagon:

$$
C_4=14
$$

### Dyck paths

Balanced \(n\) pickup and \(n\) drop operations with drops never exceeding pickups:

$$
\boxed{C_n}
$$

These are explicitly connected in Assignment 1. DM

---

# 21. Graph Theory

## Basic terminology

| Term | Meaning |
|---|---|
| Vertex | Node |
| Edge | Connection |
| Degree | Number of incident edges |
| Walk | Vertices/edges may repeat |
| Trail | No repeated edge |
| Path | No repeated vertex |
| Cycle | Closed path |

The assignment deliberately tests the differences between walk, path and cycle. DM

---

# 22. Handshaking Lemma

$$
\boxed{\sum_{v\in V}\deg(v)=2|E|}
$$

Therefore:

$$
\boxed{|E|=\frac{\sum\deg(v)}2}
$$

And:

> The number of odd-degree vertices is always even.

This is one of your **must-memorize formulas**. DM

---

# 23. Complete Graph

For \(n\) vertices:

$$
\boxed{|E(K_n)|={n\choose2}=\frac{n(n-1)}2}
$$

Maximum degree:

$$
\boxed{n-1}
$$

---

# 24. Complement Graph

For a simple graph with \(n\) vertices:

$$
\boxed{|E(G')|={n\choose2}-|E(G)|}
$$

Example:

7 vertices, 10 edges:

$$
{7\choose2}-10=
21-10=
11
$$

Exactly the style used in Assignment 8. DM

---

# 25. Euler vs Hamilton

This is a classic exam trap.

### Euler

Concerned with **edges**.

Eulerian circuit:

> Uses every edge exactly once and returns to start.

For a connected graph:

$$
\boxed{\text{All vertices have even degree}}
$$

Eulerian trail but not circuit:

$$
\boxed{\text{Exactly two odd-degree vertices}}
$$

### Hamiltonian

Concerned with **vertices**.

Hamiltonian path:

> Visits every vertex exactly once.

Hamiltonian cycle:

> Visits every vertex exactly once and returns to start.

The assignment explicitly contrasts these. DM

---

# 26. Bridge and Cut Vertex

### Bridge

An edge whose removal increases the number of connected components.

### Cut vertex

A vertex whose removal disconnects the graph.

In the museum graph used in the assignment, \(CE\) is a bridge and \(C\) is a cut vertex. DM

---

# 27. Bipartite Graph

A graph is bipartite if vertices can be divided into two groups such that every edge goes between the groups.

Critical theorem:

$$
\boxed{
G\text{ is bipartite}
\iff
G\text{ contains no odd cycle}
}
$$

Therefore:

$$
\boxed{\text{Odd cycle}\Rightarrow\text{not bipartite}}
$$

This appears directly in Assignment 8. DM

---

# 28. Graph Colouring

A proper colouring means adjacent vertices receive different colours.

The minimum number of colours required is the **chromatic number**:

$$
\boxed{\chi(G)}
$$

For complete graph:

$$
\boxed{\chi(K_n)=n}
$$

For a nontrivial bipartite graph:

$$
\boxed{\chi(G)=2}
$$

For a triangle:

$$
\boxed{\chi(K_3)=3}
$$

---

# 29. Adjacency Matrix

For a simple undirected graph:

$$
\boxed{A_{ij}=1}
$$

if vertices \(i,j\) are adjacent.

Otherwise:

$$
A_{ij}=0
$$

Properties:

- diagonal entries = 0
- matrix is symmetric

$$
\boxed{A=A^T}
$$

The assignment directly tests both. DM

---

# 30. Graph Isomorphism

Two graphs are isomorphic if there is a relabeling of vertices preserving adjacency.

Necessary conditions include:

- same number of vertices
- same number of edges
- same degree sequence

But:

$$
\boxed{\text{Same degree sequence does NOT guarantee isomorphism}}
$$

This is an important MCQ trap from Assignment 8. DM

---

# 31. Generating Functions

This deserves special attention because it looks mysterious at first, but the assignment's method is wonderfully mechanical.

### Take 0 or 1

$$
\boxed{1+x}
$$

### Take any number

$$
\boxed{1+x+x^2+x^3+\cdots=\frac1{1-x}}
$$

### Take an even number

$$
\boxed{1+x^2+x^4+\cdots=\frac1{1-x^2}}
$$

### Main rule

If

$$
F(x)=\sum a_nx^n
$$

then:

$$
\boxed{a_n=[x^n]F(x)}
$$

That means:

> The coefficient of \(x^n\) tells you how many ways produce total \(n\).

This is exactly how Assignment 9 introduces generating functions. DM

---

## Stars-and-bars connection

If \(r\) identical units are distributed among \(k\) types with unlimited repetition:

$$
\boxed{{r+k-1\choose k-1}}
$$

This is the same formula encountered earlier through integer solutions.

---

# 32. Recurrence Relations

A recurrence defines a term using previous terms.

Example:

$$
\boxed{a_n=(1+r)a_{n-1}}
$$

for compound growth.

### Important principle

A recurrence needs:

1. recurrence rule
2. initial condition(s)

Otherwise you cannot uniquely determine the sequence.

Assignment 11 begins exactly with this idea. DM

---

# 33. Fibonacci

$$
\boxed{F_n=F_{n-1}+F_{n-2}}
$$

with:

$$
F_1=F_2=1
$$

Sequence:

$$
1,1,2,3,5,8,13,21,\ldots
$$

Thus:

$$
F_7=13
$$

---

# 34. Staircase Recurrence

If you can climb either 1 or 2 steps:

$$
\boxed{f(n)=f(n-1)+f(n-2)}
$$

With:

$$
f(1)=1,\quad f(2)=2
$$

Then:

$$
f(3)=3
$$

$$
f(4)=5
$$

---

# 35. Characteristic Equation

For:

$$
a_n=c_1a_{n-1}+c_2a_{n-2}
$$

assume:

$$
a_n=x^n
$$

Then:

$$
\boxed{x^2-c_1x-c_2=0}
$$

If roots are \(r_1,r_2\):

$$
\boxed{a_n=Ar_1^n+Br_2^n}
$$

Constants \(A,B\) come from the initial conditions.

For Fibonacci:

$$
a_n=a_{n-1}+a_{n-2}
$$

so:

$$
\boxed{x^2-x-1=0}
$$

The characteristic-equation method is explicitly included in Assignment 11. DM

---

# 36. Important Algorithm Recurrences

### Tower of Hanoi

$$
T(n)=2T(n-1)+1
$$

Solution:

$$
\boxed{T(n)=2^n-1}
$$

### Binary search

$$
T(n)=T(n/2)+1
$$

$$
\boxed{T(n)=O(\log n)}
$$

### Merge sort

$$
T(n)=2T(n/2)+n
$$

$$
\boxed{T(n)=O(n\log n)}
$$

These three are explicitly compared in Assignment 11. DM

---

# 37. Growth Rates

Memorize this ordering:

$$
\boxed{
\log n
<
n
<
n\log n
<
n^2
<
2^n
<
n!
}
$$

For large \(n\).

So:

$$
n! > 2^n
$$

eventually.

---

## Big-O

Keep the dominant term.

Example:

$$
3n^2+5n+2
$$

Therefore:

$$
\boxed{O(n^2)}
$$

Not \(O(3n^2)\) in simplified form.

---

# 38. Chromatic Polynomials

Assignment 12 introduces this topic. DM

### Complete graph

$$
\boxed{
P(K_n,k)=k(k-1)(k-2)\cdots(k-n+1)
}
$$

### Path with \(n\) vertices

$$
\boxed{
P(P_n,k)=k(k-1)^{n-1}
}
$$

### Cycle with \(n\) vertices

$$
\boxed{
P(C_n,k)=
(k-1)^n+(-1)^n(k-1)
}
$$

### Chromatic number

$$
\boxed{
\chi(G)=\min\{k:P(G,k)>0\}
}
$$

For triangle:

$$
\chi(K_3)=3
$$

---

# 39. Integer Partitions

A partition of \(n\):

> Write \(n\) as a sum of positive integers, where order does not matter.

For 4:

$$
4
$$

$$
3+1
$$

$$
2+2
$$

$$
2+1+1
$$

$$
1+1+1+1
$$

Therefore:

$$
\boxed{p(4)=5}
$$

### Distinct-part partitions

No repeated parts.

For 4:

$$
4,\quad3+1
$$

so:

$$
\boxed{2}
$$

### Odd-part partitions

Only odd numbers.

For 4:

$$
3+1
$$

$$
1+1+1+1
$$

so:

$$
\boxed{2}
$$

This illustrates Euler's identity:

$$
\boxed{
\text{partitions into distinct parts}=
\text{partitions into odd parts}
}
$$

for every \(n\). DM

---

# 40. Partition Generating Functions

All partitions:

$$
\boxed{
\prod_{k=1}^{\infty}\frac1{1-x^k}
}
$$

Distinct parts:

$$
\boxed{
\prod_{k=1}^{\infty}(1+x^k)
}
$$

Odd parts:

$$
\boxed{
\prod_{\substack{k\ge1\\k\text{ odd}}}
\frac1{1-x^k}
}
$$

---

# 41. Groups

A group \(G\) with operation \(*\) satisfies four axioms:

### 1. Closure

$$
a*b\in G
$$

### 2. Associativity

$$
(a*b)*c=a*(b*c)
$$

### 3. Identity

There exists \(e\):

$$
\boxed{a*e=e*a=a}
$$

### 4. Inverse

For every \(a\):

$$
\boxed{a*a^{-1}=a^{-1}*a=e}
$$

Assignment 12 tests these definitions directly. DM

---

## Identity is unique

A group has:

$$
\boxed{\text{exactly one identity element}}
$$

---

## Integer addition

$$
(\mathbb Z,+)
$$

is a group.

Identity:

$$
\boxed{0}
$$

Inverse of \(a\):

$$
\boxed{-a}
$$

---

## Integer multiplication

$$
(\mathbb Z,\times)
$$

is **not** a group because, for example, 2 has no integer multiplicative inverse.

---

# 42. Subgroup

A subgroup is:

$$
\boxed{\text{a subset that is itself a group under the same operation}}
$$

---

# 43. Lagrange's Theorem

For a finite group \(G\):

$$
\boxed{|H|\mid |G|}
$$

for every subgroup \(H\).

Therefore, if:

$$
|G|=12
$$

possible subgroup orders are:

$$
\boxed{1,2,3,4,6,12}
$$

So 5 cannot be the order of a subgroup.

---

# 🔥 The 15 Things I Would Memorize First

If your exam were tomorrow, I'd prioritize these:

1. $\boxed{{}^nP_r=\frac{n!}{(n-r)!}}$
2. $\boxed{{n\choose r}=\frac{n!}{r!(n-r)!}}$
3. $\boxed{n!/(n_1!\cdots n_k!)}$
4. $\boxed{(n-1)!}$ circular permutations
5. $\boxed{2^n}$ subsets
6. **Three-set inclusion-exclusion**
7. **De Morgan's laws**
8. $\boxed{P\to Q\equiv\neg P\lor Q}$
9. **Equivalence = RST**
10. **Partial order = RAT**
11. $\boxed{\sum\deg(v)=2|E|}$
12. **Euler vs Hamilton**
13. $\boxed{{n+k-1\choose k-1}}$ stars and bars
14. $\boxed{C_n=\frac1{n+1}{2n\choose n}}$
15. Recurrences + characteristic equation + Big-O

---

# 📝 MOCK EXAM

I've deliberately made this **30 questions**, because 20 would leave some topics underrepresented.

Try it **without looking at the formula sheet first**.

## Section A: Counting and Sets

### Q1
From 12 students, 4 are selected and assigned to four different positions. How many arrangements are possible?

A. ${12\choose4}$  
B. $12^4$  
C. ${}^{12}P_4$  
D. $4!$

---

### Q2
How many 6-character strings can be formed using the 26 English letters if repetition is allowed?

A. $26!$  
B. $26^6$  
C. ${26\choose6}$  
D. ${}^{26}P_6$

---

### Q3
Seven people sit around a circular table. Rotations are considered identical. How many arrangements?

A. $7!$  
B. $6!$  
C. $7!/2$  
D. $6!/2$

---

### Q4
How many distinct arrangements can be made from the letters of **BANANA**?

A. $60$  
B. $120$  
C. $180$  
D. $720$

---

### Q5
A university has:

$$
|A|=50,\quad |B|=40,\quad |C|=30
$$

$$
|A\cap B|=15,\quad
|A\cap C|=10,\quad
|B\cap C|=8
$$

and

$$
|A\cap B\cap C|=5.
$$

How many students belong to at least one set?

---

### Q6
If a set contains 8 elements, how many non-empty subsets does it have?

A. $256$  
B. $255$  
C. $64$  
D. $128$

---

## Section B: Logic

### Q7
Which is logically equivalent to

$$
P\to Q?
$$

A. $P\land Q$  
B. $\neg P\lor Q$  
C. $P\lor\neg Q$  
D. $\neg P\land Q$

---

### Q8
What is the contrapositive of

$$
P\to Q?
$$

A. $Q\to P$  
B. $\neg P\to\neg Q$  
C. $\neg Q\to\neg P$  
D. $P\leftrightarrow Q$

---

### Q9
Which is a tautology?

A. $P\land\neg P$  
B. $P\lor\neg P$  
C. $P\to\neg P$  
D. $P\land Q$

---

### Q10
Given:

$$
P\to Q
$$

and

$$
\neg Q,
$$

what follows?

A. $P$  
B. $Q$  
C. $\neg P$  
D. Nothing

---

## Section C: Relations and Functions

### Q11
A relation $R$ on $A$ satisfies:

$$
aRa
$$

for every $a\in A$.

Which property is this?

A. Symmetric  
B. Reflexive  
C. Antisymmetric  
D. Transitive

---

### Q12
A relation is reflexive, symmetric and transitive. It is:

A. Partial order  
B. Equivalence relation  
C. Function  
D. Injection

---

### Q13
A relation is reflexive, antisymmetric and transitive. It is:

A. Equivalence relation  
B. Partial order  
C. Surjection  
D. Symmetric relation

---

### Q14
Let

$$
f:A\to B
$$

where $|A|=5$ and $|B|=3$.

Can $f$ be injective?

Explain briefly.

---

### Q15
A function $f:A\to B$ is surjective when:

A. Every element of $A$ has exactly one image  
B. No two elements of $A$ have the same image  
C. Every element of $B$ is the image of at least one element of $A$  
D. $A=B$

---

## Section D: Counting Techniques

### Q16
How many non-negative integer solutions exist for

$$
x+y+z=10?
$$

---

### Q17
How many positive integer solutions exist for

$$
x+y+z=10?
$$

---

### Q18
Four students return four books, with nobody receiving their own book. How many possibilities?

---

### Q19
How many ways can 3 distinct duties be assigned to 2 judges such that **both judges receive at least one duty**?

---

### Q20
What is

$$
C_4
$$

where $C_n$ is the Catalan number?

---

## Section E: Graph Theory

Consider a graph with:

$$
V=\{A,B,C,D,E\}
$$

and edges:

$$
AB,BC,CD,DA,CE.
$$

### Q21
What is the degree of $C$?

A. 1  
B. 2  
C. 3  
D. 4

---

### Q22
Which edge is a bridge?

A. $AB$  
B. $BC$  
C. $CD$  
D. $CE$

---

### Q23
Which vertex is a cut vertex?

A. $A$  
B. $B$  
C. $C$  
D. $D$

---

### Q24
What is the sum of all vertex degrees?

A. 5  
B. 8  
C. 10  
D. 12

---

### Q25
A connected graph has exactly two odd-degree vertices. Which is guaranteed?

A. Eulerian circuit  
B. Eulerian trail but not Eulerian circuit  
C. Hamiltonian cycle  
D. Complete graph

---

### Q26
Which graph cannot be bipartite?

A. A path  
B. A tree  
C. An even cycle  
D. An odd cycle

---

## Section F: Generating Functions and Recurrences

### Q27
An item may be selected 0, 1, 2, 3, ... times. What generating-function factor represents it?

A. $1+x$  
B. $x$  
C. $\frac1{1-x}$  
D. $\frac1{1-x^2}$

---

### Q28
For

$$
a_n=a_{n-1}+a_{n-2},
$$

what is the characteristic equation?

A. $x^2+x+1=0$  
B. $x^2-x-1=0$  
C. $x^2-1=0$  
D. $x-1=0$

---

### Q29
What is the asymptotic complexity of merge sort?

$$
T(n)=2T(n/2)+n
$$

A. $O(n)$  
B. $O(\log n)$  
C. $O(n\log n)$  
D. $O(2^n)$

---

## Section G: Assignment 12 Topics

### Q30
A group has order 12. Which **cannot** be the order of one of its subgroups?

A. 2  
B. 3  
C. 4  
D. 5

---

# Answer Key

Try not to peek until you've finished. 🫣

| Q | Answer |
|---:|---|
| 1 | **C** |
| 2 | **B** |
| 3 | **B** |
| 4 | **A** |
| 5 | **101** |
| 6 | **B** |
| 7 | **B** |
| 8 | **C** |
| 9 | **B** |
| 10 | **C** |
| 11 | **B** |
| 12 | **B** |
| 13 | **B** |
| 14 | **No**, because $|A|>|B|$ |
| 15 | **C** |
| 16 | $\boxed{{12\choose2}=66}$ |
| 17 | $\boxed{{9\choose2}=36}$ |
| 18 | $\boxed{D_4=9}$ |
| 19 | **6** |
| 20 | $\boxed{14}$ |
| 21 | **C = 3** |
| 22 | **D = CE** |
| 23 | **C** |
| 24 | **C = 10** |
| 25 | **B** |
| 26 | **D** |
| 27 | **C** |
| 28 | **B** |
| 29 | **C** |
| 30 | **D = 5** |

---

# 🎯 How I would revise during the next week

Given the breadth of the assignments, I would **not** study every topic with equal weight.

### Day 1
**Counting + permutations + combinations + circular arrangements**

Do 15–20 problems.

### Day 2
**Sets + inclusion-exclusion + logic**

Especially:

$$
P\to Q,\quad
\text{contrapositive},\quad
\text{De Morgan},\quad
\text{tautology}
$$

### Day 3
**Relations + equivalence relations + partial orders + functions**

Make sure you can instantly distinguish:

$$
\boxed{RST}
$$

from

$$
\boxed{RAT}
$$

### Day 4
**Graph theory**

This is a big one. Practice identifying:

- degree
- walk/trail/path/cycle
- bridge
- cut vertex
- Euler
- Hamilton
- bipartite
- complement
- adjacency matrix
- isomorphism
- colouring

The graph assignments contain a particularly dense cluster of these concepts. DM

### Day 5
**Stars & bars + derangements + Catalan + generating functions**

These are formula-heavy, so build a one-page mental toolbox.

### Day 6
**Recurrences + characteristic equations + Big-O**

Especially:

$$
2^n-1
$$

$$
O(\log n)
$$

$$
O(n\log n)
$$

and

$$
\log n<n<n\log n<n^2<2^n<n!
$$

### Day 7
**Full mock exam**

Do the 30 questions above under timed conditions.

Then revisit every question you got wrong.

---

## One final exam strategy

Your assignments reveal a very recognizable question style: **many questions are not asking you to perform a huge calculation. They are testing whether you can identify the correct mathematical structure.**

For example:

> "Order matters?" → permutation.

> "Order doesn't matter?" → combination.

> "Nobody gets their own?" → derangement.

> "Everyone receives something?" → surjection.

> "No two inputs collide?" → injection.

> "Same group?" → equivalence relation.

> "Every edge exactly once?" → Euler.

> "Every vertex exactly once?" → Hamilton.

> "Odd cycle?" → not bipartite.

> "Coefficient of $x^n$?" → number of ways to make total $n$.

> "Previous terms?" → recurrence.

> "Every pair directly connected?" → complete graph.

That pattern-recognition layer is probably your biggest scoring opportunity. The assignments repeatedly use exactly this style. DM

If you can make those associations **automatic**, the exam becomes much less like wrestling with 30 unrelated monsters and much more like opening the right drawer in a very well-organized toolbox. 🧰

