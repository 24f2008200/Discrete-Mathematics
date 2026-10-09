I'm reading "%" as division (÷). Modulo is covered at the end.

**Groups**

| Set | Operation | Identity | Inverse of a |
|---|---|---|---|
| ℤ | + | 0 | −a |
| ℚ | + | 0 | −a |
| ℝ | + | 0 | −a |
| ℚ \ {0} | × | 1 | 1/a |
| ℝ \ {0} | × | 1 | 1/a |
| ℚ⁺ (positive rationals) | × | 1 | 1/a |
| ℝ⁺ (positive reals) | × | 1 | 1/a |
| {1, −1} ⊂ ℤ | × | 1 | itself |

All of these are abelian.

**Not groups**

| Set | Operation | Why it fails |
|---|---|---|
| ℤ, ℚ, ℝ | − | Not associative: (5−3)−1 = 1, but 5−(3−1) = 3. Also no two-sided identity: a−0 = a, but 0−a = −a. |
| ℤ, ℚ, ℝ | × | 0 has no inverse. |
| ℤ \ {0} | × | 0 is gone, but 2 still has no integer inverse (1/2 ∉ ℤ). Only ±1 are invertible. |
| ℤ | ÷ | Not closed: 1÷2 ∉ ℤ. Division by 0 is also undefined. |
| ℚ \ {0}, ℝ \ {0} | ÷ | Closed, but not associative: (8÷4)÷2 = 1, while 8÷(4÷2) = 4. No two-sided identity either: a÷1 = a, but 1÷a ≠ a. |
| ℕ = {0,1,2,…} | + | Associative with identity 0, but no inverses (no n with 3 + n = 0). It is a monoid, not a group. |

**Pattern:** subtraction and division fail because they are not associative. They are really "add the inverse" and "multiply by the inverse", so the group operations are + and ×, and − and ÷ just come from them.

**If you meant modulo**

- (ℤₙ, + mod n), the integers {0,…,n−1} with addition mod n, is a group for every n ≥ 1.
- (ℤₙ \ {0}, × mod n) is a group exactly when n is prime. For n = 6, 2 has no inverse mod 6.
- (ℤₙ*, × mod n), the elements coprime to n, is a group for every n.
