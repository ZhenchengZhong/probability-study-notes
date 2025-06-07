# Study Notes: Outer and Inner Measure, Carathéodory Measurability

Date: 2025-06-07  
Textbook: Probability and Measure (3rd Edition, Patrick Billingsley)  
Section: Chapter 3 – Existence and Extension (p.47)

---

> **Note**:  
> Today's focus is on understanding the definitions and applications of outer and inner measure, as well as Carathéodory measurability. Exercises 3.2 and 3.3(a) were studied in depth, with a focus on identifying measurable sets through zero-measure logic rather than brute-force enumeration.

## Content logic

- Revisited the definitions of outer and inner measure:
  P*(A) = inf{ P(B) : A ⊆ B, B ∈ 𝔽 },
  P_*(A) = sup{ P(C) : C ⊆ A, C ∈ 𝔽 }.
- Understood that P*(A) and P_*(A) are constructed from approximations using only sets from the field 𝔽 (or 𝔽₀ if working pre-extension).
- Verified that infima and suprema in the above definitions are always achieved due to the finiteness or countability of Ω.

## Key Ideas

- A set A is Carathéodory measurable iff for every E ⊆ Ω,  
  P*(E) = P*(E ∩ A) + P*(E ∩ A^c).
- In finite Ω, this reduces to checking the equality over finitely many E ⊆ Ω.
- Zero-measure sets are always measurable. Their complements may or may not be measurable, depending on whether they are also zero-measure under the same outer measure.

## Proof Sketch

- In 3.2(b), showed that A is P*-measurable ⇔ P*(A) = P_*(A), by invoking Carathéodory's definition.
- In 3.2(c), established that once 𝔽 = σ(𝔽₀), the definitions of P*(A) and P_*(A) (via inf/sup over 𝔽₀) remain valid due to σ(𝔽₀)-closure under countable union/intersection.
- In 3.3(a), constructed two measures P₁ and P₂ on the same field 𝔽₀ such that:
  - P₁({1}) = 0, so {1} is a zero-measure set under P₁.
  - P₂({2,3}) = 0, so {2,3} is zero-measure under P₂.
- Therefore, {1} ∈ 𝔐(P₁^*) but {1} ∉ 𝔐(P₂^*), while the opposite holds for {2,3}.
- This directly implies that 𝔐(P₁^*) ≠ 𝔐(P₂^*).

## Questions & Confusions

- At first wondered whether proving P*(A) = P_*(A) automatically implies measurability, but clarified that it is equivalent only under Carathéodory's criterion.
- Clarified that although A ∉ 𝔽₀ in general, the infimum/supremum in P*(A), P_*(A) only range over 𝔽₀.
- Realized that full enumeration over all E ⊆ Ω is unnecessary when identifying differences between measurable families — it's sufficient to examine key zero-measure sets.

## Reflections

- This session provided a concrete understanding of how outer and inner measure bound unknown sets from both sides using known measurable approximators.
- Learned to rely on the behavior of zero-measure sets to quickly identify measurable sets and distinguish between measurable σ-fields.
- The exercise demonstrated that careful construction of P can lead to meaningful differences in the induced measurable σ-field even on the same base field 𝔽₀.
