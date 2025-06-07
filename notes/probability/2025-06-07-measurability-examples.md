# Study Notes: Measurability Examples and Outer Measure Definitions

Date: 2025-06-05
Textbook: Probability and Measure, Third Edition by Patrick Billingsley
Section: Chapter 3 (esp. Theorem 3.1, 3.2, and related exercises),pp.47

---

> **Note**:
> Today's focus is on examples of measurable and non-measurable sets on simple finite fields, outer and inner measure equality conditions, and the role of Carathéodory's criterion in defining measurability.

## Content Logic

This session revolves around how measurability is defined via outer and inner measure, and how those notions apply concretely in finite sample spaces. Through examples like P1 and P2 defined over Ω = {1,2,3}, I reviewed what it means for a set A to be measurable and how to verify it by checking the Carathéodory condition.

## Key Ideas

* In a finite space Ω = {1,2,3}, a field Ɵ\_0 = { ∅, {1}, {2,3}, Ω } is closed under finite union and complementation.
* For a finitely additive measure P\_1 on Ɵ\_0 with P\_1({1}) = 0 and P\_1({2,3}) = 1, we can extend outer measure P^\* to all subsets of Ω.
* Since there are only 8 subsets of Ω, measurability of each A ⊆ Ω can be checked via Carathéodory's condition: for all E ⊆ Ω, P^*(E) = P^*(E ∩ A) + P^\*(E ∩ A^c).
* In practice, it is sufficient to test A = {1} and A = {2,3}, since ∅ and Ω are trivially measurable.
* The measure of {1} being zero and the total measure of Ω being one imply that {2,3} must have measure one by additivity.

## Proof Sketch

* For each candidate A ∈ 2^Ω, check whether the Carathéodory condition holds.
* For A = {1} under P\_1, the outer measure of {1} is 0, and for any E, P^*(E) = P^*(E ∩ {1}) + P^\*(E ∩ {2,3}) always holds.
* Similarly, for A = {2,3}, outer measure is 1, and decomposition through intersections satisfies the measurability condition.
* Therefore, both {1} and {2,3} are measurable under P\_1. Same logic can be applied to P\_2 with appropriate value assignments.

## Questions & Confusions

* Why is it sufficient to only check Carathéodory condition for two sets ({1}, {2,3}) rather than all 8 subsets? Answer: other subsets either are combinations of measurable sets or trivially measurable (empty or full).
* Does field Ɵ\_0 being only a field (not σ-field) affect the outer measure definition? No, because outer measure is defined on 2^Ω regardless, and measurability is verified via Carathéodory.

## Reflections

This exercise helped ground the abstract definition of measurability in finite cases. It also clarified how outer and inner measure equality follows from measurability, not vice versa. The insight that P^*({1}) = 0 and P^*(Ω) = 1 directly implies P^\*({2,3}) = 1 under finite additivity is a useful shortcut. Also, the transition from a field Ɵ\_0 to the generated σ-field Ɵ does not change the basic strategy, since measurable sets in the completion can still be tested via Carathéodory.
