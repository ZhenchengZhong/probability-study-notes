# Study Notes: Nonmeasurable Sets and Denumerable Probabilities

Date: 2025-06-20  
Textbook: Probability and Measure by Patrick Billingsley (3rd Edition)  
Section: Exercises 3.19–3.21, Chapter 4 pp. 51–52  

---

> **Note**:  
> Today's focus is on constructing nowhere dense sets with positive measure, understanding the impossibility of translation-invariant probability measures on all subsets of (0,1), and reviewing foundational chain rule and conditional probability formulas.

## Content logic

The study began with Exercise 3.19, which constructs a Borel set A ⊂ (0,1) such that 0 < λ(A ∩ G) < λ(G) for every nonempty open G ⊂ (0,1). The construction uses:

- Nowhere dense sets with positive measure
- Countably many disjoint Borel subsets Aₙ, Bₙ ⊂ Iₙ, where {Iₙ} enumerates rational open intervals

Exercises 3.20 and 3.21 move to show that:

- No Borel set A ⊂ (0,1) can have λ(A ∩ I) simultaneously bounded above and below by fixed ratios of λ(I)
- Not every subset of (0,1) is Lebesgue measurable

The justification uses the First Impossibility Theorem: no translation-invariant probability measure can be defined on all subsets of (0,1). This is proven via Vitali set constructions, using the axiom of choice.

The session concluded with the opening of Chapter 4, focusing on the general structure of probability spaces and foundational formulas.

## Key Ideas

- Positive-measure nowhere dense sets exist and can be packed into any open interval.
- Borel sets cannot uniformly approximate open intervals both above and below in measure.
- The Vitali set is a classic example of a nonmeasurable subset of (0,1).
- Translation invariance and the axiom of choice together yield paradoxes in measure theory.
- The unit interval (0,1] under Lebesgue measure serves as a canonical probability space.

## General Formulas

If P(A) > 0, the conditional probability is defined as:

P(B | A) = P(A ∩ B) / P(A)

From this, we obtain the chain rule:

P(A ∩ B) = P(A) P(B | A)  
P(A ∩ B ∩ C) = P(A) P(B | A) P(C | A ∩ B)

If {Aₙ} partitions Ω, the law of total probability gives:

P(B) = ∑ₙ P(Aₙ) P(B | Aₙ)

These hold for any probability space (Ω, 𝔽, P) and are used repeatedly in measure-theoretic proofs.

## Proof Sketch: Impossibility of full-measure translation-invariance

Assume a translation-invariant probability measure P exists on 2^{(0,1)}. Use the axiom of choice to select a Vitali set V containing one representative from each equivalence class under x ∼ y iff x - y ∈ Q.

Then the translated sets V + q for q ∈ Q ∩ [0,1) are disjoint, each with measure P(V). But their union lies in (0,2) and is uncountable, which leads to a contradiction if P(V) > 0, or an inconsistency if P(V) = 0 but they cover (0,1). Thus, no such P can exist.

## Reflections

- Exercises 3.19–3.21 shift the perspective from constructive measure examples to limitations of the theory.
- These results deepen understanding of what makes a set measurable and how measure interacts with translation and structure.
- The transition to Chapter 4 grounds the abstract measure space in a consistent probabilistic framework.

