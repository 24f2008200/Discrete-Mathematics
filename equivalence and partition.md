**The claim:** On any set X, equivalence relations and partitions are the same thing viewed two ways. Every equivalence relation determines a partition, every partition determines an equivalence relation, and these two constructions undo each other.

**Definitions**

- An **equivalence relation** ~ on X is reflexive (a ~ a), symmetric (a ~ b ⇒ b ~ a), and transitive (a ~ b, b ~ c ⇒ a ~ c).
- A **partition** of X is a collection of nonempty subsets (blocks) that are pairwise disjoint and whose union is X.

**Direction 1: equivalence relation ⇒ partition**

Given ~, define the equivalence class [a] = {x ∈ X : x ~ a}. The set of all classes is a partition:

- *Nonempty:* a ∈ [a] by reflexivity.
- *Cover X:* every a lies in its own class [a].
- *Disjoint or equal:* suppose [a] ∩ [b] ≠ ∅, say c ∈ both. Then c ~ a and c ~ b, so a ~ c (symmetry) and a ~ b (transitivity). For any x ∈ [a]: x ~ a, a ~ b, so x ~ b, hence x ∈ [b]. So [a] ⊆ [b], and by symmetry of the argument [b] ⊆ [a]. Thus [a] = [b].

So any two classes are either identical or disjoint.

**Direction 2: partition ⇒ equivalence relation**

Given a partition P, define a ~ b iff a and b lie in the same block.

- *Reflexive:* a is in its own block.
- *Symmetric:* "same block" is symmetric.
- *Transitive:* if a, b share a block B and b, c share a block B', then B and B' both contain b, so B = B' (blocks are disjoint), and a, c share that block.

The equivalence classes of this ~ are exactly the blocks of P.

**The two constructions are inverse**

- Start with ~, form the partition of classes, then form "same block" relation: a and b are in the same class iff a ~ b. You recover ~.
- Start with P, form "same block," then take classes: the class of a is the block containing a. You recover P.

So the map {equivalence relations on X} → {partitions of X} is a bijection.

**Examples**

- **Congruence mod n on ℤ:** a ~ b iff n | (a − b). The partition is the n residue classes {[0], [1], ..., [n−1]}. This is the foundation of ℤ/nℤ in number theory.
- **Equal parity on ℤ:** the partition is {evens, odds}.
- **Fibers of a function f: X → Y:** a ~ b iff f(a) = f(b). The blocks are the preimages f⁻¹(y). Every equivalence relation arises this way (take f to be the map a ↦ [a]).

**Non-example worth noting:** "|a − b| < 1" on ℝ is reflexive and symmetric but not transitive, so it doesn't give a partition; the neighborhoods overlap without coinciding.

**Quick verification in code**

```python
from itertools import product

X = range(-6, 7)
n = 3
rel = {(a, b) for a, b in product(X, X) if (a - b) % n == 0}

# relation -> partition
classes = {frozenset(x for x in X if (x, a) in rel) for a in X}

# partition -> relation
rel2 = {(a, b) for B in classes for a in B for b in B}

print("classes:", sorted(sorted(c) for c in classes))
print("disjoint:", all(c == d or not (c & d) for c in classes for d in classes))
print("covers X:", set().union(*classes) == set(X))
print("round trip recovers relation:", rel == rel2)
```

All three checks print `True`.
