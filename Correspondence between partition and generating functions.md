**The setup.** A partition of n is a way to write n as an unordered sum of positive integers, e.g. 4 = 3+1 = 2+2 = 2+1+1 = 1+1+1+1 (so p(4) = 5). This is different from the set partitions in the last question (see the end). The generating function packages the whole sequence p(0), p(1), p(2), ... into one formal power series, so that counting problems become algebra.

**Euler's product formula**

$$P(x)=\sum_{n\ge 0} p(n)x^n=\prod_{k\ge 1}\frac{1}{1-x^k}$$

**Why it works.** A partition is determined by how many times m_k each part size k is used. For a fixed k, the factor

$$\frac{1}{1-x^k}=1+x^k+x^{2k}+\cdots=\sum_{m_k\ge 0}x^{k\,m_k}$$

records "use k exactly m_k times" as the term x^{k m_k}. Multiplying all the factors and expanding, you pick one term from each factor, giving a multiplicity vector (m_1, m_2, ...), and the exponents add:

$$x^{1\cdot m_1}\cdot x^{2\cdot m_2}\cdots = x^{\,m_1+2m_2+3m_3+\cdots}$$

So the coefficient of xⁿ counts the vectors with Σ k·m_k = n, which are exactly the partitions of n. The product encodes the bijection "partition ↔ multiplicity vector."

**The dictionary: restrict the factors, restrict the partitions**

| Partitions of n where... | Generating function |
|---|---|
| parts from a set S | ∏_{k∈S} 1/(1−x^k) |
| all parts ≤ m | ∏_{k=1}^m 1/(1−x^k) |
| parts distinct | ∏_{k≥1} (1+x^k) |
| parts all odd | ∏_{k≥1} 1/(1−x^{2k−1}) |
| exactly m parts | xᵐ / ∏_{k=1}^m (1−x^k) |

The "distinct" case works because each size is used 0 or 1 times, which gives the factor 1 + x^k instead of a geometric series.

**Two classic theorems fall out of the algebra**

1. **Euler: #distinct-part partitions = #odd-part partitions.**

$$\prod_{k\ge1}(1+x^k)=\prod_{k\ge1}\frac{1-x^{2k}}{1-x^k}=\prod_{k\ge1}\frac{1}{1-x^{2k-1}}$$

The middle step uses 1 + x^k = (1 − x^{2k})/(1 − x^k). The even-indexed factors of the denominator then cancel against the numerator, leaving only odd k.

2. **Conjugation: #partitions with largest part m = #partitions with exactly m parts.** Flip the Ferrers diagram across its diagonal. The generating functions agree: the "exactly m parts" function is xᵐ/∏_{k≤m}(1−x^k), and subtracting one from each part leaves a partition with at most m parts.

**Pentagonal number theorem and a recurrence.** Since P(x) is a reciprocal, consider ∏(1 − x^k). Euler showed

$$\prod_{k\ge1}(1-x^k)=\sum_{j\in\mathbb Z}(-1)^j x^{j(3j-1)/2}=1-x-x^2+x^5+x^7-x^{12}-x^{15}+\cdots$$

Multiplying by P(x) gives 1, so comparing coefficients of xⁿ yields

$$p(n)=\sum_{j\ge1}(-1)^{j+1}\Big[p\big(n-\tfrac{j(3j-1)}{2}\big)+p\big(n-\tfrac{j(3j+1)}{2}\big)\Big]$$

This is an O(n^{3/2}) way to compute p(n).

**Quick verification in code**

```python
def series(N, parts, distinct=False):
    c = [1] + [0] * N
    for k in parts:
        if distinct:                       # multiply by (1 + x^k)
            for n in range(N, k - 1, -1):
                c[n] += c[n - k]
        else:                              # multiply by 1/(1 - x^k)
            for n in range(k, N + 1):
                c[n] += c[n - k]
    return c

def brute(n, maxpart=None, distinct=False, odd=False):
    """Count partitions of n directly."""
    if maxpart is None:
        maxpart = n
    if n == 0:
        return 1
    total = 0
    for k in range(min(n, maxpart), 0, -1):
        if odd and k % 2 == 0:
            continue
        total += brute(n - k, k - 1 if distinct else k, distinct, odd)
    return total

N = 20
P        = series(N, range(1, N + 1))
distinct = series(N, range(1, N + 1), distinct=True)
odd      = series(N, range(1, N + 1, 2))

print("p(n):", P[:11])
print("matches brute force:",
      all(P[n] == brute(n) for n in range(N + 1)))
print("distinct matches brute force:",
      all(distinct[n] == brute(n, distinct=True) for n in range(N + 1)))
print("Euler (distinct == odd):", distinct == odd)

# pentagonal recurrence
p = [1] + [0] * N
for n in range(1, N + 1):
    s, j = 0, 1
    while j * (3 * j - 1) // 2 <= n:
        sign = 1 if j % 2 else -1
        s += sign * p[n - j * (3 * j - 1) // 2]
        if j * (3 * j + 1) // 2 <= n:
            s += sign * p[n - j * (3 * j + 1) // 2]
        j += 1
    p[n] = s
print("pentagonal recurrence matches:", p == P)
```

The first line prints `[1, 1, 2, 3, 5, 7, 11, 15, 22, 30, 42]`, and the four checks print `True`.

**Connection to the previous topic.** Set partitions (the ones matching equivalence relations) are counted by Bell numbers, whose *exponential* generating function is exp(eˣ − 1). Integer partitions use an ordinary generating function because the parts are unlabeled; set partitions use an exponential one because the elements are labeled.
