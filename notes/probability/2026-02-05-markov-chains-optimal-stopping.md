# Study Notes: Optimal Stopping in Finite Markov Chains

Date: 2026-02-05  
Textbook: Probability (Section 8: Markov Chains)  
Section: Optimal Stopping (Lemma 4–6, Theorem 8.10–8.11)

---

> **Note**:  
> Today's focus is on reading and proof structure: how optimal stopping is reduced to “minimal excessive majorant”, and why the hitting time of M = {v = f} is optimal.

## Content logic

We started from a finite-state Markov chain (X_n) on a finite set S, and a payoff function f on S. A stopping time τ is a rule for choosing when to stop based only on what has been observed so far. If we stop at time τ, the payoff is f(X_τ). The goal is to choose τ to maximize the expected payoff.

The key chain of ideas is:

- Define the value function v(i) = sup_{τ} E_i[f(X_τ)].
- Show v is excessive (Lemma 4).
- Prove an “optional stopping inequality” for any excessive function (Lemma 5).
- Use that to prove: any excessive function φ that dominates f also dominates v (Lemma 6).
- Conclude: v is the minimal excessive function dominating f (Theorem 8.10).
- Define the contact/support set M = {i : v(i) = f(i)}.
- Define τ0 as the hitting time of M: τ0 = min{n : X_n ∈ M}.
- Prove τ0 is optimal: E_i[f(X_τ0)] = v(i) for all i (Theorem 8.11).

## Key ideas

- Excessive (superharmonic) functions:
  - φ is excessive means φ(i) ≥ Σ_j p_ij φ(j) for every i.
  - Intuition: the “expected next value” is never higher than the current value.

- Value function as a minimal upper envelope:
  - Theorem 8.10 reframes the stopping problem: instead of searching over all stopping rules directly, search over functions.
  - v is the smallest function that (1) stays above f everywhere and (2) is excessive.

- Why M matters:
  - On M, stopping immediately is already optimal because v(i) = f(i).
  - The optimal strategy should be “continue until you enter M, then stop”.

## Notation

- S: finite state space.
- p_ij: one-step transition probabilities, p_ij = P(X_1 = j | X_0 = i).
- τ: stopping time (also called Markov time in the text).
- E_i[·], P_i(·): expectation/probability given X_0 = i.
- f: payoff function on states.
- v: value function, v(i) = sup_{τ} E_i[f(X_τ)].
- M: contact/support set, M = {i : v(i) = f(i)}.
- τ0: hitting time of M, τ0 = min{n : X_n ∈ M}.
- τ1: first hitting time of M after at least one step, τ1 = min{n : n ≥ 1, X_n ∈ M}.
- φ (varphi): performance of a specific strategy; in Theorem 8.11, φ(i) = E_i[f(X_τ0)].
- ψ: a temporary auxiliary function used in a contradiction step (constructed by shifting φ by a constant).

## Proof sketch: Lemma 5 (why “excessive” implies waiting does not help)

If φ is excessive, then for any stopping time τ:

- Truncate the stopping time: τ_N = min(τ, N).
- Expand E_i[φ(X_τN)] by splitting into cases: τ < N and τ ≥ N.
- Use the Markov property and the excessive inequality φ(j) ≥ Σ_k p_jk φ(k) to show
  E_i[φ(X_τN)] ≤ E_i[φ(X_τ(N-1))].
- Therefore E_i[φ(X_τN)] is non-increasing in N and bounded above by φ(i).
- Let N → ∞ to conclude φ(i) ≥ E_i[φ(X_τ)].

A useful interpretation:
- Along the chain, φ(X_n) behaves like a “supermartingale-type quantity” in expectation.
- So postponing the stopping time cannot increase its expected value.

## Proof sketch: Theorem 8.10 (v is the minimal excessive function dominating f)

Two facts:

1) v dominates f:
- τ = 0 is a valid stopping time, so v(i) = sup_{τ} E_i[f(X_τ)] ≥ E_i[f(X_0)] = f(i).

2) v is minimal among excessive dominators:
- Lemma 4: v is excessive.
- Lemma 6: if φ is excessive and φ ≥ f, then for all τ,
  φ(i) ≥ E_i[φ(X_τ)] ≥ E_i[f(X_τ)],
  hence φ(i) ≥ sup_{τ} E_i[f(X_τ)] = v(i).

So any excessive upper bound of f lies above v, meaning v is the smallest such function.

## Proof sketch: Theorem 8.11 (the hitting time τ0 is optimal)

Goal: show E_i[f(X_τ0)] = v(i).

Step 1: define φ(i) = E_i[f(X_τ0)].
Since X_τ0 ∈ M and v = f on M, we also have φ(i) = E_i[v(X_τ0)].

Step 2: show φ is excessive.
Introduce τ1 = min{n ≥ 1 : X_n ∈ M}. A computation using the Markov property gives:
E_i[v(X_τ1)] = Σ_j p_ij E_j[v(X_τ0)] = Σ_j p_ij φ(j).

Since τ0 ≤ τ1 and v is excessive, Lemma 5 implies:
E_i[v(X_τ0)] ≥ E_i[v(X_τ1)].

So:
φ(i) = E_i[v(X_τ0)] ≥ E_i[v(X_τ1)] = Σ_j p_ij φ(j),
which is exactly “φ is excessive”.

Step 3: show φ ≤ v.
This is immediate because v is the supremum over all stopping times, and τ0 is just one candidate:
φ(i) = E_i[f(X_τ0)] ≤ sup_{τ} E_i[f(X_τ)] = v(i).

Step 4: show φ ≥ f (the nontrivial part).
- If i ∈ M, then τ0 = 0, so φ(i) = E_i[f(X_0)] = f(i).
- If we assume there exists i in S \ M with φ(i) < f(i), pick i0 maximizing the gap f(i) - φ(i).
- Define ψ(i) = φ(i) + (f(i0) - φ(i0)).
  Then ψ is excessive (adding a constant preserves excessiveness), and ψ ≥ f by the choice of i0.
- By Theorem 8.10, ψ must dominate v, so at i0:
  ψ(i0) = f(i0) ≥ v(i0).
  But always v(i0) ≥ f(i0), hence v(i0) = f(i0), meaning i0 ∈ M, contradicting i0 ∈ S \ M.

So φ ≥ f holds everywhere.

Step 5: conclude φ = v.
Now φ is excessive and φ ≥ f, so by Theorem 8.10 (minimality of v), φ ≥ v.
Combined with φ ≤ v, we get φ = v.
Therefore E_i[f(X_τ0)] = v(i), i.e., τ0 is optimal.

## Why so many functions (practical mental model)

- f: the raw payoff rule (what you get if you stop now in a given state).
- v: the best possible expected payoff if you are allowed to choose the stopping rule.
- φ: the expected payoff of one concrete proposed strategy (here: “hit M then stop”).
- ψ: a one-time tool for contradiction, created by shifting φ upward to build an excessive upper bound of f.

This is a common pattern:
- Define the abstract optimum (v).
- Propose a candidate policy and compute its performance (φ).
- Prove φ matches v using structural properties (excessive + minimality).
- Use ψ only to rule out a subtle failure mode (φ falling below f somewhere).

## Questions & confusions (to revisit)

- How to compute v efficiently in concrete examples?
  - The text’s “minimal excessive majorant” viewpoint suggests an algorithmic angle, but the explicit computational method (dynamic programming / solving inequalities) needs to be made concrete.

- Continuation vs stopping region:
  - M is where v = f (“stop region”).
  - On S \ M (“continue region”), I expect v behaves like a harmonic function (often v(i) = Σ_j p_ij v(j)), but I want to confirm exactly what assumptions are needed for that equality.

## Reflections

The main conceptual win today:
- Optimal stopping is not just “search over times”. It becomes a clean structural statement:
  v is the smallest excessive function above f, and the optimal policy is to stop when the chain first hits the contact set M = {v = f}.

This matches the common real-world shape of optimal stopping rules:
- Identify a “stop region” in the state space, then stop the first time you enter it.
