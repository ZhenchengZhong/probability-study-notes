# Study Notes: Countable Approximation and Natural Density

Date: 2025-05-25
Textbook: Billingsley – Probability and Measure (3rd Edition)
Section: Chapter 2 – Probability Measures (Problems 2.16–2.18)

---

> **Note**:
> Today's focus is on understanding how countable constructions allow us to apply foundational theorems like continuity from below, continuity from above, and countable additivity in measure theory, even when working in fields instead of σ-fields. We also explored the notion of natural density and its additive properties.

---

## Content Logic

### Problem 2.16(a) – Upward continuity beyond sequences

* The problem generalizes Theorem 2.1(i), which requires a countable increasing sequence.
* The challenge is that the collection {A\_t} indexed by t > 0 is uncountable.
* The core idea is to extract a countable subfamily {A\_{t\_n}} by choosing a sequence t\_n → ∞ (e.g., t\_n = n), and define B\_n := A\_{t\_n}.
* Since A = ∪*{t>0} A\_t = ∪*{n} B\_n, and the B\_n form a countable increasing sequence in the field F, we can apply Theorem 2.1(i) to conclude:

  P(A\_t) ↑ P(A) as t → ∞.

### Problem 2.16(b) – Downward continuity via intersection

* Mirrors the logic of (a), but in the decreasing setting.
* Define A := ∩\_{t>0} A\_t.
* Choose a decreasing sequence t\_n → 0+ and let B\_n := A\_{t\_n}. Then A = ∩\_n B\_n.
* This allows us to invoke Theorem 2.1(ii) (continuity from above) on the sequence {B\_n}, since each B\_n ∈ F and A ∈ F.
* Therefore, P(A\_{t}) ↓ P(A) as t → 0+.

### Problem 2.17 – Countable additivity under "almost disjointness"

* Assumes A\_n ∈ F, and A = ∪ A\_n ∈ F, with P(A\_m ∩ A\_n) = 0 for m ≠ n.

* The A\_n are not necessarily disjoint, so we cannot directly apply countable additivity.

* Solution: define B\_n := A\_n \ ∪\_{k\<n} A\_k, so that {B\_n} are pairwise disjoint and each B\_n ∈ F.

* Since P(A\_n) = P(B\_n) due to measure-zero overlaps, and A = ∪ B\_n, we get:

  P(A) = Σ P(B\_n) = Σ P(A\_n).

* This demonstrates that even in a field (not σ-field), we can recover countable additivity in special cases via careful disjointification.

### Problem 2.18(a) – Finite but not countable additivity of natural density

* Defines P\_n(A) = (1/n) × #{m ≤ n : m ∈ A}, and density D(A) = lim P\_n(A), if the limit exists.
* Let D be the class of sets with well-defined natural density.

**Step 1: Show finite additivity**

* If A, B ∈ D and A ∩ B = ∅, then:

  P\_n(A ∪ B) = P\_n(A) + P\_n(B) ⇒ D(A ∪ B) = D(A) + D(B)

**Step 2: Show not countably additive**

* Let A\_n = {k ∈ N : k ≡ n mod 2^n}, so that D(A\_n) = 1/2^n and A\_n are disjoint.
* Then Σ D(A\_n) = 1, but the union ∪ A\_n ⊊ N, so D(∪ A\_n) < 1.
* Hence D is not countably additive.

---

## Key Ideas

* Countable approximation is a universal strategy to bring uncountable collections into the scope of countable theorems (like Theorem 2.1).
* We often construct sequences (e.g., t\_n = 1/n or t\_n = n) to reduce uncountable index sets to sequences.
* The idea of "disjointification" is central when proving additivity in fields: redefine B\_n := A\_n \ ∪\_{k\<n} A\_k to get a disjoint family.
* Natural density D is a classical example of a set function that is finitely additive but not countably additive, illustrating subtle limitations in probabilistic set functions outside σ-additive frameworks.

---

## Questions & Confusions

* Why is the intersection used in 2.16(b) rather than union? (This is structurally required to match the downward convergence assumption.)
* The formal definition of disjointification and its relationship to measure-zero overlaps requires careful justification (but is manageable via P(A\_n \ B\_n) = 0).

---

## Reflections

* This was the first time I consciously recognized how theorems in analysis serve as "tools for interpreting structure." Instead of waiting to be applied, they define **frameworks we can actively reshape our problem to fit**.
* The idea is similar to embedding a real-world variable into a standardized measurement system: like evaluating intelligence via a standardized IQ test. The test isn't the property, but a system in which the property can be revealed and quantified.
