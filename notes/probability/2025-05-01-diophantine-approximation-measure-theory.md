# Study Notes: Diophantine Approximation and Measure Theory

Date: 2025-05-01  
Textbook: Probability and Measure by Patrick Billingsley  
Section: Chapter 1, pp. 13–15 – Diophantine approximation and negligible sets

---


> **Note**:  
> Today's focus is on understanding rational approximations of irrational numbers, the measure-theoretic nature of approximation sets, and how convergence of series determines their negligibility.

## Key Ideas

- Theorem 1.4 states that if x is irrational, there are infinitely many irreducible fractions p/q such that  
  |x − p/q| < 1/q².  
  This is a consequence of the pigeonhole principle applied to the fractional parts {q·x}.

- The quality of this approximation is optimal in the sense that |x − p/q| < 1/q² is always solvable infinitely often, but tightening it to |x − p/q| < 1/q^{2+ε} leads to only finitely many irreducible solutions for almost every x.

- The notion of “irreducible” is essential to exclude trivial rescaling (e.g. 2a/2b) that doesn’t yield fundamentally new approximations.

- Approximation speed is controlled by introducing a function φ(q), and the key convergence criterion becomes the series  
  Σ 1 / (q·φ(q)).

- Theorem 1.5 (Divergent Case): If φ is positive and nondecreasing and the series  
  Σ 1 / (q·φ(q)) = ∞,  
  then the complement of the set A_φ (of x satisfying |x − p/q| < 1 / (q²·φ(q)) infinitely often) is negligible.

- Theorem 1.6 (Convergent Case): If  
  Σ 1 / (q·φ(q)) < ∞,  
  then A_φ itself is negligible.

## Proof Sketch

- For Theorem 1.4, the idea is to divide [0, 1] into Q equal subintervals and apply the pigeonhole principle to the Q+1 fractional parts {q·x}.

- Two such fractional parts must fall in the same subinterval, leading to a pair of q's such that the difference between q₁·x and q₂·x is small. This leads to an irreducible approximation p/q satisfying the stated inequality.

- The finite case is extended to the infinite case via compactness arguments and the Heine-Borel theorem.

- For Theorem 1.5 and 1.6, we construct coverings of A_φ using intervals centered at p/q with radius 1 / (q²·φ(q)). If the total length of these intervals (summed over q and p) converges, then A_φ is a set of measure zero.

## Reflections

- The line between sets that are "negligible" and those that are not is drawn by the convergence or divergence of a carefully crafted series.

- It is interesting that truncating decimal or binary expansions of x leads to rational approximations with poor accuracy, even though they seem natural. Example 4.17 (to be read later) presumably illustrates this gap.

- The use of log(q) and log^{1+ε}(q) in φ(q) shows how slowly increasing functions still influence the measure structure of these approximation sets.

- This study reveals a deep interaction between number theory, real analysis, and probability theory, especially in how almost-everywhere properties are controlled by integrability.

