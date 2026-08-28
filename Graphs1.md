These terms are easy to confuse because they differ mainly in **whether edges/vertices can repeat** and **whether the walk returns to its starting vertex**.

Let us use one graph throughout:

```text
        B
       / \
      A   C
       \ / \
        D---E
```

Edges are:

**AB, BC, CD, DA, CE, DE**

---

## 1. Walk

A **walk** is the most general concept.

* You can repeat **vertices**
* You can repeat **edges**
* No restriction on repetition

### Example

**A → B → C → B → A → D**

Here, vertex **B** is repeated and edge **AB** is effectively traversed in reverse.

Another example:

**A → B → C → D → A → B → C**

You are free to revisit vertices and edges.

### 🧠 Remember

> **Walk = Walk freely. Repeat anything.**

---

## 2. Trail

A **trail** is a walk in which **no edge is repeated**.

* Vertices **may** be repeated
* Edges **cannot** be repeated

### Example

**A → B → C → D → A → B**

Edges used:

**AB, BC, CD, DA, AB**

Oops! **AB is repeated**, so this is **NOT a trail**.

Instead:

**A → B → C → D → E → C**

Edges:

**AB, BC, CD, DE, EC**

No edge is repeated.

But notice that **C appears twice**.

Therefore, it is a **trail**.

### 🧠 Remember

> **Trail = No repeated Edges.**

---

## 3. Path

A **path** is a walk in which **no vertex is repeated**.

Consequently, edges cannot be repeated either.

### Example

**A → B → C → E**

Vertices:

**A, B, C, E**

All are different.

Therefore, it is a **path**.

But:

**A → B → C → D → A**

is **not a path**, because **A is repeated**.

### 🧠 Remember

> **Path = No repeated Vertices.**

This is the important distinction:

**Trail → don't repeat edges**

**Path → don't repeat vertices**

---

# 4. Closed Path

A **closed path** starts and ends at the **same vertex**.

For example:

**A → B → C → D → A**

It starts at **A** and ends at **A**.

However, terminology can vary between textbooks: some authors use "closed path" loosely, while others reserve **path** for a vertex-simple sequence and therefore call a closed vertex-simple structure a **cycle**.

So for exams, follow **your course's precise definition**.

---

# 5. Cycle

A **cycle** is essentially a **closed path** where:

* Start vertex = end vertex
* No other vertex is repeated
* Typically at least 3 vertices in a simple graph

### Example

**A → B → C → D → A**

Vertices:

**A, B, C, D, A**

Only the starting vertex **A** is repeated.

Therefore, this is a **cycle**.

Another cycle:

**C → D → E → C**

Again, only the starting/ending vertex **C** is repeated.

### 🧠 Remember

> **Cycle = Path that comes back home.**

---

# 6. Circuit

This is where students often get confused.

A **circuit** is a **closed trail**:

* Starts and ends at the same vertex
* **No edge is repeated**
* Vertices may be repeated

### Example

**A → B → C → D → E → C → D → A**

This is closed because it starts and ends at **A**.

If no edge is repeated, it is a **circuit**, even though **C and D may appear more than once**.

### 🧠 Remember

> **Circuit = Trail that comes back home.**

---

# The exam cheat sheet

| Term            | Repeated Edge? | Repeated Vertex?       | Closed?         |
| --------------- | -------------- | ---------------------- | --------------- |
| **Walk**        | ✅ Allowed      | ✅ Allowed              | Not necessarily |
| **Trail**       | ❌ No           | ✅ Allowed              | Not necessarily |
| **Path**        | ❌ No           | ❌ No                   | Not necessarily |
| **Closed walk** | ✅ Allowed      | ✅ Allowed              | ✅ Yes           |
| **Circuit**     | ❌ No           | ✅ Allowed              | ✅ Yes           |
| **Cycle**       | ❌ No           | ❌ No, except start=end | ✅ Yes           |

### The easiest way to memorize

Think of the hierarchy:

```text
WALK
 │
 ├── no repeated EDGE
 │       ↓
 │     TRAIL
 │       │
 │       └── closed
 │             ↓
 │          CIRCUIT
 │
 └── no repeated VERTEX
         ↓
       PATH
         │
         └── closed
               ↓
             CYCLE
```

Or even simpler:

> **Walk → anything can repeat**
> **Trail → edges cannot repeat**
> **Path → vertices cannot repeat**
> **Circuit → closed trail**
> **Cycle → closed path**

### ⭐ One exam trick

If you are given a sequence such as:

**A → B → C → D → B → E → A**

Ask these questions **in this order**:

1. **Does an edge repeat?**

   * Yes → not a trail.
   * No → it could be a trail.

2. **Does a vertex repeat?**

   * Yes → not a path.
   * No → it could be a path.

3. **Does it start = end?**

   * Yes → it is closed.
   * No → it is open.

That three-question test will solve most exam questions on these terms.
