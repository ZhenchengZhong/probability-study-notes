# Study Notes: LLN-related Exercises 6.6 – 6.14  

Date: 2025-08-06  
Textbook: Probability and Measure, 3rd ed. (P. Billingsley)  
Section: Chapter 1, §6 Problems 6.6 – 6.14  

---

> **Note**:  
> Today’s focus is on understanding how various forms of the Law of Large Numbers, the Borel–Cantelli lemmas, and entropy appear across exercises; emphasis on English reading practice and keeping track of the logical chain rather than polishing every ε-δ detail.

## Content logic
- **6.6 Cantelli’s theorem** – bounded i.i.d. with zero mean and bounded 4th moment ⇒ n⁻¹ Sₙ → 0 almost surely.  
- **6.7 Deterministic & random sequences**  
  - (a) Bounded numbers with n⁻² sₙ² → 0 ⇒ n⁻¹ sₙ → 0.  
  - (b) Uniformly bounded r.v.’s with n⁻² Sₙ² → 0 a.s. ⇒ n⁻¹ Sₙ → 0 a.s. (no identical distribution needed).  
- **6.8 Weak SLLN via first Borel–Cantelli** – bounded independent with EXₙ = 0 ⇒ n⁻¹ Sₙ → 0 in probability.  
- **6.9 Elementary proof of Borel’s normal-number theorem** – revisit Section 1 using only interval unions and Cantelli-style ideas.  
- **6.10 Variance criterion** – show n⁻¹ Nₙ − αₙ → 0 a.s. when βₙ − αₙ² = O(1/n); identify βₙ − αₙ² → 0 as condition for the weak law.  
- **6.11 m-dependence** – bounded, zero-mean, m-dependent ⇒ n⁻¹ Sₙ → 0.  
- **6.12 Asymptotic relative frequency** – for an r-ary alphabet, empirical k-tuple frequencies converge to product of letter probabilities.  
- **6.13 Complete normality** – numbers whose base-b digit blocks of every length appear with frequency b⁻ᵏ form a Lebesgue-measure-1 set.  
- **6.14 Shannon’s Theorem** – for i.i.d. letters with probabilities p₁,…,pᵣ, show (-1/n) log pₙ(ω) → h = -Σ pᵢ log pᵢ a.s.; derive asymptotic equipartition property (AEP).

## Key Ideas
- Turn variance or fourth-moment bounds into almost-sure convergence via Borel–Cantelli or Kolmogorov SLLN.  
- For bounded deterministic sequences the Cesàro mean n⁻¹ sₙ is controlled by growth of partial-sum square sₙ².  
- Independence can be weakened to m-dependence once we chop into m + 1 independent subsequences.  
- Digit-frequency problems map to LLN for indicator variables of pattern occurrence.  
- AEP follows by applying the strong LLN to the information random variable -log p_{X₁}.  

## Proof Sketch (representative: 6.14)
1. Define Yₙ = -log p_{Xₙ}.  Independence ⇒ Yₙ i.i.d., EY₁ = h.  
2. Strong LLN: (1/n) Σ Yᵢ → h a.s.  
3. Observe -(1/n) log pₙ(ω) = (1/n) Σ Yᵢ(ω).  Combine with step 2.  
4. For AEP, fix ε > 0.  a.s. events imply for large n the empirical log-probability lies in [h − ε, h + ε].  Convert to probability bounds e⁻ⁿ⁽ʰ⁺ᵋ⁾ ≤ pₙ(ω) ≤ e⁻ⁿ⁽ʰ⁻ᵋ⁾.

## Questions & Confusions
- How tight is the O(1/n) variance requirement in 6.10 relative to Kolmogorov’s SLLN?  
- For complete normality (6.13) the classic proof uses a diagonal intersection over all bases b and block lengths k; is there a more direct entropy‐based argument?

## Reflections
Working through 6.6 – 6.14 reveals a common skeleton: translate a qualitative frequency statement into an LLN for bounded (or truncated) variables, then appeal to Borel–Cantelli or variance decay.  Writing the logic in plain English first helps me remember the flow; the exact ε-δ details can be filled in later once the roadmap is secure.
