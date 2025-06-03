# Study Notes: Extension and Uniqueness of Probability Measures

Date: 2025-06-03  
Textbook: Patrick Billingsley, *Probability and Measure* (3rd Edition)  
Section: Chapter 3 – Existence and Extension (pp. 36–45)  

---

> **Note**:  
> Today's focus is on the extension of probability measures from fields to σ-fields, the uniqueness of such extensions, and the limitations imposed by nonmeasurable sets.

## Content logic

- The main goal of this section is to prove Theorem 3.1: that any countably additive probability measure on a field has a **unique extension** to the σ-field it generates.
- The first part is constructive: we define an **outer measure** and then identify a class of measurable sets where this outer measure behaves like a genuine probability.
- The second part deals with **uniqueness**, using the **π-λ theorem** and sometimes the monotone class theorem.
- Finally, the section concludes with examples of **nonmeasurable sets**, showing the fundamental limits of measure extension.

## Key Ideas

- A field of sets is not necessarily a σ-field. To make probability theory rigorous, we need to extend measures to σ-fields.
- The outer measure P* is defined by:

  P*(A) = inf ∑ P(A_n), where A ⊆ ∪ A_n and A_n ∈ F₀.

- A set A is considered measurable (P*-measurable) if for all E:

  P*(A ∩ E) + P*(A^c ∩ E) = P*(E)

- The collection of all P*-measurable sets forms a σ-field ℳ that contains F₀.
- When restricted to ℳ, P* is countably additive and agrees with P on F₀.
- Thus, P* is the unique extension of P from F₀ to σ(F₀).

## Proof Sketch

- Construct outer measure P* using coverings by sets from the field.
- Define inner measure P_* = 1 - P*(A^c).
- If P*(A) = P_*(A), then A is measurable.
- Define ℳ to be the set of such measurable sets.
- Show ℳ is a σ-field, and P* restricted to ℳ is countably additive.
- Use π-λ theorem (Theorem 3.2) to prove uniqueness:
  - If two probability measures agree on a π-system, they agree on σ(π).
- Use Lemmas 1–5 to establish closure properties, countable additivity, and agreement with original measure P.

## Questions & Confusions

- How essential is the use of countable additivity in ensuring that outer and inner measures match?
- In practice, how do we verify that a set is P*-measurable without going through the full (A ∩ E) decomposition?

## Reflections

- This section formalizes something intuitively obvious: we often want to assign probabilities to more sets than we initially define.
- But the process is delicate: without care, we could end up with contradictions (as shown later with Vitali sets).
- The π-λ theorem is surprisingly powerful — it reduces the burden of verifying equality of two measures to a small core class of sets.
- The later discussion on nonmeasurable sets is a useful philosophical reminder: not all subsets are safe to assign probabilities to, especially under the axiom of choice.

