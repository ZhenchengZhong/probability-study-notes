# Study Notes: Example 6.6, Poisson’s theorem & Cantelli’s theorem  

Date: 2025-08-01  
Textbook: Billingsley – *Probability and Measure* (3rd ed.)  
Section: Chapter 6, pp. 89-90 (Examples 6.3 – 6.6; Problems 6.1 – 6.6)

---

> **Note**:  
> Today's focus is on finishing Example 6.6 and understanding why Poisson’s theorem and Cantelli’s theorem are natural corollaries of the strong law machinery developed earlier.

## Content logic
- Example 6.3 → variance estimates for permutation statistics  
- Example 6.6 → Borel–Cantelli + strong law to classify relative errors en(ω)  
- Problem 6.5 → Poisson’s theorem (independent indicator events)  
- Problem 6.6 → Cantelli’s theorem (zero-mean, fourth moment bounded)  

## Key ideas
- Replace analytic ε–δ bounds by probability-one statements using the strong law.  
- Exploit the independence of indicator variables to turn sums into expectations and variances easy to control.  
- Fourth-moment bound + Chebyshev + Borel–Cantelli ⇒ almost-sure convergence even without identical distribution.  

## Proof sketch

### Example 6.6 (relative error classification)
1. Set rn = −log2 xn.  
2. If Σ xn diverges, then Σ rn diverges, triggering the second Borel–Cantelli lemma.  
3. Hence P[ω : en(ω) ≤ xn infinitely often] = 1 when Σ xn diverges, and 0 when it converges.  
4. Translation: the set has Lebesgue measure 1 or 0 according to Σ xn.

### Poisson’s theorem (Problem 6.5)
- A_i independent.  
- N_n = Σ 1_{A_i}.  
- Var(N_n) = Σ p_i(1−p_i) ≤ n \bar p_n.  
- Chebyshev: P[|N_n/n − \bar p_n| ≥ ε] ≤ \bar p_n /(n ε²).  
- Sum over n finite ⇒ a.s. convergence by Borel–Cantelli.

### Cantelli’s theorem (Problem 6.6)
- S_n = Σ X_i, zero mean, E[X_i⁴] ≤ C.  
- Expand E[S_n⁴] = Σ E[X_i⁴] + 3Σ_{i≠j} E[X_i²]E[X_j²] ≤ 4C n².  
- Markov with fourth moment: P(|S_n| ≥ n ε) ≤ 4C /(n² ε⁴).  
- Series converges, apply Borel–Cantelli ⇒ S_n / n → 0 a.s.

## Questions & confusions
- Is there a sharper tail bound for Cantelli’s theorem without needing the fourth moment?  
- For permutation inversions (Example 6.3) the heuristic n² / 4 is clear; can one show a central limit theorem for S_n?

## Reflections
- Today’s material shows a pattern: once independence and a moment bound are available, Borel–Cantelli quickly converts probabilistic tail estimates into almost-sure convergence.  
- The leap from weak (in-probability) to strong (a.s.) results felt natural after internalising the machinery built in Sections 4–6.  
- Writing out the fourth-moment combinatorics by hand revealed why the coefficient 3 appears in E[S_n⁴].

