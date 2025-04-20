# Probability Theory Study Notes: Borel’s Normal Number Theorem

This repository documents my study and interpretation of foundational probability theory, particularly the construction of a probability model on the unit interval and the motivation behind Borel’s Normal Number Theorem.

## Study Context

These notes are part of my preparation for applying to research-based master's programs in statistics and probability. I aim to build a solid understanding of measure-theoretic probability through first principles, starting with classical sources.

## Topics Covered

Section 1: The Unit Interval and Probability

- Why discrete probability theory is insufficient for infinite processes
- Construction of a probability model over the unit interval (0, 1]
- Definitions of interval length and probability using Riemann integration
- Step functions and indicator functions
- The additivity of probability for disjoint intervals
- Physical motivation using models such as radioactive decay and telephone arrivals

## Key Formulas

Length of interval: |(a, b]| = b - a

Additivity of measure for disjoint sets: P(A ∪ B) = P(A) + P(B)

Riemann integral of a step function: ∫₀¹ f(ω) dω = ∑{j=1}^{k} c_j (x_j - x{j-1})


## Reflections

This section shows how classical probability can be rigorously constructed on a continuous interval using simple tools like length and step functions. Understanding how integration over indicator functions defines probability helps bridge intuition with formal mathematics. The model provides a natural way to represent both physical randomness (e.g., radioactive emission) and abstract processes like infinite coin tosses.



## Reference

Patrick Billingsley, *Probability and Measure*, 3rd Edition, John Wiley & Sons.






