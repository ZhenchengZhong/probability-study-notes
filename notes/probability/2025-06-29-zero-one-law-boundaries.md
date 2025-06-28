# Study Notes: Lower Envelopes, Zero-One Law, and Boundaries for Run Lengths

Date: 2025-06-29  
Textbook: Probability and Measure by Billingsley (3rd Edition)  
Section: Example 4.16 to Example 4.21

---

> **Note:**  
> Today's focus is on lower envelopes, the zero-one law, Diophantine approximation context, and the boundary analysis of run lengths in binary expansions, building foundations for advanced probability and measure theory for PhD preparation.

## Content logic

### Example 4.16

- If l_n(omega) >= log_2 n, then e_n(omega) <= 1/n.
- By the inequality, we have:
  P[omega : e_n(omega) <= 1/n i.o.] = 1.
- This shows that 1/n acts as a lower envelope for e_n(omega) almost surely.

### Example 4.17

- In the Diophantine approximation context, replacing x_n = 1/n^{1+epsilon} with 1/((n-1) log 2)^{1+epsilon} keeps the series sum convergent.
- We have:
  P[omega : e_n(omega) <= 1/(log 2^{n-1})^{1+epsilon} i.o.] = 0,
  and by the previous result,
  P[omega : e_n(omega) < 1/log 2^{n-1} i.o.] = 1.
- This illustrates a sharp boundary between approximations that occur infinitely often versus only finitely often in the context of binary rational approximations.

### Example 4.18 (Tail sigma-field)

- Introduces the tail sigma-field:
  T = intersection over n of sigma(A_n, A_{n+1}, ...).
- Events in the tail sigma-field are called tail events, determined solely by the values of A_n for large n.
- The limsup and liminf of a sequence of events are examples of tail events.

### Theorem 4.5 (Kolmogorov Zero-One Law)

- If A_1, A_2, ... is an independent sequence, then for any A in the tail sigma-field T,
  P(A) is either 0 or 1.
- The proof uses independence of sigma-fields and shows that A being independent of itself implies P(A) = P(A)^2, forcing P(A) to be 0 or 1.

### Example 4.19

- Examines the run length l_n(omega) and sets H_n = [omega : d_n(omega) = 0].
- Shows that:
  [omega : l_n(omega) >= r_n i.o.] = intersection over n >= n_0 of union over k >= n of [omega : l_k(omega) >= r_k],
  which is a tail event for the sequence {H_n}.
- This enables the use of Kolmogorov’s zero-one law to determine whether the event has probability 0 or 1.

### Example 4.20

- Applies the zero-one law and Borel-Cantelli lemmas to limsup events of A_n when the A_n are independent.
- Indicates that P(limsup A_n) is either 0 or 1, with Borel-Cantelli providing convergence/divergence criteria using sum P(A_n).

### Example 4.21

- Applies to sequences r_n = theta log_2 n.
- By the earlier criteria:
  - If theta > 1, sum 2^{-r_n} converges, giving an outer boundary.
  - If theta <= 1, sum 2^{-r_n} r_n^{-1} diverges, giving an inner boundary.
- For r_n = log_2 n + theta log_2 log_2 n:
  - sum 2^{-r_n} ~ sum 1/(n (log_2 n)^{theta}), which converges if theta > 1 (outer boundary).
  - sum 2^{-r_n} r_n^{-1} ~ sum 1/(n (log_2 n)^{1+theta}), which diverges if theta <= 0 (inner boundary).
- The case 0 < theta <= 1 is left unresolved here, deferred to later analysis.

## Key Ideas

- Lower envelope characterizations for e_n(omega) with probabilistic boundaries.
- Use of Kolmogorov's zero-one law on tail events to assert P(A) = 0 or 1.
- Borel-Cantelli lemmas provide explicit convergence/divergence criteria for determining the boundary behavior of events.
- Outer boundary: the event happens only finitely often (sum probabilities converge).
- Inner boundary: the event happens infinitely often (sum probabilities diverge under independence).
- For run lengths, the growth rate log_2 n is a critical threshold for behavior.

## Reflections

- These examples provide clear insight into how advanced probability results like the zero-one law and Borel-Cantelli are applied in measure theory contexts.
- The link between Diophantine approximation and binary expansions reveals the power of probabilistic methods in number theory and analysis.
- Understanding lower and upper envelopes deepens intuition about almost sure behavior versus typical event frequencies.
- This prepares foundational knowledge for advanced study in measure-theoretic probability and stochastic processes in PhD-level coursework and research.

## Questions & Confusions

- Further clarification needed for the borderline case where 0 < theta <= 1 in Example 4.21, to be studied in Example 6.5.

