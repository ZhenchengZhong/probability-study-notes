# Study Notes: Strong Law vs Weak Law of Large Numbers

Date: 2025-04-27  
Textbook: Probability and Measure (Third Edition) - Patrick Billingsley  
Section: Chapter 1 - Strong Law Versus Weak Law

---

> **Note**:  
> Today's focus is on proof details, logical structure, and English reading practice.

## Key Ideas

- The strong law of large numbers (SLLN) is strictly stronger than the weak law (WLLN).
- (1.30) focuses on convergence in probability, controlling the behavior globally.
- (1.31) requires almost everywhere convergence, which is a much stronger condition.
- Proof strategy:
  - Define a positive sequence (ε_n) tending to 0 slowly, for example ε_n = n^(-1/8).
  - Ensure the series Σ ε_n^4 n^(-2) converges.
  - Define sets A_n = { ω : |n^(-1) s_n(ω)| ≥ ε_n }.
  - Estimate P(A_n) ≤ 3 ε_n^(-4) n^(-2) based on previous inequalities.
  - Show that Σ P(A_n) < ∞.
  - Cover N^c by the union of A_n for n ≥ m.
- As a result, the negligible complement of N is established, proving almost everywhere convergence.
- (1.30) being true does not imply (1.31) holds. There are counterexamples where (1.30) holds but (1.31) fails (Example 5.4).

## Proof Sketch

- Choose ε_n such that Σ ε_n^4 n^(-2) converges.
- Define A_n = { ω : |n^(-1) s_n(ω)| ≥ ε_n }.
- Estimate P(A_n) and ensure Σ P(A_n) < ∞.
- Show N^c ⊆ ⋃_{n=m}^∞ A_n.
- Decompose each A_n into a finite disjoint union of intervals I_{nk}, where Σ_k |I_{nk}| = P(A_n).
- Hence ⋃_{n=m}^∞ A_n becomes a countable union of intervals covering N^c.
- By the definition of negligibility, conclude that N^c is negligible.

## Reflections

- This section marks a significant shift from intuitive probability to rigorous measure-theoretic probability.
- Logical clarity is crucial: informal reasoning about convergence is not sufficient.
- Understanding the difference between convergence in probability and almost everywhere convergence is fundamental.
- Thinking of abstract results as "tools" helps reduce psychological resistance to complexity.
- This proof shows why strong law proofs are inherently harder and demand more structure than weak laws.


