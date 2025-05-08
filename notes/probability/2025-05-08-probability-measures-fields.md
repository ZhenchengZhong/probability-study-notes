# Study Notes: Probability Measures and Fields

Date: 2025-05-08
Textbook: *Probability and Measure* by Patrick Billingsley (3rd Edition)
Section: Chapter 2 – Probability Measures, pp. 17–20

---

> **Note**:
> Today's focus is on understanding the construction of sample spaces in probability theory, the motivation for assigning probabilities to various types of sets, and the formal definitions of fields and σ-fields.

## Key Ideas

* A sample space Ω is the set of all possible outcomes ω of a probabilistic experiment.
  Examples range from finite sets like {0,1,…,n} to continuous ones such as the unit interval \[0,1].

* Events are subsets of Ω. Probabilities should ideally be assigned to as many subsets as possible.

* Some sets, such as the set of normal numbers N (those satisfying lim n⁻¹s\_n(ω) = 0), are not finite unions of intervals. These motivate the extension of the probability framework beyond simple intervals.

* Not all subsets of Ω can or should receive a probability in an ad hoc manner. A systematic approach is necessary.

## Defining Fields

* A field of subsets of Ω is a class F such that:

  * Ω ∈ F
  * A ∈ F ⇒ Aᶜ ∈ F
  * A, B ∈ F ⇒ A ∪ B ∈ F

* By DeMorgan’s law and closure under complementation, closure under finite unions is equivalent to closure under finite intersections.

* This leads to the equivalent condition:

  * A, B ∈ F ⇒ A ∩ B ∈ F

* Fields are also known as finitely additive fields.

## Defining σ-fields

* A class F is a σ-field if it is a field and additionally closed under countable unions:

  * A₁, A₂, … ∈ F ⇒ A₁ ∪ A₂ ∪ … ∈ F

* Again, using DeMorgan’s law:

  * A₁, A₂, … ∈ F ⇒ A₁ ∩ A₂ ∩ … ∈ F

* A set in F is called measurable with respect to F, or an F-set.

## Examples and Applications

* The field B₀ consists of all finite disjoint unions of subintervals of (0,1], plus the empty set. B₀ is closed under complement and finite intersection but **not** under countable operations.

* B₀ is **not** a σ-field: it does not contain singletons or the normal number set N from earlier in the section, which are formed through countable intersections or unions.

* This motivates the need for working within σ-fields when building a full probabilistic model that assigns probability to a broader class of events.

## Reflections

* The distinction between a field and a σ-field is foundational for modern probability theory.
  While fields are sufficient for simple, finite-event spaces, only σ-fields can support rigorous definitions of probability on infinite or continuous spaces.

* Building up from intuitive examples to formal structures helps bridge the gap between practical motivation (e.g. coin tosses, gambler’s ruin) and abstract measure-theoretic rigor.


