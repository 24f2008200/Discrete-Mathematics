[Counting](#c1)[Sets](#c2)[Logic](#c3)[Relations](#c4)[Functions](#c5)[Induction](#c6)[Pigeonhole](#c7)[Graphs](#c8)[Traps](#tr)

# Discrete Mathematics: Exam Study Sheet

Built from the 270 lecture transcripts (NPTEL, Prof. Sudarshan Iyengar, IIT Ropar). The course says it is "more than 50% counting", so expect counting questions in every chapter.

About 40 lectures (mostly Relations 143–155 and Functions 168–209) are video stills with no transcript text. For those topics I used the standard definitions, which match the course's examples where they appear.

## 1. Counting (Lectures 1–39)

Everything is built from the rule of sum and the rule of product. Permutations are ordered selections, combinations are unordered, and stars and bars handles selection with repetition. The binomial and multinomial theorems, Pascal's triangle and Catalan numbers are all consequences of these.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Sum / product rule | Either-or: m + n. Both together: m × n | "Pizza or burger" adds; "pizza and burger" multiplies. |
| Factorial | n! = n(n−1)…2·1, 0! = 1 | Arrangements of n distinct objects. 10! ≈ 3.6 million, 20! is astronomical. |
| Permutation | nPr = n!/(n−r)! | Order matters. Repeated letters: divide by k! (LEADER → 6!/2! = 360). |
| Combination | nCr = n!/(r!(n−r)!) = nPr/r! | Order does not matter. nC0 = nCn = 1. |
| Identities | nCr = nCn−r; nCr = n−1Cr + n−1Cr−1 | Second one is Pascal's rule. |
| Repetition (stars and bars) | Non-negative solutions of x1+…+xr = n: n+r−1Cr−1 (= n+r−1Cn) | n slots plus r−1 separators. 10 ice-creams, 3 flavours: C(12,2). 100 candies, 7 colours: C(106,6). |
| Binomial theorem | (a+b)n = Σj=0..n nCj an−j bj | rth term: Tr = nCr−1 an−r+1 br−1. Used to approximate (1.04)4 and to reach e. |
| Multinomial | Coefficient of x1n1…xknk in (x1+…+xk)n = n!/(n1!…nk!) | Splitting 36 girls into 4 labelled teams of 9: 36!/(9!)4. k = 2 gives the binomial theorem. |
| Pascal's triangle | Row n sums to 2n; row n reads 11n (small n); symmetric | Second diagonal is 1, 2, 3, …; each entry is the sum of the two above it. |
| Catalan numbers | Cn = (1/(n+1))·2nCn = 2nCn − 2nCn+1 | 1, 1, 2, 5, 14, 42, 132. Counts lattice paths (0,0)→(n,n) not crossing the diagonal, balanced parentheses, polygon triangulations, non-crossing handshakes. Proof: bad paths map to paths ending at (n−1, n+1) by flipping after the first crossing. |
| Counting strategy | Build a one-to-one correspondence to an easier set | Same idea reappears as bijections and power sets. |

## 2. Set Theory (Lectures 40–68)

Sets, subsets, union, intersection, complement, difference and symmetric difference. The main proof technique is double containment. The power set links back to the binomial theorem.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Element vs subset | ∅ ⊆ every set; ∅ ∈ {∅}; ∅ ∉ {0} | \|{∅}\| = 1; \|{a,{a,{b}}}\| = 2. Check whether an object is an element or a subset. |
| Inclusion–exclusion | \|A∪B\| = \|A\| + \|B\| − \|A∩B\| \|A∪B∪C\| = Σ\|singles\| − Σ\|pairs\| + \|A∩B∩C\| | Subtract the overcounted overlap. |
| Power set | \|P(A)\| = 2\|A\|; \|P(P(S))\| = 22^\|S\| | Subset ↔ n-bit binary string. Size-k subsets number nCk, so ΣnCk = 2n. |
| Complement | Ac = U − A | Needs a universal set U. |
| De Morgan (sets) | (A∪B)c = Ac∩Bc; (A∩B)c = Ac∪Bc | Use it to remove big complements when simplifying. |
| Proving X = Y | Show X ⊆ Y and Y ⊆ X (pick x, chase it) | One containment alone only shows "Y is bigger". |
| Set difference | A − B = A ∩ Bc | Usually A−B ≠ B−A, and the two are always disjoint. |
| Symmetric difference | A△B = (A−B)∪(B−A) = (A∪B) − (A∩B) | In exactly one of the two sets. |

## 3. Logic (Lectures 69–118)

A statement is a declarative sentence that is true or false (not a question, command or exclamation). Compound statements are built with NOT, AND, OR, XOR, → and ↔ and judged by truth tables. Equivalence and the laws of logic let you simplify without tables, and inference rules let you conclude from given truths.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Basic operators | ¬p flips; p∧q true only if both; p∨q false only if both false | Three-variable OR/AND: false/true only in the all-0 / all-1 row respectively. |
| Implication | p→q is false only when p = 1 and q = 0 | p→q ≡ ¬p ∨ q. Think "small set ⊆ big set" (born in New York → born in US). |
| Biconditional | p↔q ≡ (p→q) ∧ (q→p) | Same as "iff", "necessary and sufficient". |
| Converse / inverse / contrapositive | Converse: q→p. Inverse: ¬p→¬q. Contrapositive: ¬q→¬p | Only the contrapositive is equivalent to p→q. |
| XOR | p⊕q true iff exactly one is true | For three variables compute (p⊕q)⊕r. |
| Tautology / contradiction | Always true / always false | Example tautology: p → (p∨q). Implication fails only at 1→0, so show that case is impossible. |
| Satisfiability (SAT) | Is there an assignment making the formula true? | Easy to state, hard in general. Brute force is 2n rows. |
| Logical equivalence | Identical truth-table columns | Simplify using the laws below. |
| Laws of logic | Commutative, associative, distributive (∧ over ∨ and ∨ over ∧), idempotent (p∧p = p), identity (p∧T = p, p∨F = p), inverse (p∨¬p = T, p∧¬p = F), domination (p∨T = T, p∧F = F), absorption (p∨(p∧q) = p), double negation ¬¬p = p | Every law holds with ∧ and ∨ swapped (and T/F swapped). |
| De Morgan (logic) | ¬(p∧q) ≡ ¬p∨¬q; ¬(p∨q) ≡ ¬p∧¬q | Complement ↔ NOT, union ↔ OR, intersection ↔ AND. |
| Rules of inference | Modus ponens: p, p→q ⊢ q. Syllogism: p→q, q→r ⊢ p→r. Disjunctive: ¬p, p∨q ⊢ q | Do not conclude p from q and p→q. Technique: assume the conclusion is false, propagate 0/1 values, find a contradiction. |

## 4. Relations (Lectures 119–162)

A relation on A is a subset of A×A, shown as arrows, a 0/1 matrix, or a set of pairs. The course classifies relations by property and counts how many of each exist. Reflexive + symmetric + transitive gives an equivalence relation, which splits the set into disjoint classes.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Cartesian product | \|A×B\| = \|A\|·\|B\| | A relation from A to B is any subset of A×B. |
| All relations on n elements | 2n² | Each of the n² pairs is in or out. |
| Reflexive | (a,a)∈R for every a; matrix diagonal all 1 | Count: 2n²−n. One missing diagonal 1 kills it. |
| Symmetric | (a,b)∈R ⇒ (b,a)∈R; matrix equals its transpose | Count: 2n(n+1)/2 (free: diagonal + one triangle). Example: parallel lines, handshakes. |
| Antisymmetric | (a,b),(b,a)∈R ⇒ a = b | Diagonal free; each off-diagonal pair has 3 choices (neither, one way, other way). Count: 2n·3n(n−1)/2. Not the opposite of symmetric. |
| Transitive | (a,b),(b,c)∈R ⇒ (a,c)∈R | "Taller than" yes. Handshakes no. {(a,b): a+b = 0} is symmetric but not transitive. |
| Equivalence relation | Reflexive + symmetric + transitive | Examples: same birth month; a ≡ b (mod 4); (a,b)\~(c,d) iff ad = bc. |
| Partition | An equivalence relation splits the set into disjoint classes covering it | Any two classes are equal or disjoint. "A friend's friend is a friend" gives clusters. |

## 5. Functions (Lectures 163–209)

A function sends every domain element to exactly one codomain element. One-one, onto and bijective functions are tied to cardinality comparisons, and the course counts each kind. Composition chains functions, and an inverse exists exactly when the function is a bijection.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Function | f: X→Y; every x has exactly one image | Domain X, codomain Y, range = actual images. Codomain elements may be unused; domain elements may not. |
| One-one (injective) | f(a) = f(b) ⇒ a = b | Proof: assume equal outputs, derive equal inputs. If f: A→B is one-one then \|A\| ≤ \|B\|. |
| Onto (surjective) | For every y in codomain there is x with f(x) = y | Proof: pick y, produce x. If onto then \|A\| ≥ \|B\|. |
| Bijection | One-one and onto | Then \|A\| = \|B\|; a bijection proves equal size. To disprove, break either property. |
| Counting (\|A\| = m, \|B\| = n) | All functions: nm One-one: nPm = n!/(n−m)! Bijections (m = n): n! | Onto example: {a,b,c}→{1,2}: 2³ − 2 = 6 (remove the two constant maps). |
| Composition | (f∘g)(x) = f(g(x)) | Generally f∘g ≠ g∘f. With f = x²+1, g = 3x: g∘f = 3(x²+1), f∘g = (3x)²+1. |
| Inverse | f−1 exists as a function iff f is a bijection | Method: set y = f(x), solve for x. f(x) = 3x+2 gives f−1(y) = (y−2)/3. ⌊x⌋ is not invertible. |

## 6. Mathematical Induction (Lectures 210–232)

Induction is the domino argument: knock over the first domino, and make sure each one knocks over the next. It proves statements for all n, and the course applies it to sums, inequalities, divisibility, subsets and tiling.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Template | 1. Base: P(first n) true. 2. Hypothesis: assume P(k). 3. Step: prove P(k+1). | Base case = "kickstart", step = "ideal gap". Always state where the hypothesis is used. |
| Sum results | 1+2+…+n = n(n+1)/2 1+3+…+(2n−1) = n² 1+2+2²+…+2n = 2n+1 − 1 | Add the next term to both sides of P(k). |
| Inequalities | n \< 2n (n ≥ 1); n² > 2n+1 for n ≥ 3 | The second fails at n = 1, 2, so the base case is n = 3. |
| Divisibility | n³ − n is divisible by 3 | Rewrite (k+1)³−(k+1) in terms of k³−k. |
| Other applications | Every n > 1 is a product of primes; a set of n elements has 2n subsets; a 2n×2n board minus one square can be tiled by triominoes | Prime factorisation needs assuming P holds for all smaller values. Tiling splits into four 2k boards. |
| Pitfall | "All horses have the same colour" is a false proof | The step P(1)→P(2) fails. Verify the step works for small k, not just in general. |

## 7. Pigeonhole Principle (Lectures 233–248)

If more pigeons than holes, some hole holds two. The skill is choosing the pigeons and the holes, often by partitioning into pairs, remainders or regions.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Basic | n+1 pigeons in n holes ⇒ some hole has at least 2 | 8 people, 7 weekdays: two share a birth weekday. |
| Generalised | n pigeons in k holes ⇒ some hole has at least ⌈n/k⌉ | 50 coins to 10 daughters: someone gets at least 5. Proof by contradiction. |
| Remainders | Any n+1 integers contain two whose difference is a multiple of n | Holes are the n remainders mod n. |
| Pairing trick | Pick 51 of 1..100 ⇒ two are consecutive. Pick 5 of 1..8 ⇒ two sum to 9 | Holes: {1,2},{3,4},…; and {1,8},{2,7},{3,6},{4,5}. |
| Guarantee questions | Cards: 4 suits ⇒ 2·4+1 = 9 cards guarantee 3 of a suit. Initials: 27 people guarantee a repeated first letter | Worst case first, then add one. Dictation: 12 students, 10 possible error counts for 11 of them ⇒ a tie. |
| Geometry | 10 points in a unit equilateral triangle ⇒ two within distance 1/3 | Cut into 9 small triangles of side 1/3. |
| Friends | In any group of n people, two have the same number of friends | Degrees 0 and n−1 cannot both occur. Links to graphs. |

## 8. Graph Theory (Lectures 249–270)

The chapter opens with puzzles (six people, Königsberg bridges, three utilities, map colouring), then builds the basics: vertices, edges, degrees, the handshake lemma, Havel–Hakimi, regular graphs, and walks, trails and paths.

| Concept | Formula / statement | Remember |
| --- | --- | --- |
| Graph | G = (V, E); edge SR = RS | Vertices = nodes, edges = lines. |
| Degree sequence | List of all degrees, written in non-decreasing order | Example: 1,3,4,2,3,3 → 1,2,3,3,3,4. |
| Handshake lemma | Σv deg(v) = 2\|E\| | Each edge is counted at both ends. |
| Corollary | Every graph has an even number of odd-degree vertices | The sum is even. So \<1,1,1> is impossible. |
| Havel–Hakimi | Sorted d1 ≥ … ≥ dn is graphic iff removing d1 and subtracting 1 from the next d1 entries gives a graphic sequence | Re-sort and repeat. All zeros ⇒ graphic. A negative entry ⇒ not graphic. \<5,5,3,3,2,2,2> is graphic; \<5,5,5,5,2,2,2> is not (I ran the steps). |
| Regular / irregular | Regular: all degrees equal. Irregular: not regular | Irregular does not mean all degrees differ, and that is impossible anyway (pigeonhole). |
| Walk | Sequence of vertices and edges; repeats allowed | Widest notion. |
| Trail | Walk with no repeated edge (vertices may repeat) | u–a–c–e–d–c–v is a trail (c repeats). |
| Path | Walk with no repeated vertex | Implies no repeated edge. Path ⊂ trail ⊂ walk. A closed walk starts and ends at the same vertex. |

**Common exam traps**

- Add for "or", multiply for "and". Divide by k! when objects repeat.
- ∅ is a subset of every set but only an element if listed. Distinguish ∈ from ⊆.
- p→q is true when p is false. The converse and inverse are not equivalent to it.
- Antisymmetric is not "not symmetric". A relation can be both, or neither.
- State the domain and codomain before judging one-one, onto, or invertibility.
- In induction, check the base case start (n = 3 for n² > 2n+1) and that the step is valid for every k.
- Pigeonhole: define pigeons and holes explicitly, and use ⌈n/k⌉.

Generated from the course transcripts. Cross-check against your lecture slides before the exam.