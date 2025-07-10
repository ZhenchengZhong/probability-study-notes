# Study Notes: Independence and Construction of Independent Sequences

Date: 2025-07-10  
Textbook: Billingsley, Probability and Measure  
Section: p.67 (Exercise 4.15) to p.75 (Theorem 5.3)

---

> **Note**:  
> Today's focus is on the precise meaning and construction of independence for simple random variables, dyadic expansion, convergence concepts, and the detailed constructive proof of the existence of independent sequences with prescribed discrete distributions.

## Content Logic

### Convergence of Random Variables

- Reviewed the event { lim X_n = X } and its complement described via epsilon and i.o. notation:
  
  [ lim X_n = X ]^c = union_{epsilon} [ |X_n - X| >= epsilon i.o. ]

- The equivalence for convergence with probability 1:
  
  P[ |X_n - X| >= epsilon i.o. ] = 0 for each epsilon
  
- This implies convergence in probability:

  lim P[ |X_n - X| >= epsilon ] = 0

- Convergence with probability 1 implies convergence in probability, but the converse is not true.

### Counterexamples

- Example 5.4 shows that P(A_n) -> 0 does not imply P[A_n i.o.] = 0.
- Defined A_n on the unit interval using dyadic intervals to illustrate how events with P(A_n) -> 0 can still have P[A_n i.o.] = 1.

### Independence

- Defined independence of a sequence X_1, X_2, ... of simple random variables using:

  P[ X_1 in H_1, ..., X_n in H_n ] = P[ X_1 in H_1 ] ... P[ X_n in H_n ]

- Showed the connection to the case where X_i takes discrete values:

  P[ X_1 = x_1, ..., X_n = x_n ] = P[ X_1 = x_1 ] ... P[ X_n = x_n ]

- Example 5.5 discussed dyadic digits d_1(omega), d_2(omega), ... as an independent sequence modeling fair coin tossing, illustrating the independence of sigma(d_1, d_2) and sigma(d_3).

### Cyclic Representations and Independence

- Example 5.6 illustrated permutations represented as products of cycles, using the indicator variables X_k(omega) that mark the completion of a cycle.
- Showed how X_1, ..., X_n are independent and P[X_k = 1] = 1 / (n - k + 1).

### Existence of Independent Sequences (Theorem 5.3)

- Defined the distribution of a simple random variable X as:

  mu(A) = P[ X in A ]

- Theorem 5.3 states that given a sequence of discrete probability measures { mu_n } with finite support, there exists a probability space with an independent sequence { X_n } having distribution mu_n.

## Proof Sketch: Theorem 5.3

- Constructed the probability space as the unit interval with Lebesgue measure.
- Successively decomposed the interval according to the prescribed masses p_{n,i} of mu_n.
- Defined X_1, X_2, ... step-by-step using these interval decompositions, ensuring independence.
- Showed by induction that:

  P[ X_1 = x_{1,i_1}, ..., X_n = x_{n,i_n} ] = p_{1,i_1} ... p_{n,i_n}

- Concluded that X_n has distribution mu_n, and the sequence X_1, ..., X_n is independent.

## Key Ideas

- Independence in measure theory is grounded in sigma-algebra independence, specialized for simple random variables using set intersections and their probabilities.
- Dyadic expansion provides a natural model for independent fair coin tosses on the unit interval.
- Permutation cycles can be used to construct examples of independent indicator variables.
- The constructive proof of independent sequences with prescribed distributions leverages recursive partitioning of (0,1] and Lebesgue measure to align with the target distributions while preserving independence.

## Reflections

- The clean, constructive methods in Billingsley help build intuition on abstract independence definitions.
- Tracking the connection between convergence with probability 1 and in probability, and understanding when the converse fails, is crucial.
- The measure-theoretic approach provides a rigorous foundation for constructing independent random variables beyond abstract existence, with explicit procedures that can be coded or simulated.

