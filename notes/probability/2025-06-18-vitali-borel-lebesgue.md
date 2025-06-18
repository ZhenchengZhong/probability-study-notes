# Study Notes: Nonmeasurable Sets, Borel vs Lebesgue, and Vitali Construction

Date: 2025-06-18  
Textbook: Probability and Measure (3rd Edition), Patrick Billingsley  
Section: 3.14 – 3.18  

---

> **Note**:  
> Today's focus is on understanding the structure of nonmeasurable sets, the distinction between Borel and Lebesgue measurable σ-algebras, and the use of Vitali-type constructions in proving set-theoretic limitations under Lebesgue measure.

## Content Logic

- Explored how to construct a Lebesgue measurable set with measure zero that is not a Borel set (3.14)
- Defined Jordan content, inner and outer content, and the conditions under which they coincide (3.15)
- Investigated why Vitali sets are not even Lebesgue measurable, and how that implies they cannot be Borel (discussion and reflection)
- Used the Vitali construction to show that:
  - There exist subsets of Borel sets of measure zero that are not Borel themselves
  - Any set with positive outer measure contains a nonmeasurable subset (3.18b)
- Clarified the definition of inner measure λ_*(H) via Borel subsets only
- Reconfirmed that λ_*(H) = 0 follows immediately from the fact that all Borel subsets of H have λ = 0

## Key Ideas

- Borel σ-algebra is **not complete**: there exist subsets of Borel null sets that are not Borel.
- Lebesgue σ-algebra **is complete**: any subset of a null measurable set is still measurable.
- Vitali set construction relies on the axiom of choice to select one representative from each equivalence class modulo Q.
- Inner measure λ_*(H) is defined by:
  λ_*(H) = sup{ λ(A) : A ⊂ H, A ∈ Borel }
- If all such λ(A) = 0, then λ_*(H) = 0 immediately, regardless of whether H is measurable or not.

## Proof Sketch: 3.18(b)

- Assume λ^*(E) > 0.
- There exists an open interval I ⊂ E with λ(I) > 0.
- Construct a Vitali set V ⊂ [0,1].
- Apply an affine transformation f mapping [0,1] to I.
- Then f(V) ⊂ E and remains nonmeasurable.
- Hence, E contains a nonmeasurable subset.

## Questions & Confusions

- Is there any class of measurable sets strictly between Borel and Lebesgue σ-algebras that are practically useful?
- Can the Vitali construction be avoided with determinacy axioms (e.g., AD)?

## Reflections

- The power of the axiom of choice is striking in these constructions.
- Despite being nonconstructive, Vitali-type examples are critical in understanding why certain measure-theoretic systems cannot be complete or closed under subsets.
- Internalizing the role of inner and outer measure helps clarify the border between structure (Borel) and flexibility (Lebesgue).

