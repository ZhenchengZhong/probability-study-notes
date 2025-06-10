# Study Notes: Outer Measure, Carathéodory Measurability, and Examples

Date: 2025-06-10  
Textbook: Probability and Measure (Third Edition), Patrick Billingsley  
Section: 3.3–3.5 (Page 47)

---

> **Note**:  
> Today's focus is on understanding outer measures, Carathéodory measurability, and how non-measurable sets can naturally arise through various constructions. We also practiced recognizing when an outer measure does not originate from a probability measure via the standard construction.

## Content logic

- Studied the definition of the outer measure P* as defined in (3.1).
- Compared this with the special outer measure f(λ*(A)) in Problem 3.4.
- Analyzed specific examples where P* fails to agree with P on the original field 𝓕₀.
- In 3.4, proved that f(λ*(A)) is an outer measure, but cannot be constructed via any probability measure P and field 𝓕₀ using (3.1).
- In 3.5, proved that the triple (Ω, 𝓕, P) forms a valid probability space, then constructed a non-measurable set A such that P_*(A) = 0 and P^*(A) = 1.

## Key Ideas

- Outer measure P* is constructed by infimum over countable covers from a field, while inner measure P_* is the supremum over subsets.
- A set is Carathéodory measurable (with respect to P*) iff for all E, we have:
  
  P^*(E) = P^*(E ∩ A) + P^*(E ∩ A^c)

- In Problem 3.4, using a concave function f such that f(0) = 0 and f strictly increasing, we constructed an outer measure not derived from any P via (3.1).
- The measurable sets under this f(λ*(A)) outer measure are extremely “thin”: only sets with λ*(A) = 0 or λ*(A^c) = 0 are measurable.
- In 3.5, we encountered a natural example where a horizontal line y = 1/2 has inner measure 0 but outer measure 1, illustrating non-measurability in a very intuitive way.

## Proof Sketch

### 3.4

- Showed f(λ*(A)) is nonnegative, monotone, and countably subadditive using properties of f and λ*.
- Used strict concavity of f to show that when both λ*(A) and λ*(A^c) are positive, the Carathéodory condition fails.
- Concluded that such an outer measure cannot come from (3.1), since it violates the additive structure required from a measure P.

### 3.5

- Defined Ω = (0,1]^2 and 𝓕 as vertical “strips” {(x,y): x ∈ A, y ∈ (0,1]}, with A ∈ 𝔅.
- Showed that (Ω, 𝓕, P) is a probability space by checking σ-algebra closure and countable additivity.
- Constructed A = {(x,y): y = 1/2} and showed:
  - No vertical strip fits inside A → P_*(A) = 0.
  - Countably many strips cover A → P^*(A) = 1.

## Questions & Confusions

- The concavity inequality f(∑λ*(A_n)) ≤ ∑f(λ*(A_n)) was at first counterintuitive—Jensen’s inequality in reverse was clarified with care.
- Why σ(𝓕₀) ⊆ 𝓜(P^*) needed to be clarified—resolved by realizing outer measure defines a larger class, and measurable sets only satisfy Carathéodory’s condition.

## Reflections

- The idea that f(λ*(A)) gives rise to an outer measure but is “too thin” to capture Lebesgue measurable sets was subtle and surprising.
- 3.5 was particularly illuminating: it visually demonstrates what a non-measurable set looks like—not artificial, but natural and geometric.
- I now better understand why outer measures do not always give rise to full σ-algebras of interest, and how measurability must be carefully defined.
