# Study Notes: Measurability, Inequalities, and Expectation-Minimization

Date: 2025-07-18  
Textbook: Probability and Measure by Patrick Billingsley  
Section: Problems 5.1 – 5.9

---

> **Note**:  
> Today's focus is on measurability conditions, Jensen and Schwarz inequalities, convexity-based inequalities (Cantelli, Chebyshev, Hölder), and expectation minimization.

---

## Problem 5.1 – Measurability and σ-fields

- (a) Showed that a random variable X is measurable w.r.t. σ-field 𝒢 iff σ(X) ⊆ 𝒢. Used the fact that σ(Y) generates minimal σ-field under which Y is measurable.
- (b) Proved that when 𝒢 = {∅, Ω}, any measurable X must be constant (since only trivial sets are measurable).
- (c) If every A ∈ 𝒢 has probability 0 or 1, and X is measurable w.r.t. 𝒢, then X is almost surely constant. Examples include tail σ-field or σ-field of countable-cocountable sets under Lebesgue measure.

## Problem 5.2 – Replacing the Unit Interval

- Discussed how in Theorem 5.3 (constructing an i.i.d. sequence with given distributions), the unit interval [0,1] can be replaced by any nonatomic probability space. This generalization leverages the richness of nonatomic spaces to support uniform random variables needed for inverse transform constructions.

## Problem 5.3 – Minimizer of Expected Squared Error

- Proved that m = E[X] minimizes E[(X − m)²].
- Used calculus: minimized function f(m) = E[(X − m)²] by taking derivative and setting f′(m) = 0.
- Also provided intuitive understanding: variance is minimized when centered at mean.

## Problem 5.4 – Sharpness of Chebyshev

- Constructed X taking values m−α, m, m+α with probabilities p, 1−2p, p.
- Showed that this leads to equality in Chebyshev’s inequality, hence the bound cannot be improved without additional assumptions on X (like symmetry or unimodality).

## Problem 5.5 – Cantelli’s Inequality and Comparison

- (a) Proved Cantelli's inequality:  
  P(X − m ≥ α) ≤ σ² / (σ² + α²), for α ≥ 0  
  via minimization over auxiliary parameter λ in E[(X − λ)²].
- (b) Derived two-sided version:  
  P(|X − m| ≥ α) ≤ 2σ² / (σ² + α²)
- (c) Constructed example with X taking two values to show equality is achieved ⇒ Cantelli's inequality is sharp.

## Problem 5.6 – Schwarz via Polynomial Positivity

- Considered function f(t) = E[(t|X| + |Y|)²], a quadratic in t.
- Since it has at most one real root ⇒ discriminant ≤ 0 ⇒  
  (E[|X||Y|])² ≤ E[|X|²] · E[|Y|²], which is Schwarz’s inequality.

## Problem 5.7 – Jensen-based Power Inequality

- (a) Rewrote (5.37) as:  
  E^{β/α} [ |X|^α ] ≤ E[ |X|^α ]^{β/α}  
  and derived this from Jensen's inequality using φ(z) = z^{β/α}, a convex function when β ≥ α.
- (b) Proved that  
  E[1 / X^p] ≥ 1 / (E[X])^p for p > 0 and X > 0  
  by applying Jensen's inequality with convex φ(x) = x^(−p).

## Problem 5.8 – Jensen Inequality in Two Variables

- (a) For convex f on convex set C, showed:  
  f(E[X], E[Y]) ≤ E[f(X,Y)]
- (b) Verified convexity condition via Hessian test:  
  f₁₁ ≥ 0, f₂₂ ≥ 0, and f₁₁f₂₂ ≥ f₁₂²

## Problem 5.9 – Hölder’s Inequality via Jensen

- Recalled that Hölder’s inequality is:  
  E[X^{1/p} Y^{1/q}] ≤ E^{1/p}[X] · E^{1/q}[Y], with 1/p + 1/q = 1  
- Derived this inequality from Jensen using (5.38) and convexity of exponential functions.

---

## Reflections

- Seeing Chebyshev, Cantelli, Jensen, and Hölder in one sequence highlights how convexity underpins most classical inequalities in probability.
- Understanding "sharpness" in inequalities is crucial – not just proving them, but knowing when they are tight.
- Jensen’s inequality is extremely powerful; once convexity is recognized, many inequalities become straightforward.

