# Study Notes: Asymptotic Prime Estimates via Probabilistic Tools

Date: 2025-07-24  
Textbook: Billingsley – Probability and Measure (3rd ed.)  
Section: Exercises 5.18 to 5.20 (Pages 83–84)

---

> **Note**:  
> Today's focus is on asymptotic independence, prime number estimates, and weak versions of the prime number theorem using probabilistic expectations and truncation arguments.

## Content logic

### 5.18 – Independence in the non-identically distributed case

- This exercise generalizes Theorem 5.3 to a case where the distributions μ_n are not identical.
- The main goal is to prove:  
  μ̂_n(ω) → μ̄_n := (1/n) Σ μ_k
- The proof relies on a version of the weak law of large numbers adapted to sequences of independent (but not identically distributed) random variables.
- Key idea: Even if μ_n differs, as long as the underlying variables are independent and the average of measures converges, the empirical measure still converges.

### 5.19 – Asymptotic independence of α_p(m)

- Introduces α_p(m), the exponent of prime p in the prime factorization of m.
- Under uniform distribution on {1, ..., n}, α_p becomes a random variable.
- Shows that for fixed primes p_1, ..., p_u and fixed exponents k_1, ..., k_u:
  
  P_n[α_{p_i} ≥ k_i for all i] = ⌊n / (p_1^{k_1} ... p_u^{k_u})⌋ / n → 1 / (p_1^{k_1} ... p_u^{k_u})
  
- Likewise, shows:
  
  P_n[α_{p_i} = k_i for all i] → ∏_{i=1}^u (1/p_i^{k_i} - 1/p_i^{k_i+1})
  
  and
  
  P_n[δ_{p_i} = 1 for all i] → 1 / (p_1 ... p_u)

- These results show that the α_p and δ_p behave almost independently in the limit, laying the groundwork for approximations involving multiplicative functions.

### 5.20 – Estimating π(x), the number of primes ≤ x

#### (a) Expected log under uniform measure

- Start with E_n[log] = (1/n) log(n!) = log n + O(1) using Stirling’s formula.

#### (b) Expected value of log⁎m

- log⁎m = Σ δ_p(m) log p
- Derived:  
  E_n[log⁎] = Σ_p (⌊n/p⌋ / n) log p = log n + O(1)

#### (c) Difference E_{2n}[log⁎] − E_n[log⁎]

- Bounded difference due to limited number of primes in (n, 2n], so still O(1).
- This implies Σ_{p ≤ x} log p = O(x)

#### (d) Truncation and asymptotics

- Use truncated sum over (θx, x] and earlier result on Σ log p/p = log x + O(1)
- Conclude:  
  Σ_{p ≤ x} log p ≍ x

#### (e) Prime counting and divergence of Σ 1/p

- Since Σ log p ≍ x, and each log p ≈ log x, number of primes must be:  
  π(x) ≍ x / log x

- Also deduce:
  - The r-th prime p_r ≍ r log r
  - Harmonic series of primes diverges:  
    Σ 1/p = ∞, by comparison to Σ 1/(r log r)

---

## Key Ideas

- Use expectations over log or log⁎ to estimate average prime behavior.
- Truncation helps isolate dominant contribution from high primes.
- Log-sum asymptotics invert to give prime-counting asymptotics.
- Formal logic from probability expectations can approximate number-theoretic behavior.

## Proof Sketch

- Expectation of log⁎ gives weighted average of primes over divisibility.
- Use difference techniques and summation estimates to get asymptotic log p sums.
- π(x) follows by comparing average log p to total log sum.
- Divergence of Σ 1/p proven via integral comparison with 1/(r log r).

## Questions & Confusions

- Why does log⁎ have the same expectation as log? (Because the missing α_p > 1 parts cancel out in O(1))
- Why is truncation valid? Because log p grows slowly and high primes dominate the sum.

## Reflections

- This is a beautiful bridge from elementary probability to analytic number theory.
- Learned to use expectation and asymptotics together.
- Start of understanding how prime distributions can be approximated without complex analysis.

