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
