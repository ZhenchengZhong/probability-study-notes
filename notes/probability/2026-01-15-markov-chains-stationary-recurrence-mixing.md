# Study Notes: Markov Chains — Stationary Distributions, Recurrence Classification, and Exponential Convergence

Date: 2026-01-15  
Textbook: Probability (Markov Chains)  
Section: Section 8 — Stationary distributions, coupling, recurrence classification, exponential convergence

---

> Note:
> Today's focus is on proof structure (coupling and contraction arguments) and turning definitions into usable criteria in examples.

## Content logic

This set of pages builds a single storyline:

- Start from the definition of a stationary distribution (pi P = pi).
- Explain why periodicity matters for convergence.
- Prove convergence to the stationary distribution in the irreducible, aperiodic case via a coupling argument (Theorem 8.6).
- Classify long-run behaviors into three regimes: transient, null persistent, positive persistent (Theorem 8.8).
- In the finite-state case, strengthen convergence to an exponential rate (Theorem 8.9).
- Work examples to see how the criteria show up in concrete transition structures.

## Key ideas

- Stationary distribution:
  - A vector pi = (pi_i) with pi_i >= 0, sum_i pi_i = 1, and pi P = pi.
  - If X_0 ~ pi, then X_n ~ pi for all n.

- Period and aperiodicity:
  - Period of state j is gcd{ n >= 1 : p_jj^(n) > 0 }.
  - In an irreducible chain, all states share the same period.
  - Period 1 means aperiodic, which is the regime where mixing/convergence is expected.

- Why coupling is powerful:
  - To compare p_ik^(n) and p_jk^(n), run two copies of the chain (X_n, Y_n).
  - Once they meet (or are forced to meet at a chosen reference state), their future distributions match.
  - The difference between their n-step laws is controlled by the probability that they have not met yet.

## Proof sketch: Theorem 8.6 (coupling and convergence)

Goal:
- For an irreducible, aperiodic chain with a stationary distribution pi, show:
  1) the chain is persistent,
  2) lim_{n->infty} p_ij^(n) = pi_j for all i, j,
  3) pi is unique and pi_j > 0.

Main steps:

1) Stationarity rules out transience
- If the chain were transient, then p_ij^(n) -> 0 for all i, j.
- But stationarity gives pi_j = sum_i pi_i p_ij^(n) for every n.
- Sending n -> infty forces pi_j = 0 for all j, contradicting sum_j pi_j = 1.
- Therefore the chain must be persistent.

2) Build the coupled chain on S x S
- Define a Markov chain on pairs (i, j) with transition:
  p((i, j), (k, l)) = p_ik p_jl.
- Interpret as two independent copies X and Y evolving under the same original transition matrix.
- Use irreducible + aperiodic to argue the coupled chain is irreducible.

3) Meeting time and the key inequality
- Fix a reference state i0.
- Define tau = min{ n : X_n = Y_n = i0 }.
- Persistence of the coupled chain implies tau < infty with probability 1 (under P_{ij}).

- Using the Markov property at time tau:
  For k fixed, |P_{ij}(X_n = k) - P_{ij}(Y_n = k)| <= P_{ij}(tau > n).
  Hence |p_ik^(n) - p_jk^(n)| <= P_{ij}(tau > n) -> 0.

4) Deduce convergence to pi
- Use stationarity: pi_k = sum_i pi_i p_ik^(n).
- Then pi_k - p_jk^(n) = sum_i pi_i (p_ik^(n) - p_jk^(n)).
- Since each difference goes to 0 and the weights sum to 1, the right side goes to 0.
- Therefore p_jk^(n) -> pi_k.

5) Uniqueness and positivity
- Uniqueness: the limit of p_jk^(n) is forced, so there cannot be two different stationary distributions.
- Positivity: irreducibility lets positivity propagate from one state to all others; since sum_j pi_j = 1, at least one pi_j > 0, hence all pi_i > 0.

## Recurrence classification: Theorem 8.8 (three regimes)

For an irreducible, aperiodic chain exactly one of the following holds:

(i) Transient
- lim_{n->infty} p_ij^(n) = 0
- and sum_{n>=1} p_ij^(n) < infty.

(ii) Null persistent (persistent but no stationary distribution)
- p_ij^(n) -> 0
- but sum_{n>=1} p_ij^(n) = infty (goes to 0 too slowly),
- mean return time mu_j = infty.

(iii) Positive persistent (stationary distribution exists)
- lim_{n->infty} p_ij^(n) = pi_j > 0,
- mean return time mu_j = 1/pi_j < infty.

Interpretation:
- The difference between (i) and (ii) is not the limit (both go to 0), but the total mass across time, sum_n p_ij^(n).
- Positive persistent is the only regime with a genuine long-run equilibrium distribution.

## Finite-state strengthening: Theorem 8.9 (exponential convergence)

Statement:
- If the state space is finite and the chain is irreducible and aperiodic, then a stationary distribution pi exists and
  |p_ij^(n) - pi_j| <= A rho^n
  for some A >= 0 and 0 <= rho < 1.

Proof idea (contraction via min/max envelopes):
- Fix j and define:
  m_j^(n) = min_i p_ij^(n),
  M_j^(n) = max_i p_ij^(n).
- Show monotonicity:
  m_j^(n) is nondecreasing in n, M_j^(n) is nonincreasing in n.
- Under an additional temporary assumption that all one-step probabilities are positive:
  let s be the number of states, delta = min_{i,j} p_ij > 0.
  Then the spread contracts:
  M_k^(n+1) - m_k^(n+1) <= (1 - s delta) (M_k^(n) - m_k^(n)).
  Hence M_k^(n) - m_k^(n) <= (1 - s delta)^n.
- Conclude m_j^(n) and M_j^(n) meet at a common limit pi_j, and every p_ij^(n) is squeezed to pi_j at an exponential rate.
- If not all p_ij are positive, use that in a finite irreducible aperiodic chain there exists m with p_ij^(m) > 0 for all i, j, then apply the argument to P^m and translate back to step-by-step bounds.

## Worked examples (how the criteria show up)

1) Queueing-style chain (Example 8.11 / 8.12)
- State is queue length {0, 1, 2, ...}.
- Drift intuition: expected one-step change (when nonempty) is t2 - t0.
- Stationary distribution exists only when the system has a negative drift toward smaller states (t0 > t2).
- In the boundary case t0 = t2, the chain can be persistent but still have no stationary distribution (null persistent).
- When t0 > t2, the stationary tail is geometric: pi_k behaves like (t2/t0)^k.

2) Success-run length chain (Example 8.13)
- State i is the current length of consecutive successes.
- Transition: i -> i+1 with probability p_i, i -> 0 with probability q_i (both positive).
- Persistence criterion is tied to the product p_0 p_1 ... p_n:
  - If lim_{n->infty} p_0 ... p_n > 0, there is a positive chance of never returning to 0, pushing toward transience.
  - In persistent regimes, stationary distribution exists exactly when sum_k p_0 ... p_k converges (positive persistent).
  - If p_0 ... p_k -> 0 but sum_k p_0 ... p_k diverges, the chain is null persistent.

3) Cyclic random walk / circulant transition matrix (Example 8.15)
- State space {0, 1, ..., s-1} and each row of P is a cyclic shift of the first row.
- Columns sum to 1 as well, so the uniform distribution pi_i = 1/s solves pi P = pi.
- If all step probabilities are positive, Theorem 8.9 yields exponential convergence to uniform.

## Questions and confusions

- In the coupling proof, the key conceptual leap is why tau < infty a.s. follows once the coupled chain is irreducible and persistent. I want to restate this in my own words using return-to-state arguments.
- Theorem 8.9’s constant (1 - s delta) is very explicit under positivity. When positivity only appears at step m, it would be useful to track how A and rho degrade with m.

## Reflections

- The clean hierarchy is:
  finite + irreducible + aperiodic => unique stationary distribution + exponential mixing.
  infinite-state chains split into transient / null persistent / positive persistent, and stationary distributions exist only in the positive persistent regime.
- Two proof patterns are worth memorizing:
  - coupling to kill dependence on the initial state,
  - envelope contraction (min/max) to get quantitative rates.
