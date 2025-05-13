# Study Notes: Properties of Probability Measures

Date: 2025-05-13  
Textbook: Probability and Measure (Patrick Billingsley, 3rd ed.)  
Section: Chapter 2, pp. 22–24

---

> **Note**:  
> Today's focus is on understanding the foundational properties of probability measures, including countable additivity, continuity from below and above, and how these properties interact in discrete probability spaces.

## Content logic

This section develops the theoretical structure of probability measures defined on a field or sigma-field. The initial goal is to define what it means for a set function P to qualify as a probability measure, and then to explore its implications and equivalent formulations.

The progression is as follows:

- Definition of a probability measure via three axioms:
  - Non-negativity: 0 ≤ P(A) ≤ 1
  - Normalization: P(∅) = 0, P(Ω) = 1
  - Countable additivity: For disjoint sets A₁, A₂, ..., we have P(⋃A_k) = ∑P(A_k)
- Deduction of basic properties:
  - Finite additivity as a special case of countable additivity
  - Monotonicity: A ⊆ B implies P(A) ≤ P(B)
  - Complement rule: P(Aᶜ) = 1 − P(A)
  - Inclusion–exclusion for unions of events
- Continuity properties:
  - From below: If Aₙ ↑ A, then P(Aₙ) ↑ P(A)
  - From above: If Aₙ ↓ A, then P(Aₙ) ↓ P(A)
- Countable subadditivity in the general case when A₁, A₂, ... are not disjoint

## Key Ideas

- Countable additivity implies finite additivity, but not vice versa.
- Continuity from below follows by constructing disjoint components Bₖ such that Aₙ = ⋃_{k=1}^n Bₖ.
- Continuity from above is proved by complementing the sequence and applying continuity from below.
- Countable subadditivity is a weaker property than countable additivity, and always holds for probability measures.

## Proof Sketch

- For continuity from below: Write Aₙ as increasing unions of disjoint pieces Bₖ = Aₖ \ Aₖ₋₁, and apply finite additivity.
- For continuity from above: Use Aₙ ↓ A ⇒ Aₙᶜ ↑ Aᶜ, then apply (i) and take complements.
- Countable subadditivity is shown by enlarging a disjoint decomposition to majorize a union of arbitrary (not necessarily disjoint) sets.

## Reflections

Although the properties discussed seem technical, they are essential for making probability theory analytically rigorous. In particular, the subtle difference between finite and countable additivity is foundational: it distinguishes naive definitions of probability from the formal measure-theoretic approach.

The inclusion-exclusion formula also bridges intuitive set operations with formal probability calculations. Its generalization shows how overlapping probabilities interact and why disjoint decomposition is often a powerful proof tool.

The examples on discrete probability spaces help to ground the abstract definitions in concrete, verifiable models. They demonstrate how continuity from above, combined with finite additivity, suffices to recover full countable additivity in many practical settings.

