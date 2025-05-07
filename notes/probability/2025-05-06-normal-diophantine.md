# Study Notes: Normal Numbers and Diophantine Approximation

Date: 2025-05-06
Textbook: Probability and Measure (Third Edition) by Patrick Billingsley
Section: Chapter 1.8–1.11

---

> **Note**:
> Today's focus is on understanding the interplay between topological smallness (nowhere dense and first category sets) and measure-theoretic smallness (negligible and trifling sets), as well as exploring Diophantine approximation arguments related to rationality and irrationality of real numbers.

## Key Ideas

* A real number ω is called normal in base 2 if the average of its binary digits converges to 1/2. Formally,
  N = { ω ∈ (0,1] : lim (1/n) Σ\_{i=1}^n d\_i(ω) = 1/2 }.
* Normal numbers form a set of full measure (not negligible) but are of the first category (can be written as a countable union of nowhere dense sets).
* A trifling set is a set that can be covered by finitely many dyadic intervals with arbitrarily small total length.
* A nowhere dense set is one whose closure has empty interior, i.e., it is “thin” everywhere.
* Not all negligible sets are of the first category, and vice versa.

## Proof Sketch

### 1.9(a)

* We showed that any trifling set must be nowhere dense.
  The key is that a set covered by finitely many small dyadic intervals cannot occupy any open interval fully, which implies its closure lacks interior points.

### 1.9(b)

* Defined a set A = (0,1] \ B where
  B = ∪\_n (r\_n − 2^{−n−2}, r\_n + 2^{−n−2}),
  and {r\_n} is an enumeration of rationals in (0,1].
* A is nowhere dense since all rational neighborhoods are removed, but it is not trifling (cannot be covered by finitely many intervals of arbitrarily small length), and not negligible (its measure is ≥ 1/2).

### 1.10(a)

* We wrote the set of normal numbers N as N ⊆ ∪*m A\_m, where
  A\_m = ∩*{n ≥ m} { ω : |(1/n) S\_n(ω) − 1/2| < 1/2 }.
* Each A\_m is nowhere dense since any small perturbation can make a sequence deviate from the bound.
* Thus, N is a countable union of nowhere dense sets, i.e., first category.

### 1.11(a)

* If x is rational, then only finitely many irreducible fractions p/q satisfy
  |x − p/q| < 1/q^2.
  For large q, such approximations can only equal x itself, as the inequality implies |aq − bp| < 1 ⇒ aq = bp.

### 1.11(b)

* If infinitely many (p,q) satisfy the inequality but only finitely many are coprime, x must be rational.
  Because irrational numbers can be approximated by infinitely many irreducible fractions with error less than 1/q^2, having only finitely many such approximants contradicts irrationality.

### 1.11(c)

* Even when φ(q) increases rapidly and A\_φ becomes negligible (by Theorem 1.6), it remains uncountable.
  Construction:
  x = Σ\_{k=1}^∞ 1/2^{α(k)},
  where α(k) grows fast enough so that the tail sums are smaller than 1/q^{φ(q)}.
  This x can be approximated by infinitely many rational truncations of itself.

## Reflections

* Topological and measure-theoretic notions of “smallness” behave very differently.
  A set can be “thin” everywhere (nowhere dense) yet have full measure, or conversely be negligible but dense.
* The equivalence between rationality and “limited approximability” is an elegant tool in Diophantine approximation.
* Constructing examples via binary expansions with rapidly increasing positions is a powerful method to build counterexamples in analysis.


