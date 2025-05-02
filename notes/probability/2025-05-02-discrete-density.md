# Study Notes: Discrete Probability Spaces and Density in (0,1)

Date: 2025-05-02
Textbook: *Probability and Measure* by Patrick Billingsley (3rd Edition)
Section: Chapter 1, Problems 1.1–1.2

---

> **Note**:
> Today's focus is on the structure of discrete probability spaces, impossibility results for infinite independent events, and the density of rational and irrational numbers in the unit interval.

## Key Ideas

* A discrete probability space, where the sample space is countable and each point has positive measure summing to 1, cannot support a sequence of infinitely many independent events with fixed nontrivial probability such as 1/2.
* The intuition is that such a space lacks the capacity to represent the complexity of infinite independence — for example, the set of outcomes corresponding to independent coin tosses has the cardinality of the continuum, while a discrete space can only hold countably many.
* In Problem 1.1(b), the result is extended to events with varying probabilities. If the series of min(p\_n, 1−p\_n) diverges, the sequence is “too random” to be realized independently in a discrete space.
* Problem 1.2 shifts focus to topological properties: showing that both the set of reduced rationals and their complement are dense in the interval (0,1).

## Proof Sketch

### For 1.1(a):

* Assume toward contradiction that (A\_n) is an infinite sequence of independent events in a discrete probability space with P(A\_n) = 1/2.
* The collection of all possible outcomes (sequences of heads and tails) would be uncountable (like binary sequences), but the sample space is countable. Contradiction.

### For 1.1(b):

* Define α\_n = min(p\_n, 1 − p\_n). The quantity α\_n represents how far the event is from being trivial (probability close to 0 or 1).
* If Σ α\_n diverges, then the cumulative “randomness” is too great to encode in a countable space while maintaining independence.
* Formal proofs use entropy arguments or rely on the idea that independence of events imposes lower bounds on the number of distinguishable outcome configurations, which cannot be met in a discrete setup.

### For 1.2:

* Let N be the set of reduced fractions in (0,1). For any interval (a,b), one can always find p/q ∈ (a,b) with gcd(p,q) = 1. Hence N is dense.
* The complement N^c consists of irrational numbers in (0,1), and irrationals are also known to be dense in R, hence also dense in (0,1).
* Thus, both N and N^c are dense.

## Reflections

* These problems illustrate the essential difference between countable and uncountable probability structures. Infinite independence, while natural in coin tossing, is fundamentally non-discrete.
* The density argument in 1.2 is a helpful reminder that “most” of the real numbers are irrational, yet the rationals are still topologically rich.
* The condition Σ α\_n = ∞ in 1.1(b) echoes ideas from information theory: when randomness accumulates beyond a certain threshold, encoding it discretely becomes impossible.


