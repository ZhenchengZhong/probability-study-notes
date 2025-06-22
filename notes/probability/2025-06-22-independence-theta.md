# Study Notes: Independence of Sigma-Fields Indexed by General Sets

Date: 2025-06-22
Textbook: Probability and Measure by Patrick Billingsley
Section: Section 4 – From Limit Sets (p.52) to Corollary 1 (p.55)

---

> **Note**:
> Today's focus is on understanding how the concepts of limit sets and basic probability identities evolve into formal definitions of independence among sigma-fields indexed by arbitrary sets.

## Content Logic

* We began by reviewing the fundamental limit set identities (Equations 4.4 and 4.5):

  * lim sup A\_n = intersection from n=1 to ∞ of union from k=n to ∞ of A\_k
  * lim inf A\_n = union from n=1 to ∞ of intersection from k=n to ∞ of A\_k
* These are essential in interpreting "infinitely often" and "eventually always" events in a probabilistic context.
* From there, we looked at Theorem 4.1, which relates the probability of the lim inf and lim sup of events A\_n to the lim inf and lim sup of their probabilities.
* This leads into a rigorous definition of independence, both for finite and infinite families of sets.
* Finally, we examined Theorem 4.2 and Corollary 1, where independence of pi-systems extends to their generated sigma-fields.

## Key Ideas

* A key probabilistic identity: If P(A\_n) = 0 for all n, then P(union A\_n) = 0; if P(A\_n) = 1 for all n, then P(intersection A\_n) = 1.
* These facts support interpretations of convergence and almost sure events in probability.
* Independence of events is first defined via products of probabilities for finite families (A and B), then extended to collections indexed by general sets Θ.

## Proof Sketch

* Theorem 4.2 proves that independence among finitely many pi-systems implies independence among their sigma-fields.
* Corollary 1 generalizes this: if A\_θ is a pi-system and the family {A\_θ : θ ∈ Θ} is independent (in the sense that every finite subfamily is independent), then the sigma-fields {σ(A\_θ)} are also independent.

## Questions & Confusions

* Does Theorem 4.2 hold if n is countably infinite? Answer: no. The theorem and its proof implicitly rely on n being a finite natural number.
* What exactly does the introduction of an index set Θ achieve? It gives us a unified language to describe families of sigma-fields that can be finite, countably infinite, or uncountable.

## Reflections

* Today’s reading starts from the fundamental probabilistic interpretation of limit sets and naturally builds toward abstract independence via sigma-field generation.
* The framework introduced with Θ helps clarify the structure of independence in infinite-dimensional settings, such as stochastic processes.

