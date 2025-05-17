# Study Notes: Cylinder Sets, Product Measure and Constructing Sigma Fields

Date: 2025-05-17
Textbook: Probability and Measure (3rd Edition), by Patrick Billingsley
Section: Chapter 2, pp. 25–30

---

> **Note**:
> Today's focus is on the formal construction of the product measure on sequence spaces, the recursive definition of cylinder set fields, and the method of building σ-fields from basic set classes.

---

## Content Logic

### - Introduction to sequence spaces S^∞

* Each ω in S^∞ is an infinite sequence (z₁(ω), z₂(ω), ...), where each z\_k(ω) ∈ S.
* When S = {0,1}, this sequence represents repeated outcomes of a simple experiment, such as coin tosses.
* The cylinder sets of rank n are defined as subsets of S^∞ constrained by the first n coordinates.

### - Field of cylinders ℰ₀ and product measure

* ℰ₀ consists of all cylinder sets of finite rank.
* ℰ₀ is a field: it is closed under finite unions and complements.
* A product measure P is defined on ℰ₀ by assigning probabilities to sequences, using
  P(\[z₁(ω), ..., z\_n(ω)] = (u₁, ..., u\_n)) = p\_{u₁} \* ... \* p\_{u\_n}.
* The measure is finitely additive and extended to countable additivity via Theorem 2.3.

### - Compactness and Lemma for countable additivity

* Lemma: If A\_n ↓ A, and A\_n are nonempty cylinders, then A ≠ ∅.
* Uses a diagonal argument and compactness of S^∞ to show that there exists a common limit point ω⁰.

---

## Key Ideas

* A σ-field is closed under complements and countable unions.
* The product measure on ℰ₀ mimics the logic of Lebesgue measure on dyadic intervals.
* Although ℰ₀ contains many important sets, it is not enough to generate the full Borel σ-field ℬ.

---

## Proof Sketch: Why P is countably additive on ℰ₀

* By verifying finite additivity first, and then using Lemma 2.3 to ensure that disjoint decreasing sequences of cylinders do not converge to an empty set without vanishing measure.
* Diagonalization provides a concrete construction of a limit point in the intersection of decreasing sets.

---

## Questions & Confusions

* Why construct ℐ\_n recursively instead of defining σ(ℐ₀) directly?

  * Answer: This helps analyze which operations are essential to reach σ(ℐ₀), and why countable operations are fundamentally necessary.
* Why the decomposition of intervals like (a, b] into nested unions and intersections?

  * This is a standard technique to approximate Borel sets via rational endpoints, making the structure manageable.

---

## Reflections

* The recursive construction of ℐₙ = ℐₙ₋₁\* and the diagonal lemma are deeply connected to compactness and closure properties in topology.
* Product measure construction on infinite Cartesian spaces mirrors the challenges faced in building Lebesgue measure on \[0,1].
* The transition from finite additivity to countable additivity hinges on compactness—a subtle but powerful idea.
