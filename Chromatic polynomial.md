The chromatic polynomial of a graph tells us the number of ways to colour its vertices using $k$ available colours, such that no two adjacent vertices have the same colour.

It is written as $P_G(k)$, where $G$ is the graph.

## 1. Start with a simple graph

[Map Reduce and Its Applications. Tl;dr: This blog delves into the major… | by Distributed Systems | Medium](https://images.openai.com/static-rsc-4/6hqF1nLVt6MRvmiAcqNAqjOitoMskilpsu5P_PsKaqACBu-rlJ_ioXMPatnC_-ODmF3NrwJM0WPAE0mCzYzQLdWeiUbrAJMn-iWzLqZRdgc9WqtbXsRRFrdm6amymVQRFsjoVB8CXlapgttnHNooPvOv6-AOEPJrle2PMY0x0Ro?purpose=inline)

[medium.com](https://medium.com/%40distributed.systems.blogs/map-reduce-and-its-applications-87502bf48625)

Consider a triangle graph: three vertices, each connected to the other two.

Suppose we have $k$ available colours.

- First vertex: $k$ choices.
- Second vertex: $k-1$ choices, because it is adjacent to the first.
- Third vertex: $k-2$ choices, because it is adjacent to both the first and second.

Therefore,

$$ \boxed{P_G(k)=k(k-1)(k-2)} $$

For example, with 4 available colours,

$$ P_G(4)=4\times3\times2=\boxed{24} $$

So there are 24 valid colourings of the triangle.

## 2. Chromatic polynomials of common graphs

| Graph                          | Chromatic polynomial           |
| ------------------------------ | ------------------------------ |
| One isolated vertex            | $k$                        |
| Two vertices joined by an edge | $k(k-1)$                   |
| Path with $n$ vertices     | $k(k-1)^{n-1}$             |
| Complete graph $K_n$       | $k(k-1)(k-2)\cdots(k-n+1)$ |
| Cycle with $n$ vertices    | $(k-1)^n+(-1)^n(k-1)$      |

## 3. How do we use the polynomial?

The most important application is finding the chromatic number, denoted by $\chi(G)$.

The chromatic number is the minimum number of colours needed to colour the graph properly.

For a triangle,

$$ P_G(k)=k(k-1)(k-2) $$

- $P_G(1)=0$: one colour is insufficient.
- $P_G(2)=0$: two colours are insufficient.
- $P_G(3)=6$: three colours work.

Therefore,

$$ \boxed{\chi(G)=3} $$

Notice that $P_G(3)=6$ counts the number of valid colourings using the three available colours, while $\chi(G)=3$ gives the minimum number of colours required.

## 4. A useful formula for exams

If a graph has $n$ vertices, its chromatic polynomial has degree $n$. For a graph with at least one proper colouring, it counts the valid colourings for each positive integer $k$.

A useful method for deriving chromatic polynomials is deletion–contraction:

$$ \boxed{P_G(k)=P\_{G-e}(k)-P\_{G/e}(k)} $$

where:

- $G-e$: remove an edge $e$.
- $G/e$: contract edge $e$, merging its endpoints into one vertex.

This formula is especially useful for graphs that are not simple paths or complete graphs.

Remember: The chromatic polynomial counts valid colourings; the chromatic number tells you the minimum number of colours needed.
