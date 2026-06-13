# Study Notes: Markov Chain Exercises 8.7–8.15

Date: 2026-06-13  
Textbook: Probability and Measure, Third Edition, Patrick Billingsley  
Section: Chapter 1, Section 8 — Markov Chains, Exercises 8.7–8.15

---

> **Note**:  
> Today's focus is on proof structure in Markov chains, especially first-step decomposition, transience and recurrence, bounded harmonic functions, exit probabilities, coupling, and stationary distributions.


## Content Logic

The exercises form a connected sequence.

- Exercises 8.7–8.10 develop different characterizations of transience.
- Exercise 8.11 identifies an exit probability as the minimal nonnegative solution of a system.
- Exercises 8.12–8.14 use examples to clarify the limits of irreducibility and aperiodicity results.
- Exercise 8.15 combines drift, recurrence, and stationary equations in a complete classification problem.

The recurring strategy is to translate a probabilistic event into a system of equations, then study the smallest, largest, bounded, or summable solutions of that system.



## Exercise 8.7: First-Step and Finite-Time Decomposition

The hitting probability f_ik satisfies the first-step equation

f_ik = p_ik + Σ_{j ≠ k} p_ij f_jk.

The two terms correspond to:

- reaching k in the first step;
- moving first to some j ≠ k and then reaching k from j.

More generally,

f_ik = f_ik^(1) + ··· + f_ik^(n)
       + Σ_{j ≠ k} P_i[X_1 ≠ k, ..., X_{n−1} ≠ k, X_n = j] f_jk.

This separates paths that hit k during the first n steps from paths that avoid k through time n and may hit it later.

Taking k = i gives a structural criterion:

i is transient if and only if there is some j ≠ i such that f_ij > 0 and f_ji < 1.

For an irreducible chain, f_ij > 0 automatically holds for all i and j. Therefore, transience can be detected by finding a reachable state from which return is not certain.



## Exercise 8.8: An Absorbing State and Population Extinction

Assume S = {0, 1, 2, ...}, p_00 = 1, and f_i0 > 0 for every i.

Since 0 is absorbing,

f_0j = 0 for every j ≥ 1.

For each positive state j,

f_j0 > 0 and f_0j < 1.

By the criterion from Exercise 8.7, every positive state is transient. Hence

P_i(⋃_{j=1}^∞ [X_n = j infinitely often]) = 0.

If X_n represents population size, then:

- p_00 = 1 means that extinction is permanent;
- f_i0 > 0 means that extinction is possible from every finite population size;
- with probability one, the population either becomes extinct or eventually leaves every finite positive level, which means X_n → ∞.



## Exercise 8.9: Bounded Signed Solutions

Equation (8.27) is

x_i = Σ_{j ≠ i_0} p_ij x_j,    i ≠ i_0,

with 0 ≤ x_i ≤ 1 in its original form.

The exercise shows that, for an irreducible chain, a nontrivial solution of (8.27) exists if and only if there is a nontrivial bounded solution of the same equation, even when negative values are allowed.

One direction is immediate: a solution of (8.27) is already bounded.

For the converse, suppose a bounded nonzero signed solution exists. If the chain were persistent, let K bound |x_i|. Iterating the equation through paths that avoid i_0 gives

|x_i| ≤ K P_i[X_k ≠ i_0 for 1 ≤ k ≤ n].

In a persistent irreducible chain, the probability of avoiding i_0 through time n tends to 0. Therefore x_i = 0 for every i, contradicting nontriviality.

Thus the chain must be transient. Theorem 8.5 then guarantees a nontrivial solution of (8.27).



## Exercise 8.10: Bounded Nonconstant Harmonic Functions

Consider

y_i = Σ_j p_ij y_j,    i ≠ i_0,

where the sum is over all states j.

Define

x_i = y_i − y_i0,    i ≠ i_0.

Since Σ_j p_ij = 1,

x_i = Σ_{j ≠ i_0} p_ij x_j.

Thus a bounded nonconstant solution {y_i} produces a bounded nontrivial solution {x_i} of the system in Exercise 8.9.

Conversely, from a bounded solution {x_i}, define

y_i0 = 0,
y_i = x_i for i ≠ i_0.

Then {y_i} satisfies the full harmonic equation outside i_0.

Therefore, for an irreducible chain,

the chain is transient if and only if there exists a bounded nonconstant function that is harmonic outside an arbitrary state i_0.



## Exercise 8.11: Exit Probabilities as the Minimal Solution

Let

T = inf{n ≥ 1 : X_n ∉ U}

and define

q_i = P_i(T < ∞),    i ∈ U.

First-step decomposition gives

q_i = Σ_{j ∈ U} p_ij q_j + Σ_{j ∉ U} p_ij.

Thus {q_i} is a solution of the exit-probability system.

To prove minimality, let {z_i} be any nonnegative solution. Iterating the equation shows

z_i ≥ P_i(T ≤ n)

for every n.

Since

P_i(T ≤ n) ↑ P_i(T < ∞) = q_i,

it follows that

z_i ≥ q_i.

Hence the actual exit probabilities form the minimal nonnegative solution.

The condition z_i ≤ 1 is unnecessary because the constant sequence z_i = 1 is also a solution. The minimal solution is therefore automatically at most 1.



## Exercise 8.12: Pointwise Thresholds Need Not Be Uniform

Lemma 2 states that, in an irreducible aperiodic chain, for every fixed pair i, j there is a finite n_0(i,j) such that

p_ij^(n) > 0 whenever n > n_0(i,j).

This does not imply that the values n_0(i,j) have a common finite upper bound.

Consider a lazy nearest-neighbor walk on S = ℤ:

p(i,i) = 1/2,
p(i,i+1) = p(i,i−1) = 1/4.

The chain is irreducible and aperiodic. From i to j, at least |i−j| steps are required, while additional steps can be added by remaining in place. Thus one may take

n_0(i,j) = |i−j| − 1.

For i = 0 and j = m,

n_0(0,m) = m − 1 → ∞.

Therefore

sup_{i,j} n_0(i,j) = ∞.

The main lesson is the distinction between

for every i,j there exists n_0(i,j),

and

there exists one finite N that works for every i,j.



## Exercise 8.13: Signs of Absolutely Summable Invariant Solutions

Suppose

π_j = Σ_i π_i p_ij

and

Σ_i |π_i| < ∞.

Then

Σ_j |π_j|
= Σ_j |Σ_i π_i p_ij|
≤ Σ_j Σ_i |π_i|p_ij
= Σ_i |π_i|Σ_j p_ij
= Σ_i |π_i|.

The two end terms are equal, so equality must hold throughout. Therefore, for each fixed j, the nonzero terms π_i p_ij cannot contain both positive and negative values. Otherwise strict cancellation would occur.

If π_i > 0 and p_ij > 0, then π_j > 0. Positivity therefore propagates along every positive-probability path. By irreducibility, one positive component forces every component to be positive.

The same argument applies to negative components. Hence an absolutely summable invariant solution must be:

- strictly positive everywhere;
- strictly negative everywhere;
- or identically zero.

A nontrivial solution can therefore be multiplied by −1 if necessary and normalized by its total mass. This produces stationary probabilities.



## Exercise 8.14: Periodicity Can Destroy Irreducibility of the Coupled Chain

Consider the two-state chain

0 → 1,
1 → 0,

with both transitions having probability 1.

The original chain is irreducible but has period 2.

For two independent copies, the coupled chain has state space

{(0,0), (0,1), (1,0), (1,1)}.

Its transitions are

(0,0) ↔ (1,1),

and

(0,1) ↔ (1,0).

Thus the coupled state space splits into two closed communicating classes:

{(0,0), (1,1)}

and

{(0,1), (1,0)}.

The coupled chain is therefore not irreducible.

The example shows why aperiodicity is needed in Theorem 8.6: both coordinates must be able to complete the required transitions at the same time.



## Exercise 8.15: Drift, Recurrence, and Stationary Probabilities

The state space is ℤ. At 0,

p_0,−1 = p_0,0 = p_0,1 = 1/3.

Away from 0, the probability p moves the chain toward 0, while q = 1−p moves it away from 0.

Because p,q > 0, every integer can be reached from every other integer, so the chain is irreducible.

Since p_00 = 1/3 > 0, state 0 has period 1. By irreducibility, the chain is aperiodic.

To determine recurrence, consider the probability h of reaching 0 from state 1:

h = 1 when p ≥ q,
h = p/q when p < q.

The first-return probability from 0 is

f_00 = 1/3 + (2/3)h.

Therefore,

f_00 = 1 if and only if p ≥ q,

so the chain is persistent if and only if

p ≥ 1/2.

For stationary probabilities, local balance gives

π_1 = π_0/(3p),

and, for k ≥ 1,

π_{k+1} = (q/p)π_k.

By symmetry, π_−k = π_k. The stationary mass is summable if and only if

q/p < 1,

which is equivalent to

p > 1/2.

Hence:

- p < 1/2: transient, with no stationary probabilities;
- p = 1/2: null persistent, with no stationary probabilities;
- p > 1/2: positive persistent, with stationary probabilities.

When p > 1/2,

π_0 = 3(p−q) / [3(p−q)+2],

and for k ≥ 1,

π_k = π_−k = [π_0 / (3p)] × (q / p)^(k−1)


## Key Ideas

- First-step decomposition converts a future event into a recursive equation.
- Irreducibility propagates local properties, such as positivity, negativity, recurrence, and period, throughout the state space.
- A probabilistically meaningful solution is often characterized as the minimal or maximal nonnegative solution of a system.
- Bounded harmonic functions provide an analytic test for transience.
- Pointwise finiteness does not imply a uniform finite bound on an infinite state space.
- Recurrence and the existence of stationary probabilities are different:
  recurrence requires eventual return with probability one, while stationary probabilities require positive recurrence and finite expected return time.
- Aperiodicity is essential when two chains must make compatible transitions at the same time.


## Questions and Confusions

One important caution concerns Exercise 8.9.

A signed solution should not simply be shifted by a constant to make it nonnegative. The equation

x_i = Σ_{j ≠ i_0} p_ij x_j

does not generally remain unchanged under translation because

Σ_{j ≠ i_0} p_ij

may be less than 1.

The correct proof is indirect:

- show that a persistent irreducible chain has no nonzero bounded signed solution;
- conclude that the existence of such a solution forces transience;
- apply Theorem 8.5 to obtain a nontrivial nonnegative solution.

Another distinction to retain is:

persistent does not automatically mean that stationary probabilities exist.

The case p = 1/2 in Exercise 8.15 is persistent but null persistent, so no stationary probability distribution exists.



## Reflections

These exercises connect probabilistic behavior with linear equations in a very concrete way.

The equations are not merely algebraic identities. Their solutions represent events such as hitting a state, avoiding a state forever, leaving a set, or preserving a distribution under one-step evolution.

The most useful habit is to identify the probabilistic meaning of a proposed solution before manipulating the equation. Once that meaning is clear, first-step decomposition, iteration, and monotone convergence usually determine whether the relevant solution is minimal, maximal, bounded, or summable.

The exercises also reinforce the need to read quantifiers carefully. A conclusion that holds separately for each pair of states may fail uniformly over an infinite state space.

