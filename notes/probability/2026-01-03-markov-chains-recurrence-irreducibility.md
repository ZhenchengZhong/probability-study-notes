# Study Notes: Markov Chains (recurrence, irreducibility, and staying in a set)

Date: 2026-01-03  
Textbook: Probability and Measure (Patrick Billingsley)  
Section: Section 8 (Markov Chains), pp. 111–123  

---

> Note: Today's focus is on careful English reading + translation, and on the proof logic behind recurrence/transience (first-visit decomposition, Borel–Cantelli) and irreducibility.

## Content Logic

- Start with the definition of a time-homogeneous Markov chain on a finite/countable state space S.
- Work through standard examples (diffusion model, absorbing random walk, unrestricted random walk, random walk on Z^k, secretary problem).
- Introduce n-step transition probabilities p_ij^(n), matrix powers P^n, and Chapman–Kolmogorov.
- Existence theorem: given (α_i) and a stochastic matrix P, a Markov chain exists on some probability space.
- Define first-visit probabilities f_ij^(n) and eventual-visit probabilities f_ij, then define transient vs persistent (recurrent).
- Theorem 8.2: recurrence/transience criterion via Σ_n p_ii^(n).
- Polya’s theorem (Example 8.6): symmetric random walk is recurrent in k = 1,2 and transient in k ≥ 3.
- Irreducibility: the chain must be either all transient or all persistent (Theorem 8.3).
- Another criterion for persistence via substochastic matrices and “staying forever in a subset” (Theorem 8.4, Example 8.10).

## Key Definitions and Notation

- State space: S is finite or countable.
- Transition probabilities: p_ij ≥ 0 and Σ_{j∈S} p_ij = 1 for each i.
- Markov property (time-homogeneous):
  P[X_{n+1}=j | X_0=i_0, …, X_n=i] = P[X_{n+1}=j | X_n=i] = p_ij.
- Initial distribution: α_i = P[X_0=i], with α_i ≥ 0 and Σ_i α_i = 1.
- n-step transitions:
  p_ij^(n) = P[X_{m+n}=j | X_m=i] (does not depend on m).
  Also p_ij^(n) is the (i,j) entry of P^n.
- First-visit probability:
  f_ij^(n) = P_i[X_1≠j, …, X_{n-1}≠j, X_n=j].
- Eventual visit probability:
  f_ij = P_i(⋃_{n≥1} [X_n=j]) = Σ_{n≥1} f_ij^(n).
- Persistent (recurrent) state i: f_ii = 1.
  Transient state i: f_ii < 1.
- “i.o.” means infinitely often.

## Key Ideas

- First-visit decomposition (the main algebra tool):
  p_ij^(n) = Σ_{s=0}^{n-1} f_ij^(n-s) p_jj^(s).
  Intuition: to be at j at time n, the chain must first hit j at some earlier time (n−s), then return to j in the remaining s steps.

- Recurrence vs “sum of return probabilities”:
  For a fixed state i, Σ_n p_ii^(n) behaves like a “total mass of return opportunities.”
  If this total mass is finite, returns cannot happen infinitely often; if it is infinite, returns happen infinitely often (in the sense of Theorem 8.2).

## Proof Sketches

### Existence (Theorem 8.1)

- Reuse the construction idea from earlier existence results: build a nested sequence of partitions of [0,1) so that cylinder events
  {X_0=i_0, …, X_n=i_n}
  have probability α_{i_0} p_{i_0 i_1} … p_{i_{n-1} i_n}.
- This yields a Markov chain with the prescribed initial distribution and transition matrix.

### Transience and persistence via first visits (Section “Transience and Persistence”)

- Define f_ij^(n) and f_ij, then show a 0–1 type conclusion for infinite revisits:
  P_i[X_n=i i.o.] is either 0 or 1, depending on whether f_ii < 1 or f_ii = 1.

### Theorem 8.2 (criterion using Σ_n p_ii^(n))

- One direction: if Σ_n p_ii^(n) < ∞, apply the first Borel–Cantelli lemma to events {X_n=i}, giving P_i[X_n=i i.o.] = 0, hence f_ii < 1 (transient).
- The other direction uses the first-visit decomposition with i=j:
  sum_{t=1}^n p_ii^(t) can be bounded by f_ii times a similar partial sum, leading to
  (1−f_ii) Σ_{t=1}^n p_ii^(t) ≤ f_ii.
  If f_ii < 1, the partial sums are uniformly bounded, so Σ_n p_ii^(n) < ∞.

### Polya’s theorem (Example 8.6)

- k = 1:
  Return in 2n steps means n steps right and n steps left:
  a_2n^(1) = C(2n,n) / 2^(2n) ~ (π n)^(-1/2),
  so Σ_n a_n^(1) diverges, hence recurrence.
- k = 2:
  The return probability satisfies a_2n^(2) = (a_2n^(1))^2 ~ (π n)^(-1),
  again Σ diverges, hence recurrence.
- k ≥ 3:
  The book shows a_2n^(3) = O(n^(-3/2)), hence Σ converges, hence transience.
  The same decay pattern extends to higher k: a_n^(k) = O(n^(-k/2)).

### Irreducibility dichotomy (Theorem 8.3)

- Irreducible means for any i,j there exists n with p_ij^(n) > 0.
- Use paths i→j and j→i to compare return sums:
  p_ii^(r+s+n) ≥ p_ij^(r) p_jj^(n) p_ji^(s).
  This transfers convergence/divergence of Σ_n p_ii^(n) between states.
- Conclusion: either every state is transient (and visits to any fixed j happen only finitely often), or every state is persistent (and every state is visited infinitely often).

## Notes from Examples

- Example 8.9 (unrestricted random walk on Z):
  Even in the persistent case (p=q=1/2), we can have p_ij^(n) → 0.
  In fact p_ij^(n) = C(n, (n+j−i)/2) 1/2^n (when parity matches), and the maximum is of order n^(-1/2), so p_ij^(n) → 0.

- Another criterion for persistence (substochastic matrix method):
  Let Q = [q_ij] be substochastic: q_ij ≥ 0 and Σ_j q_ij ≤ 1.
  Define row sums σ_i^(n) = Σ_j q_ij^(n); then σ_i^(n) is decreasing in n and converges to σ_i.
  The limit vector (σ_i) solves x_i = Σ_{j∈U} q_ij x_j with 0 ≤ x_i ≤ 1 and is the maximal solution.

- Theorem 8.4 (staying forever in U):
  For U ⊂ S, define x_i = P_i[X_t ∈ U for all t ≥ 1].
  Then (x_i) is the maximal solution of x_i = Σ_{j∈U} p_ij x_j with 0 ≤ x_i ≤ 1.

- Example 8.10 (U = {0,1,2,…} for random walk on the line):
  The system becomes:
  x_i = p x_{i+1} + q x_{i−1} for i ≥ 1, and x_0 = p x_1.
  The maximal bounded solution is:
  - x_n = 0 when q ≥ p (probability of staying forever in nonnegative integers is 0),
  - x_n = 1 − (q/p)^(n+1) when q < p.

## Questions & Confusions

- The Weierstrass M-test step: I want to re-derive precisely why it justifies passing limits through Σ_j in the definition of σ_i.
- For the 3D bound a_2n^(3) = O(n^(-3/2)), I want to rewrite the argument in my own words, especially the step that discards l=0 and l=n and bounds the remaining sum.
- Combinatorial identity used in 2D: Σ_{u=0}^n C(n,u) C(n,n−u) = C(2n,n). I know it’s standard, but I want a clean proof I can reproduce quickly.

## Reflections / Next Steps

- Re-check the role of “i.o.” events and how they connect to first-visit probabilities f_ij and to Borel–Cantelli.
- Do a small simulation (Python) of symmetric random walks in k=1,2,3 and empirically compare return behavior.
- Read the referenced problems (8.7, 8.35) to fill in the missing details about f_ij=1 in a transient setting and dependence issues.
