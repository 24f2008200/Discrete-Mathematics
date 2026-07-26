Here is the step-by-step solution and explanation for each question in the **Week 2 Assignment**.

---

## Case Study 1: HealthPlus Student Wellness Survey

### **Given Data:**

* $\vert{}G\vert{} = 72$, $\vert{}C\vert{} = 58$, $\vert{}N\vert{} = 50$
* $\vert{}G \cap C\vert{} = 30$, $\vert{}G \cap N\vert{} = 26$, $\vert{}C \cap N\vert{} = 22$
* $\vert{}G \cap C \cap N\vert{} = 10$

---

### **Breakdown by Regions (Venn Diagram Regions):**

1. **All three services:**
* $\text{Only } (G \cap C \cap N) = 10$


2. **Exactly two services:**
* $\text{Only } (G \cap C)Here are the step-by-step solutions for all 20 questions in the **Week 2 : Assignment 2** quiz on set theory.



---

## Case Study 1: HealthPlus Student Wellness Survey

**Given Data:**

* $\vert{}G\vert{} = 72, \quad \vert{}C\vert{} = 58, \quad \vert{}N\vert{} = 50$
* $\vert{}G \cap C\vert{} = 30, \quad \vert{}G \cap N\vert{} = 26, \quad \vert{}C \cap N\vert{} = 22$
* $\vert{}G \cap C \cap N\vert{} = 10$

---

### Question 1

**How many students used at least one of the three wellness services?**

Using the Inclusion-Exclusion Principle:


$$\vert{}G \cup C \cup N\vert{} = (\vert{}G\vert{} + \vert{}C\vert{} + \vert{}N\vert{}) - (\vert{}G \cap C\vert{} + \vert{}G \cap N\vert{} + \vert{}C \cap N\vert{}) + \vert{}G \cap C \cap N\vert{}$$

$$\vert{}G \cup C \cup N\vert{} = (72 + 58 + 50) - (30 + 26 + 22) + 10$$

$$\vert{}G \cup C \cup N\vert{} = 180 - 78 + 10 = 112$$

* **Correct Answer:** **112**

---

### Question 2

**How many students used only Gym Access?**

The formula for students using *only* $G$ is:


$$\text{Only } G = \vert{}G\vert{} - \vert{}G \cap C\vert{} - \vert{}G \cap N\vert{} + \vert{}G \cap C \cap N\vert{}$$

$$\text{Only } G = 72 - 30 - 26 + 10 = 26$$

* **Correct Answer:** **26**

---

### Question 3

**How many students used exactly two of the three wellness services?**

To find those using exactly two services, subtract three times the intersection of all three from the pairwise intersections:


$$\text{Exactly two} = (\vert{}G \cap C\vert{} + \vert{}G \cap N\vert{} + \vert{}C \cap N\vert{}) - 3 \times \vert{}G \cap C \cap N\vert{}$$

$$\text{Exactly two} = (30 + 26 + 22) - 3 \times 10 = 78 - 30 = 48$$

* **Correct Answer:** **48**

---

### Question 4

**How many students used exactly one wellness service?**

First, calculate students using only each service:

* **Only $G$:** $72 - 30 - 26 + 10 = 26$
* **Only $C$:** $58 - 30 - 22 + 10 = 16$
* **Only $N$:** $50 - 26 - 22 + 10 = 12$

$$\text{Exactly one} = 26 + 16 + 12 = 54$$

Alternatively: $\text{At least one} - \text{Exactly two} - \text{Exactly three} = 112 - 48 - 10 = 54$.

* **Correct Answer:** **54**

---

### Question 5

**Let $A$ be the set of students who used Gym Access and Counseling Support ($A = G \cap C$), and let $B$ be the set of students who used Counseling Support and Nutrition Guidance ($B = C \cap N$). What is $\vert{}A \cup B\vert{}$?**

* $\vert{}A\vert{} = \vert{}G \cap C\vert{} = 30$
* $\vert{}B\vert{} = \vert{}C \cap N\vert{} = 22$
* $\vert{}A \cap B\vert{} = \vert{}G \cap C \cap N\vert{} = 10$

Applying Inclusion-Exclusion for two sets:


$$\vert{}A \cup B\vert{} = \vert{}A\vert{} + \vert{}B\vert{} - \vert{}A \cap B\vert{} = 30 + 22 - 10 = 42$$

* **Correct Answer:** **42**

---

### Question 6

**Students who used all three wellness services are eligible for special focus groups. How many non-empty focus groups can be formed from these 10 students?**

The total number of subsets (including the empty set) of a 10-element set is $2^{10}$. Subtracting the empty group yields:


$$2^{10} - 1$$

* **Correct Answer:** **$2^{10} - 1$**

---

### Question 7

**Which statement correctly represents students who used Gym Access but not Nutrition Guidance?**

The set difference $G - N$ defined as elements in $G$ and not in $N$.

* **Correct Answer:** **$G - N$**

---

### Question 8

**Which of the following is a correct De Morgan’s law?**

De Morgan's law states that the complement of the union of two sets is the intersection of their complements:


$$(G \cup C)' = G' \cap C'$$

* **Correct Answer:** **$(G \cup C)' = G' \cap C'$**

---

### Question 9

**How many students used Counseling Support only?**

$$\text{Only } C = \vert{}C\vert{} - \vert{}G \cap C\vert{} - \vert{}C \cap N\vert{} + \vert{}G \cap C \cap N\vert{}$$

$$\text{Only } C = 58 - 30 - 22 + 10 = 16$$

* **Correct Answer:** **16**

---

### Question 10

**Which expression represents students who used either Gym Access or Nutrition Guidance, but not Counseling Support?**

Students using Gym Access or Nutrition Guidance form the set $G \cup N$. Excluding those who used Counseling Support ($C$) gives:


$$(G \cup N) - C$$

* **Correct Answer:** **$(G \cup N) - C$**

---

---

## Case Study 2: CitySkill Digital Learning Program

**Given Data:**

* Total students $U = 160$
* $\vert{}V\vert{} = 95, \quad \vert{}Q\vert{} = 85, \quad \vert{}D\vert{} = 70$
* $\vert{}V \cap Q\vert{} = 45, \quad \vert{}V \cap D\vert{} = 35, \quad \vert{}Q \cap D\vert{} = 30$
* $\vert{}V \cap Q \cap D\vert{} = 20$
* Shortlisted mentors = 9

---

### Question 11

**How many students used at least one digital learning tool?**

Applying Inclusion-Exclusion Principle:


$$\vert{}V \cup Q \cup D\vert{} = (\vert{}V\vert{} + \vert{}Q\vert{} + \vert{}D\vert{}) - (\vert{}V \cap Q\vert{} + \vert{}V \cap D\vert{} + \vert{}Q \cap D\vert{}) + \vert{}V \cap Q \cap D\vert{}$$

$$\vert{}V \cup Q \cup D\vert{} = (95 + 85 + 70) - (45 + 35 + 30) + 20$$

$$\vert{}V \cup Q \cup D\vert{} = 250 - 110 + 20 = 160$$

* **Correct Answer:** **160**

---

### Question 12

**How many students used none of the three digital learning tools?**

$$\text{None} = \text{Total students} - \vert{}V \cup Q \cup D\vert{} = 160 - 160 = 0$$

* **Correct Answer:** **0**

---

### Question 13

**How many students used exactly two of the three tools?**

$$\text{Exactly two} = (\vert{}V \cap Q\vert{} + \vert{}V \cap D\vert{} + \vert{}Q \cap D\vert{}) - 3 \times \vert{}V \cap Q \cap D\vert{}$$

$$\text{Exactly two} = (45 + 35 + 30) - 3 \times 20 = 110 - 60 = 50$$

* **Correct Answer:** **50**

---

### Question 14

**How many students used only Video Lessons?**

$$\text{Only } V = \vert{}V\vert{} - \vert{}V \cap Q\vert{} - \vert{}V \cap D\vert{} + \vert{}V \cap Q \cap D\vert{}$$

$$\text{Only } V = 95 - 45 - 35 + 20 = 35$$

* **Correct Answer:** **35**

---

### Question 15

**How many different groups can be formed from the 9 shortlisted mentors (including the empty selection)?**

The total number of subsets of a set with 9 elements is:


$$2^9 = 512$$

* **Correct Answer:** **512**

---

### Question 16

**How many non-empty groups can be formed from the 9 shortlisted mentors?**

Subtracting the 1 empty subset gives:


$$2^9 - 1$$

* **Correct Answer:** **$2^9 - 1$**

---

### Question 17

**If every student who used Discussion Boards also used Video Lessons, so $D \subseteq V$, which complement relationship must be true?**

By the law of contrapositive / subset complement property, if $D \subseteq V$, taking complements reverses the inclusion direction:


$$V' \subseteq D'$$

* **Correct Answer:** **$V' \subseteq D'$**

---

### Question 18

**How many students used only Discussion Boards?**

$$\text{Only } D = \vert{}D\vert{} - \vert{}V \cap D\vert{} - \vert{}Q \cap D\vert{} + \vert{}V \cap Q \cap D\vert{}$$

$$\text{Only } D = 70 - 35 - 30 + 20 = 25$$

* **Correct Answer:** **25**

---

### Question 19

**Which expression represents students who used Practice Quizzes but did not use Video Lessons?**

The set of students in $Q$ and not in $V$ is represented by the set difference or intersection with complement:


$$Q \cap V' \quad (\text{or } Q - V)$$

* **Correct Answer:** **$Q \cap V'$**

---

### Question 20

**How many different 3-member committees can be selected from the 9 shortlisted mentors?**

Since the order of members in a committee does not matter, use combinations $C(n, k)$:


$$C(9, 3)$$

* **Correct Answer:** **$C(9, 3)$**
