# Study Notes: Markov Chain Subsolutions and One-Dimensional Random Walk Recurrence

Date: 2026-06-09  
Textbook: Billingsley, Probability and Measure  
Section: Chapter 1, Section 8, Markov Chains

---

> **Note**:  
> Today's focus is on the core logic behind Exercises 8.4, 8.5, and 8.6: first hitting decomposition, subsolutions, and the recurrence criterion for the one-dimensional random walk.

## Content Logic

The main logical chain is:

first hitting decomposition  
→ subsolution comparison  
→ bounded nonnegative solutions  
→ recurrence or transience.

## Exercise 8.4: First Hitting Decomposition

The key identity is

f_ij Σ_{k=0}^∞ p_jj^(k)
= Σ_{n=1}^∞ Σ_{m=1}^n f_ij^(m) p_jj^(n-m)
= Σ_{n=1}^∞ p_ij^(n).

Core idea:

To be at j at time n, the chain must first reach j at some time m, then continue from j for another n - m steps.

So

p_ij^(n) = Σ_{m=1}^n f_ij^(m) p_jj^(n-m).

If j is transient, then

Σ_{n=1}^∞ p_jj^(n) < ∞,

and therefore

Σ_{n=1}^∞ p_ij^(n) < ∞

for every i.

This also gives

f_ij = [Σ_{n=1}^∞ p_ij^(n)] / [1 + Σ_{n=1}^∞ p_jj^(n)].

## Exercise 8.5: Subsolutions

The system is

x_i = Σ_j q_ij x_j,    0 ≤ x_i ≤ 1.

A subsolution satisfies

x_i ≤ Σ_j q_ij x_j,    0 ≤ x_i ≤ 1.

The main result is

x_i ≤ σ_i.

Core idea:

A subsolution is iteratively bounded by σ_i^(n), and taking the limit gives

x_i ≤ lim σ_i^(n) = σ_i.

So σ dominates all solutions and all subsolutions.

Another useful fact:

If

x = Qx

and

-1 ≤ x_i ≤ 1,

then

|x| ≤ Q|x|.

Therefore {|x_i|} is a subsolution.

## Exercise 8.6: Random Walk on Z

The random walk is

i → i + 1 with probability p,

i → i - 1 with probability q,

where

p + q = 1.

The goal is to prove

the chain is persistent if and only if p = q = 1/2.

By Theorem 8.5, this is reduced to checking whether system (8.27) has a nonzero bounded nonnegative solution.

Take

i_0 = 0,

so

U = Z - {0}.

This splits into two half-lines:

positive half-line: 1, 2, 3, ...

negative half-line: -1, -2, -3, ...

## Positive Half-Line

The equation leads to the characteristic roots

r = 1,

r = q/p.

So for p ≠ q,

x_k = A + B(q/p)^k.

The boundary condition gives

A = -B.

Hence

x_k = C[1 - (q/p)^k].

If p > q, then q/p < 1, so this gives a nonzero bounded nonnegative solution.

Therefore

p > q implies transience.

## Negative Half-Line

Write

y_k = x_{-k}.

This is why y_k represents the negative half-line.

The equation leads to the characteristic roots

r = 1,

r = p/q.

So for p ≠ q,

y_k = A + B(p/q)^k.

The boundary condition gives

A = -B.

Hence

y_k = C[1 - (p/q)^k].

If p < q, then p/q < 1, so this gives a nonzero bounded nonnegative solution.

Therefore

p < q implies transience.

## Critical Case: p = q = 1/2

When p = q = 1/2, the solution on each half-line becomes linear:

x_k = A + Bk.

The boundary condition forces

A = 0.

Boundedness and nonnegativity force

B = 0.

So the only bounded nonnegative solution is the zero solution.

Therefore system (8.27) has no nonzero bounded nonnegative solution.

By Theorem 8.5, the chain is not transient. Since the random walk is irreducible, it is persistent.

## Final Conclusion

For the unrestricted one-dimensional random walk:

p > q implies transience to the positive direction.

p < q implies transience to the negative direction.

p = q = 1/2 implies recurrence.

Therefore,

the chain is persistent if and only if p = q = 1/2.

## Reflection

The main lesson is that recurrence can be tested through bounded nonnegative solutions.

A directional drift creates a nonzero bounded nonnegative solution, which signals transience.

In the symmetric case, boundedness forces the zero solution, which signals recurrence.
