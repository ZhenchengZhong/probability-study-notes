# Study Notes: Expected Value, Convexity, and Hölder/Young Inequalities

Date: 2025-07-14  
Textbook: Probability and Measure by Patrick Billingsley (3rd ed.)  
Section: pp. 76–79  

---

> **Note**:  
> Today's focus is on understanding the definition of expected value for simple random variables, its properties, its integral representation using tail probabilities, the geometric meaning of convex functions, and how Hölder and Young inequalities relate to Lp spaces.

## Content Logic

### 1. Definition of Expected Value

- For a simple random variable X written as X = ∑ x_i I_{A_i}, the expected value is defined as:

  E[X] = ∑ x_i P(A_i)

- Alternatively, using the distribution of X:

  E[X] = ∑_{x ∈ Range(X)} x · P[X = x]

- These two forms are equivalent and both emphasize that E[X] only depends on the distribution of X.

---

### 2. Basic Properties

- Linearity:  
  E[αX + βY] = α E[X] + β E[Y]

- Order preservation:  
  If X ≤ Y (pointwise), then E[X] ≤ E[Y]

- Absolute value inequality:  
  |E[X]| ≤ E[|X|]

- Difference inequality:  
  |E[X - Y]| ≤ E[|X - Y|]

- Expectation of indicator:  
  E[I_A] = P(A)

- Expectation of constant:  
  E[c] = c

---

### 3. Dominated Convergence for Simple Random Variables

- Theorem 5.4 states:  
  If X_n → X almost surely and the sequence {X_n} is uniformly bounded, then:

  E[X] = lim E[X_n]

- This is a discrete version of the Dominated Convergence Theorem, using uniform boundedness in place of a dominating function.

---

### 4. Tail Sum Representation of Expectation

- For a nonnegative discrete random variable X with ordered support 0 ≤ x_1 < x_2 < ... < x_k:

  E[X] = x_1 P[X ≥ x_1] + ∑_{i=2}^k (x_i - x_{i-1}) P[X ≥ x_i]

- This sum corresponds to the area under a step function representing P[X ≥ x].

- Hence, the expectation can be expressed as:

  E[X] = ∫₀^∞ P[X ≥ x] dx

- This is formula (5.29), which bridges discrete sums and integral intuition.

---

### 5. Convex Functions and Geometric Meaning

- A function φ is convex on an interval if for all 0 ≤ p ≤ 1 and x, y in that interval:

  φ(px + (1 - p)y) ≤ p φ(x) + (1 - p) φ(y)

- Geometrically, this means:  
  The chord connecting (x, φ(x)) and (y, φ(y)) lies above the graph of φ.  
  The graph of φ “holds up” the chord from below—this is why convex functions are “bowl-shaped” or “open upwards”.

- If φ is twice differentiable, then φ''(x) ≥ 0 implies φ is convex.

---

### 6. Lᵖ Spaces and Hölder/Young Inequalities

#### Definition of Lᵖ:

- Lᵖ(μ) = { f : ∫ |f|^p dμ < ∞ }

- The Lᵖ norm is defined as:

  ||f||_p = ( ∫ |f|^p dμ )^{1/p}

#### Hölder’s Inequality:

- If 1/p + 1/q = 1, and f ∈ Lᵖ, g ∈ L^q, then:

  ∫ |fg| dμ ≤ ||f||_p · ||g||_q

- Special case p = q = 2 gives the Cauchy–Schwarz inequality.

#### Young’s Inequality (for scalars):

- For a, b ≥ 0 and 1/p + 1/q = 1:

  ab ≤ a^p/p + b^q/q

- Young’s inequality underlies the proof of Hölder’s inequality.

---

## Reflections

- Today’s reading clarified the geometric intuition behind convexity and its deep connection with expectation via Jensen’s inequality.
- The tail-integral expression of expected value provides a powerful link between discrete and continuous probability.
- Understanding Lᵖ spaces and Hölder’s inequality is essential for advanced probability and analysis, and appears repeatedly in the study of measure concentration, dual norms, and optimization.

