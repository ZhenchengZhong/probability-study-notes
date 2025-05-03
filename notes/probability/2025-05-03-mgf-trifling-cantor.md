# Study Notes: Moment Generating Functions and Trifling Sets

Date: 2025-05-03  
Textbook: Probability and Measure (3rd Edition) by Patrick Billingsley  
Section: Exercises 1.3–1.6  

---

> **Note**:  
> Today's focus is on moment generating functions and the notion of trifling sets, with applications to integrals involving sₙ(ω) and Cantor set properties.

## Key Ideas

- A set is called **trifling** if for every ε > 0, it can be covered by a finite collection of open intervals whose total length is less than ε.
- Every trifling set is negligible, but not every negligible set is trifling.
- The closure of a trifling set is still trifling.
- Cantor set C can be seen as the closure of A₃(1), where A₃(1) contains all numbers in (0,1] whose base-3 expansion contains no digit 1.
- Though C is uncountable, it is still trifling.
- The function M(t) = ∫₀¹ e^{t sₙ(ω)} dω acts as a moment generating function for sₙ(ω), and has the closed-form M(t) = cosh^n(t).

## Proof Sketch

### (1.6) Derivatives of M(t)

Let M(t) = cosh^n(t). Then:

- First derivative:  
  M'(t) = n cosh^{n−1}(t) sinh(t)

- Second derivative:  
  M''(t) = n cosh^{n−1}(t) cosh(t) + n(n−1) cosh^{n−2}(t) sinh²(t)

- At t = 0:  
  cosh(0) = 1, sinh(0) = 0  
  → M'(0) = 0  
  → M''(0) = n  
  → M⁽⁴⁾(0) = n + 3n(n−1)

From the identity:

- M⁽ᵏ⁾(0) = ∫₀¹ sₙ^k(ω) dω

We recover:

- ∫₀¹ sₙ(ω) dω = 0  
- ∫₀¹ sₙ²(ω) dω = n  
- ∫₀¹ sₙ⁴(ω) dω = n + 3n(n−1) ≤ 3n²

These match formulas (1.16), (1.18), and (1.28) respectively.

### (1.5) Cantor Set and Trifling

- The Cantor set C = closure of A₃(1), formed by removing middle thirds iteratively.
- Though C is uncountable, it can be covered by finite intervals of arbitrarily small total length.
- Thus C is trifling.
- C is also perfect: it is closed and every point is a limit point.

## Reflections

- The concept of trifling is stricter than negligible, yet it behaves well under closure and finite unions.
- Moment generating functions provide an elegant way to compute integrals of sₙ^k(ω) via derivatives.
- The interplay between series expansion (cosh^n(t)) and probability integrals highlights how analysis and probability deeply connect.
