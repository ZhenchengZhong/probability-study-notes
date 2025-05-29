# Study Notes: Construction of Carathéodory Extension

Date: 2025-05-29  
Textbook: Probability and Measure (Third Edition), Patrick Billingsley  
Section: Section 3 – Existence and Extension (pp. 36–38)

---

> **Note**:  
> Today's focus is on the construction of outer measure and the definition of Carathéodory measurable sets, with the goal of extending a measure from a field to a σ-field.

## Content Logic

- We are given a measure P defined only on a field F₀ of subsets of Ω.
- The goal is to extend P to a full σ-field while preserving countable additivity.
- This is done in two main steps:
  - First, define an outer measure P* on all subsets of Ω.
  - Then, define a class of “good” sets (Carathéodory measurable sets) on which P* behaves like a true measure.

## Key Ideas

- **Outer measure construction**:
  For any A ⊆ Ω, define the outer measure by  
  P*(A) = inf { ∑ P(A_n) : A ⊆ ∪ A_n, A_n ∈ F₀ }

- **Inner measure**:  
  P_*(A) = 1 − P*(Aᶜ)

- **Carathéodory measurable sets**:
  A set A is said to be measurable if  
  P*(A ∩ E) + P*(Aᶜ ∩ E) = P*(E) for all E ⊆ Ω.  
  This means A can “cleanly” separate any set E without increasing the total outer measure.

- These measurable sets form a σ-field M, and P* restricted to M is a true measure.

## Proof Sketch

- Show that M is a σ-field:
  - The empty set is measurable.
  - M is closed under complementation: the defining condition is symmetric in A and Aᶜ.
  - M is closed under finite and countable unions: proven using subadditivity and induction.

- Show that P* is countably additive on M:
  - For disjoint A_i ∈ M, prove that  
    P*(∪ A_i) = ∑ P*(A_i)

- Show that F₀ ⊆ M:
  - Any set in the original field F₀ satisfies the Carathéodory condition due to the finite additivity of P and the way P* is constructed.

## Questions & Confusions

- Why does P*(A ∩ E) + P*(Aᶜ ∩ E) > P*(E) sometimes happen?
  - Because P* is only subadditive, not additive. If A is too “wild,” it may double-count parts of E when split, hence the inequality.
  - That’s exactly why we must restrict to measurable A to ensure countable additivity.

## Reflections

- This construction is elegant because it defines measurability not by how to measure A directly, but by whether A interacts “cleanly” with all other sets E.
- The Carathéodory condition becomes a filtering test: only sets that do not break measure additivity are admitted.
- It highlights a deep idea: measurable sets are not just those we want to measure, but those that won’t ruin other measurements.

