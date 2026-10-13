# Discrete Mathematics: Final Exam Prep

Oct 13, 2026 · @PBN

This doc covers all 12 weekly assignments: a formula sheet first, then 71 practice questions in the same style, then an answer key. Read the sheet once, attempt the questions without looking, then check the key.

## 1. Counting and Catalan numbers (Weeks 1, 10)

First decide: does order matter, and can items repeat? That picks the formula.

| Situation | Formula |
| --- | --- |
| Ordered, no repeats (r from n) | P(n,r) = n!/(n−r)! |
| Unordered, no repeats | C(n,r) = n!/(r!(n−r)!) |
| Ordered, repeats allowed (codes, passcodes) | n^r |
| Independent stages | Multiply (3 letters then 2 digits: 26^3 · 10^2) |
| Choose from separate groups | Multiply the C's: C(7,2) · C(9,3) |
| Subsets of an n-set | 2^n (non-empty: 2^n − 1) |
| Arrangements with repeated letters | n!/(a! b! ...) (LEVEL: 5!/(2! 2!) = 30) |
| Circular arrangements of n distinct people | (n−1)! |
| Two specific people adjacent in a row | 2 · (n−1)! |
| Two specific people not adjacent in a row | n! − 2 · (n−1)! |
| Two specific people adjacent at a round table | 2 · (n−2)! |
| A before B in a random order | n!/2 (pair each order with its reverse) |

**Catalan numbers.** C\_n = C(2n,n)/(n+1). Values: C\_0=1, C\_1=1, C\_2=2, C\_3=5, C\_4=14, C\_5=42, C\_6=132.

- Monotone grid paths (0,0) to (n,n), unrestricted: C(2n,n). Staying on or below the diagonal: C\_n.
- Non-crossing pairings of 2n points on a circle: C\_n (12 points: C\_6).
- Triangulations of an n-sided convex polygon: C\_(n−2) (hexagon: C\_4 = 14).
- Dyck paths and balanced pickup/drop logs (drops never exceed pickups): C\_n.
- Stack-sortable outputs: for input A B C D, the output C A B D is impossible (A cannot leave before B once C is out).

**Growth.** n! eventually beats 2^n.

**Stars and bars.** Non-negative solutions of x1 + ... + xk = n: C(n+k−1, k−1). The same count applies to choosing r units from k types with repeats.

**Upper limits (inclusion–exclusion).** For a limit x ≤ b, subtract solutions with x ≥ b+1 (substitute x' = x − (b+1)), add back overlaps. Example: x+y+z=9 with each ≤ 4 gives C(11,2) − 3·C(6,2) + 0 = 55 − 45 = 10.

**Derangements.** D\_n = n!(1 − 1/1! + 1/2! − ... + (−1)^n/n!). D\_1=0, D\_2=1, D\_3=2, D\_4=9, D\_5=44.

**Onto functions** from m items to n targets: sum for k=0..n of (−1)^k C(n,k) (n−k)^m. For 5 duties onto 2 judges: 2^5 − 2 = 30.

**Non-attacking rooks.** k on an n×n board: C(n,k)^2 · k!.

**Trap from your assignment:** 6 people around a round table is 5! = 120, not 6! = 720.

## 2. Sets, inclusion–exclusion and logic (Weeks 2, 3, 10)

**Inclusion–exclusion.**

```latex
|A \cup B \cup C| = |A|+|B|+|C| - |A\cap B| - |A\cap C| - |B\cap C| + |A\cap B\cap C|
```

Two sets: |A ∪ B| = |A| + |B| − |A ∩ B|. None of the sets = total − |union|.

**Region counts (the Venn peel).** Let t = |A∩B∩C|.

| Region | Count |
| --- | --- |
| In A and B only (not C) | \|A∩B\| − t |
| Only A | \|A\| − \|A∩B\| − \|A∩C\| + t |
| Exactly two sets | sum of pairwise overlaps − 3t |
| Exactly one set | union − (exactly two) − t |
| All three | t |

Worked check (HealthPlus: 72, 58, 50; pairs 30, 26, 22; triple 10): union = 112, exactly two = 48, exactly one = 54, only Gym = 26.

**Set identities.** A − B = A ∩ B'. De Morgan: (A ∪ B)' = A' ∩ B' and (A ∩ B)' = A' ∪ B'. If D ⊆ V then V' ⊆ D'. "Either G or N but not C" = (G ∪ N) − C.

**Logic basics.**

- Atomic proposition: a single statement with no connectives (P, not P ∧ R).
- Implication: p → q ≡ ¬p ∨ q. False only when p is true and q is false. A false antecedent makes it vacuously true.
- Contrapositive of p → q is ¬q → ¬p, and it is equivalent. The converse q → p is not equivalent.
- Biconditional: p ↔ q is true when both have the same truth value.
- De Morgan: ¬(p ∧ q) ≡ ¬p ∨ ¬q and ¬(p ∨ q) ≡ ¬p ∧ ¬q.
- Tautology: always true (R ∨ ¬R). Contradiction: always false (E ∧ ¬E). Contingency: sometimes true, sometimes false (W → R).
- "Cannot both hold" is ¬(V ∧ N).
- "Whenever A and not B, then C" is (A ∧ ¬B) → C.

**Inference rules.**

| Rule | Form |
| --- | --- |
| Modus ponens | p → q, p, therefore q |
| Modus tollens | p → q, ¬q, therefore ¬p |
| Disjunctive syllogism | p ∨ q, ¬p, therefore q |

A set of statements is inconsistent when no assignment makes all of them true, e.g. {F → V, F, ¬V}.

## 3. Relations and functions (Weeks 4, 5)

**Relation properties** (on a set A, relation R, matrix M).

| Property | Meaning | In the matrix |
| --- | --- | --- |
| Reflexive | (a,a) in R for every a | All diagonal entries are 1 |
| Symmetric | (a,b) in R implies (b,a) in R | Matrix equals its transpose |
| Antisymmetric | (a,b) and (b,a) in R implies a = b | No pair of off-diagonal 1s mirrored across the diagonal |
| Transitive | (a,b) and (b,c) in R implies (a,c) in R | Check every two-step path |

- **Partial order** = reflexive + antisymmetric + transitive (badge dependency D).
- **Equivalence relation** = reflexive + symmetric + transitive (same study circle).
- Equivalence classes partition the set: classes are disjoint, non-empty and cover the set. Overlapping blocks like {s1,s2},{s2,s3} are not a partition.
- Number of relations on an n-set: 2^(n²) (n=4 gives 2^16). Number of equivalence relations on a 5-set: Bell number B\_5 = 52.
- Ordered pairs in an equivalence relation with class sizes a, b, ... = a² + b² + ... (classes 2 and 3 give 13; classes 2,1,2 give 9).
- Zeroing the diagonal kills reflexivity.
- Adding a new element to a class: it needs a self-pair plus two-way pairs with every member.

**Functions.** f: X → Y is well-defined when every x has exactly one output.

| Term | Meaning |
| --- | --- |
| Injective (one-to-one) | Different inputs give different outputs |
| Surjective (onto) | Every element of the codomain is hit |
| Bijective | Both; this is exactly when the inverse exists |
| Constant | Every input gives the same output |
| Composition (g∘f)(x) | g(f(x)): do f first |

- Injections from an m-set to an n-set (m ≤ n): P(n,m) = n!/(n−m)! (40 learners into 50 paths: 50!/10!).
- If |domain| > |codomain|, the function cannot be injective.
- If |domain| < |codomain|, it cannot be surjective.
- A function induces an equivalence relation: u \~ v when f(u) = f(v).
- A one-way (hash) function is easy to compute but hard to invert.
- Ceiling: d(n) = ceil(n/15) is not injective, because many n share a block. d(31) = 3.
- The tie-in with Week 1: bijections between equal-size finite sets exist, and counting onto functions uses inclusion–exclusion (section 1).

## 4. Induction, pigeonhole, recurrences and growth (Weeks 6, 11)

**Induction template.**

1. Base case: check the smallest n (check it carefully: 3^n > 2n+1 fails at n=1, so the base is n=2).
2. Induction hypothesis: assume the statement for an arbitrary fixed k ≥ base.
3. Induction step: prove it for k+1 using the hypothesis. For sums, T(k+1) = T(k) + P(k+1).
4. Conclude for all n ≥ base. Checking a few values proves nothing, since there are infinitely many n.

Solar panel example: P\_i = 3i+2 and T(n) = n(3n+7)/2. T(1)=5. Step: k(3k+7)/2 + (3k+5) = (k+1)(3k+10)/2.

Inequality example: 3^(k+1) = 3·3^k > 3(2k+1) = 6k+3 ≥ 2(k+1)+1 = 2k+3.

**Pigeonhole.** Pigeons are the items placed, holes are the categories.

- More than n items into n boxes: some box has at least 2.
- N items into n boxes: some box has at least ceil(N/n).
- To guarantee two share a box you need n+1 items (4 time-slots: 5 learners; 7 weekdays: 8 learners).
- 20 learners into 6 colours: the learners are the pigeons, the colours are the holes, and some colour has at least ceil(20/6) = 4.

**Recurrence relations.** A recurrence needs initial values so later terms can be computed.

| Model | Recurrence | Notes |
| --- | --- | --- |
| Compound interest | a\_n = (1+r) a\_(n−1) | a\_n = a\_0 (1+r)^n |
| Doubling | a(n) = 2a(n−1), a(0)=3 | a(n) = 3 · 2^n |
| Stair climbing (1 or 2 hops) | f(n) = f(n−1) + f(n−2), f(1)=1, f(2)=2 | f(3)=3, f(4)=5 |
| Fibonacci | F(n) = F(n−1) + F(n−2), F(1)=F(2)=1 | 1,1,2,3,5,8,13 so F(7)=13 |
| Binary strings with no two consecutive 0s | a(n) = a(n−1) + a(n−2), a(1)=2, a(2)=3 | a(3)=5, a(4)=8 (out of 2^4 = 16 total) |
| Tower of Hanoi | T(n) = 2T(n−1) + 1, T(1)=1 | T(n) = 2^n − 1 (4 disks: 15, 5 disks: 31) |
| Binary search | T(n) = T(n/2) + 1 | O(log n); 8 items: 3 guesses |
| Merge sort | T(n) = 2T(n/2) + n | O(n log n) |

**Characteristic equation.** For a(n) = c1 a(n−1) + c2 a(n−2), solve x² = c1 x + c2 for roots r1, r2. General solution a(n) = A r1^n + B r2^n, with A and B fixed by the initial values. For Fibonacci: x² − x − 1 = 0. For a(n) = 2a(n−1): root 2, so a(n) = A · 2^n.

**Big-O.** Drop constants and lower-order terms: 3n² + 5n + 2 is O(n²); 2^n − 1 is O(2^n).

Growth ladder, slowest to fastest: log n < n < n log n < n² < 2^n < n!.

## 5. Graph theory (Weeks 7, 8, 9)

**Walks and paths.**

| Term | Repeats allowed? |
| --- | --- |
| Walk | Vertices and edges may repeat (A,B,C,B,C) |
| Trail | Edges do not repeat; vertices may |
| Path | No repeated vertex |
| Cycle | Closed path: starts and ends at the same vertex, no other repeats |

- Connected: a path exists between every pair of vertices.
- Bridge: an edge whose removal disconnects the graph. Cut-vertex: a vertex whose removal disconnects it. In the museum graph (AB, BC, CD, DA, CE), CE is the bridge and C is the cut-vertex.
- Induced subgraph on a vertex set: those vertices and every original edge among them.
- Complete graph K\_n has C(n,2) edges. Complement has C(n,2) − |E| edges (7 islands, 10 routes: 21 − 10 = 11).

**Degrees.**

- Handshaking lemma: sum of degrees = 2|E|, so the number of odd-degree vertices is even. Degree sum 18 means 9 edges.
- Simple graph on n vertices: maximum degree is n−1 (so (5,2,2,1,0) is impossible on 5 vertices).
- Havel–Hakimi test for a graphic sequence: sort descending, remove the largest d, subtract 1 from the next d entries, repeat. A negative entry means not graphic; all zeros means graphic. Check the sum is even first ((4,2,1,0) has sum 7, so it fails).
- Same degree sequence does not imply isomorphic. A different degree sequence does imply not isomorphic.

**Euler and Hamilton.**

| Goal | Condition |
| --- | --- |
| Eulerian circuit (every edge once, return) | Connected and every vertex has even degree |
| Eulerian trail (every edge once, no return) | Connected and exactly two odd-degree vertices |
| Hamiltonian path or cycle (every vertex once) | No simple degree test; it is a separate question |

Sensor example: A–B, A–C, B–C, C–D, D–E has C and E odd, so no closed patrol.

**Planar graphs.** Euler's formula: V − E + F = 2 for a connected planar graph. With 7 vertices and 10 edges: F = 5.

**Bipartite and colouring.**

- Bipartite: vertices split into two groups with edges only between groups. Equivalent to having no odd cycle. Paths, trees and even cycles are bipartite; odd cycles and triangles are not.
- Chromatic number: the fewest colours for a proper colouring. A triangle needs 3, so any graph containing a triangle needs at least 3. A bipartite graph with an edge needs exactly 2.

**Representations.** The adjacency matrix of a simple undirected graph is symmetric with zeros on the diagonal; entry (i,j) = 1 means i and j are adjacent. Row sum = degree. A directed graph's out-degree counts arrows leaving a vertex.

**Isomorphism.** A bijection of vertices preserving adjacency. Necessary conditions: same number of vertices, edges and degree sequence (not sufficient).

**Counting with generating functions (Week 9).** Multiply one factor per item; the coefficient of x^n is the number of ways to take n units total.

| Item rule | Factor |
| --- | --- |
| At most once | 1 + x |
| Any number of times | 1/(1−x) = 1 + x + x² + ... |
| Even number of times | 1/(1−x²) |

The coefficient of x^0 is always 1 (the empty choice). Example: (1+x)(1+x) = 1 + 2x + x², so exactly one sauce can be chosen 2 ways. Choosing r units from k types with repeats: C(r+k−1, k−1), e.g. r=2, k=3 gives C(4,2) = 6.

## 6. Chromatic polynomials, partitions and groups (Week 12)

The Week 12 assignment shows no recorded answers, so the answers below are worked out from the definitions given.

**Chromatic polynomial** P(G,k) = the number of proper colourings of G with k colours. The chromatic number is the least k with P(G,k) > 0.

| Graph | P(G,k) | Chromatic number |
| --- | --- | --- |
| Complete K\_n | k(k−1)(k−2)...(k−n+1) | n |
| Path or tree on n vertices | k(k−1)^(n−1) | 2 |
| Cycle C\_n | (k−1)^n + (−1)^n (k−1) | 2 if n even, 3 if n odd |

Checks: K\_3 with k=3 gives 3·2·1 = 6. Path on 3 vertices: k(k−1)². C\_4: (k−1)^4 + (k−1), which factors as k(k−1)(k²−3k+3).

**Partitions of n** (sums of positive integers, order ignored). Partitions of 4: 4, 3+1, 2+2, 2+1+1, 1+1+1+1, so p(4) = 5.

- Distinct parts: 4 and 3+1, so 2.
- Odd parts only: 3+1 and 1+1+1+1, so 2.
- Euler's identity: for every n, the number of distinct-part partitions equals the number of odd-part partitions.

| Counting | Generating function |
| --- | --- |
| All partitions | 1/((1−x)(1−x²)(1−x³)...) |
| Distinct parts | (1+x)(1+x²)(1+x³)... |
| Odd parts | 1/((1−x)(1−x³)(1−x⁵)...) |

**Groups.** A group (G, ∗) satisfies four rules: closure, associativity, an identity e (a∗e = e∗a = a), and an inverse for every element (a∗a⁻¹ = e).

- The identity is unique, so a group has exactly one.
- Commutativity is not required.
- Integers under addition: a group, identity 0, inverse of a is −a (inverse of 7 is −7).
- Rotations of a square (0°, 90°, 180°, 270°) form a group of order 4.
- Integers under multiplication: not a group, because 2 has no integer inverse.
- Order = number of elements. Subgroup = a subset that is itself a group under the same operation.
- Lagrange's theorem: the order of a subgroup divides the order of the group. For order 12 the possible subgroup orders are 1, 2, 3, 4, 6, 12, so 5 cannot occur.

## 7. Practice questions, part 1: counting, sets, logic

Give a number or expression for each. Answers are in the key at the end.

- **Q1.** From 12 speakers, 4 are chosen and put in a speaking order. How many schedules?
- **Q2.** How many ways can a committee of 3 be chosen from 10 people?
- **Q3.** A passcode has 5 characters, each one of 26 letters, repeats allowed. How many passcodes?
- **Q4.** A plate has 2 distinct letters (from 26) followed by 3 digits (repeats allowed). How many plates?
- **Q5.** Seven mentors sit in a row. Two particular mentors must not sit together. How many arrangements?
- **Q6.** Six tasks are done in a line, and two named tasks must be consecutive. How many orders?
- **Q7.** How many distinct arrangements of the letters of BALLOON?
- **Q8.** Seven mentors sit at a round table. (a) How many seatings? (b) How many if two of them must sit together?
- **Q9.** Choose 2 guides from 6 seniors and 3 from 8 juniors. How many teams?
- **Q10.** A robot walks from (0,0) to (5,5) with right/up steps. (a) How many paths in all? (b) How many stay on or below the diagonal?
- **Q11.** (a) How many triangulations does a convex octagon have? (b) How many non-crossing pairings of 10 points on a circle?
- **Q12.** How many non-negative integer solutions does x + y + z + w = 10 have?
- **Q13.** How many non-negative solutions of x + y + z = 10 have every variable at most 5?
- **Q14.** How many derangements of 5 items are there?
- **Q15.** How many onto functions from 4 duties to 3 judges?
- **Q16.** In how many ways can 2 non-attacking rooks be placed on a 4×4 board?
- **Q17.** |A|=40, |B|=35, |C|=30, |A∩B|=15, |A∩C|=10, |B∩C|=12, |A∩B∩C|=5. Find |A ∪ B ∪ C|.
- **Q18.** If there are 90 students in total in Q17, how many are in none of A, B, C?
- **Q19.** In Q17, how many are in exactly two of the sets?
- **Q20.** In Q17, how many are only in A?
- **Q21.** In Q17, how many are in exactly one set?
- **Q22.** Simplify (A ∪ B)' ∩ A.
- **Q23.** Write the contrapositive of "If the alarm rings (A), the hall is evacuated (E)."
- **Q24.** Negate "the ID is valid (V) or the student is registered (R)".
- **Q25.** Is (p → q) ∧ p ∧ ¬q a tautology, a contradiction or a contingency?
- **Q26.** From p → q and ¬q, what follows and by which rule?
- **Q27.** For which truth values is p → q false?
- **Q28.** Is the set {p → q, p, ¬q} consistent?
- **Q29.** Show that p → (q → p) is a tautology by rewriting it with ¬ and ∨.

## 8. Practice questions, part 2: relations, functions, induction, pigeonhole

- **Q30.** On {1,2,3}, R = {(1,1),(2,2),(3,3),(1,2),(2,1)}. Which of reflexive, symmetric, antisymmetric, transitive hold? What are its equivalence classes?
- **Q31.** A relation on {1,2,3} has matrix rows \[1 1 0\], \[0 1 1\], \[0 0 1\]. Is it reflexive, antisymmetric, transitive? Which pair is missing for transitivity?
- **Q32.** Is "a divides b" on {1,2,3,6} a partial order? Is it an equivalence relation? Why?
- **Q33.** How many binary relations exist on a 3-element set?
- **Q34.** An equivalence relation on 5 elements has classes of sizes 3 and 2. How many ordered pairs does it contain?
- **Q35.** How many equivalence relations exist on a 4-element set?
- **Q36.** Which is a partition of {1,2,3,4,5}: (a) {{1,2},{3},{4,5}} or (b) {{1,2},{2,3},{4,5}}?
- **Q37.** Is f(x) = 2x from the integers to the integers injective? Surjective?
- **Q38.** Is f(x) = x² from the reals to the reals injective? Surjective?
- **Q39.** How many injective functions go from a 4-element set to a 6-element set?
- **Q40.** If f(x) = x + 1 and g(x) = 2x, find (g∘f)(x) and (f∘g)(x).
- **Q41.** Let d(n) = ceil(n/10) on positive integers. Find d(25) and d(40), and say whether d is injective.
- **Q42.** If f(a) = f(b) defines a \~ b, what kind of relation is \~ on the domain?
- **Q43.** Prove by induction that 1 + 2 + ... + n = n(n+1)/2 for all n ≥ 1.
- **Q44.** Prove by induction that the sum of the first n odd numbers is n².
- **Q45.** Prove by induction that 2^n > 2n for all n ≥ 3. Why does the base case start at 3?
- **Q46.** Among 53 people, at least how many share a birth month?
- **Q47.** What is the smallest number of students that guarantees 3 share the same weekday of birth?
- **Q48.** Show that among any 5 integers, two have the same remainder on division by 4.
- **Q49.** 100 items go into 7 boxes. Some box holds at least how many?

## 9. Practice questions, part 3: graphs, recurrences, chromatic, partitions, groups

- **Q50.** A graph has edges AB, BC, CA, CD, DE. Give every degree, the number of edges, all bridges and all cut-vertices.
- **Q51.** Is (3,3,2,2,2) a graphic sequence? Use Havel–Hakimi.
- **Q52.** Is (4,4,3,1,0) graphic? Give two different reasons.
- **Q53.** Which of K4 and K5 has an Eulerian circuit? Does K4 have an Eulerian trail?
- **Q54.** (a) Maximum edges in a simple graph on 8 vertices? (b) A graph on 8 vertices has 12 edges. How many edges does its complement have?
- **Q55.** A connected planar graph has 9 vertices and 14 edges. How many regions does a planar drawing have?
- **Q56.** Is C7 (a 7-cycle) bipartite? What is its chromatic number?
- **Q57.** Write the adjacency matrix of the path 1–2–3–4 and read off each degree.
- **Q58.** C6 and two disjoint triangles both have degree sequence (2,2,2,2,2,2). Are they isomorphic? What does this show about degree sequences?
- **Q59.** Find the coefficient of x³ in (1+x)²/(1−x).
- **Q60.** How many ways can 6 units be chosen from 3 item types with repeats allowed? Which formula, and what generating function describes one type taken an even number of times?
- **Q61.** Solve a(n) = 3a(n−1) with a(0) = 2. Find a(4).
- **Q62.** Binary strings of length n with no two consecutive 0s satisfy a(n) = a(n−1) + a(n−2), a(1)=2, a(2)=3. Find a(5).
- **Q63.** Solve a(n) = a(n−1) + 2a(n−2) with a(0)=1, a(1)=2 using the characteristic equation.
- **Q64.** How many moves does the Tower of Hanoi need for 6 disks?
- **Q65.** Order from slowest to fastest growth: n², n!, log n, 2^n, n log n.
- **Q66.** Find the chromatic polynomial of K4 evaluated at k=4, and its chromatic number.
- **Q67.** For C5, P(C5,k) = (k−1)^5 − (k−1). Evaluate at k=2 and k=3 and explain the k=2 result.
- **Q68.** List the partitions of 5. How many use distinct parts, and how many use only odd parts?
- **Q69.** Is the set of positive integers under addition a group? Is the set of non-zero reals under multiplication?
- **Q70.** A group has order 20. List the possible subgroup orders, and say whether a subgroup of order 8 can exist.
- **Q71.** Name the four group axioms and say which one fails for the integers under multiplication.

## 10. Answer key

**Part 1**

- **Q1.** P(12,4) = 12·11·10·9 = 11,880.
- **Q2.** C(10,3) = 120.
- **Q3.** 26^5 = 11,881,376.
- **Q4.** P(26,2) · 10^3 = 650 · 1000 = 650,000.
- **Q5.** 7! − 2·6! = 5040 − 1440 = 3600.
- **Q6.** 2 · 5! = 240.
- **Q7.** 7!/(2!·2!) = 1260 (L twice, O twice).
- **Q8.** (a) 6! = 720. (b) 2 · 5! = 240.
- **Q9.** C(6,2) · C(8,3) = 15 · 56 = 840.
- **Q10.** (a) C(10,5) = 252. (b) Catalan C\_5 = 42.
- **Q11.** (a) C\_6 = 132. (b) C\_5 = 42.
- **Q12.** C(13,3) = 286.
- **Q13.** C(12,2) − 3·C(6,2) = 66 − 45 = 21 (two variables at least 6 is impossible).
- **Q14.** D\_5 = 44.
- **Q15.** 3^4 − 3·2^4 + 3·1^4 = 81 − 48 + 3 = 36.
- **Q16.** C(4,2)² · 2! = 36 · 2 = 72.
- **Q17.** 40+35+30 − (15+10+12) + 5 = 105 − 37 + 5 = 73.
- **Q18.** 90 − 73 = 17.
- **Q19.** (15+10+12) − 3·5 = 22.
- **Q20.** 40 − 15 − 10 + 5 = 20.
- **Q21.** 73 − 22 − 5 = 46 (check: 20 + 13 + 13).
- **Q22.** The empty set, since A' ∩ B' ∩ A has A and A' together.
- **Q23.** ¬E → ¬A.
- **Q24.** ¬V ∧ ¬R.
- **Q25.** Contradiction: p and p → q force q, which clashes with ¬q.
- **Q26.** ¬p, by modus tollens.
- **Q27.** p true and q false.
- **Q28.** Inconsistent: p and p → q give q, but ¬q is also asserted.
- **Q29.** p → (q → p) ≡ ¬p ∨ ¬q ∨ p ≡ (¬p ∨ p) ∨ ¬q ≡ true.

**Part 2**

- **Q30.** Reflexive, symmetric and transitive; not antisymmetric because (1,2) and (2,1) both appear with 1 ≠ 2. It is an equivalence relation with classes {1,2} and {3}.
- **Q31.** Reflexive and antisymmetric, but not transitive: (1,2) and (2,3) are present, (1,3) is missing.
- **Q32.** It is a partial order (reflexive, antisymmetric, transitive). It is not an equivalence relation because it is not symmetric: 1 divides 2 but 2 does not divide 1.
- **Q33.** 2^9 = 512.
- **Q34.** 3² + 2² = 13.
- **Q35.** Bell number B\_4 = 15.
- **Q36.** (a). In (b) the element 2 lies in two blocks, so the blocks overlap.
- **Q37.** Injective yes; surjective no, because odd integers are never hit.
- **Q38.** Neither: f(2) = f(−2), and −1 is never an output.
- **Q39.** P(6,4) = 6·5·4·3 = 360.
- **Q40.** (g∘f)(x) = 2(x+1) = 2x + 2. (f∘g)(x) = 2x + 1. Composition is not commutative.
- **Q41.** d(25) = 3, d(40) = 4. Not injective: d(21) = d(30) = 3.
- **Q42.** An equivalence relation; its classes are the sets of inputs sharing an output.
- **Q43.** Base n=1: 1 = 1·2/2. Hypothesis: the sum to k equals k(k+1)/2. Step: k(k+1)/2 + (k+1) = (k+1)(k+2)/2.
- **Q44.** Base: 1 = 1². Hypothesis: sum of first k odds is k². Step: k² + (2k+1) = (k+1)².
- **Q45.** Base n=3: 8 > 6. Hypothesis: 2^k > 2k. Step: 2^(k+1) = 2·2^k > 4k ≥ 2k + 2 for k ≥ 1. The base starts at 3 because n=1 (2 > 2) and n=2 (4 > 4) are false.
- **Q46.** ceil(53/12) = 5.
- **Q47.** 2·7 + 1 = 15.
- **Q48.** The 5 integers are pigeons; the 4 possible remainders 0, 1, 2, 3 are holes, so two share a remainder.
- **Q49.** ceil(100/7) = 15.

**Part 3**

- **Q50.** Degrees A=2, B=2, C=3, D=2, E=1. Sum 10, so 5 edges. Bridges: CD and DE. Cut-vertices: C and D.
- **Q51.** Yes. (3,3,2,2,2) → (2,1,1,2) → sorted (2,2,1,1) → (1,0,1) → sorted (1,1,0) → (0,0). All zeros, so graphic.
- **Q52.** No. Havel–Hakimi: remove 4, subtract 1 from the next four to get (3,2,0,−1), which is negative. Also, two vertices of degree 4 on 5 vertices each touch every other vertex, so no vertex can have degree 0.
- **Q53.** K5 (all degrees 4). K4 has four odd-degree vertices, so it has neither a circuit nor a trail.
- **Q54.** (a) C(8,2) = 28. (b) 28 − 12 = 16.
- **Q55.** F = 2 − V + E = 2 − 9 + 14 = 7.
- **Q56.** Not bipartite (odd cycle). Chromatic number 3.
- **Q57.** Rows: \[0 1 0 0\], \[1 0 1 0\], \[0 1 0 1\], \[0 0 1 0\]. Degrees 1, 2, 2, 1 (row sums).
- **Q58.** Not isomorphic: C6 is connected and two triangles are not. Equal degree sequences are necessary but not sufficient.
- **Q59.** (1 + 2x + x²)(1 + x + x² + ...): coefficient of x³ is 1 + 2 + 1 = 4.
- **Q60.** C(6+3−1, 3−1) = C(8,2) = 28. Even-times factor: 1/(1−x²).
- **Q61.** a(n) = 2·3^n; a(4) = 162.
- **Q62.** a(3) = 5, a(4) = 8, a(5) = 13.
- **Q63.** x² − x − 2 = 0, roots 2 and −1. a(n) = A·2^n + B·(−1)^n. A + B = 1 and 2A − B = 2 give A = 1, B = 0. So a(n) = 2^n.
- **Q64.** 2^6 − 1 = 63.
- **Q65.** log n < n log n < n² < 2^n < n!.
- **Q66.** P(K4,4) = 4·3·2·1 = 24. Chromatic number 4.
- **Q67.** k=2 gives 1 − 1 = 0, so no proper 2-colouring exists (an odd cycle is not bipartite). k=3 gives 32 − 2 = 30.
- **Q68.** 5; 4+1; 3+2; 3+1+1; 2+2+1; 2+1+1+1; 1+1+1+1+1 (7 in all). Distinct parts: 5, 4+1, 3+2 (3). Odd parts only: 5, 3+1+1, 1+1+1+1+1 (3). Equal, as Euler's identity says.
- **Q69.** Positive integers under addition: not a group (no identity 0, no inverses). Non-zero reals under multiplication: a group (identity 1, inverse 1/a).
- **Q70.** Possible orders: 1, 2, 4, 5, 10, 20. A subgroup of order 8 cannot exist because 8 does not divide 20.
- **Q71.** Closure, associativity, identity, inverses. For integers under multiplication, inverses fail (2 has no integer inverse).
