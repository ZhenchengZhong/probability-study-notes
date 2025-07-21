# Study Notes: Borel–Cantelli Lemmas and Types of Convergence

Date: 2025-07-21  
Textbook: Probability and Measure by Patrick Billingsley  
Section: Exercises 5.11–5.17  

---

> **Note**:  
> Today's focus is on mastering Borel–Cantelli Lemma II, understanding the distinctions between pointwise, uniform, almost sure, and in-probability convergence, and constructing counterexamples.

## Content Logic

### Exercise 5.11  
Established equivalence between uniform convergence to 0 and sup_x |f_n(x)| → 0.  
Key idea: uniform convergence is a uniform bound on deviation across all x, captured by the supremum.

### Exercise 5.12  
Gave a counterexample: pointwise convergence can hold even when sup_x |f_n(x)| does not go to 0 ⇒ no uniform convergence.  
Used a “moving spike” construction to show this.

### Exercise 5.13  
Formalized: if sup_x |f_n(x)| → 0, then f_n converges to 0 uniformly.  
Explained it directly via ε-definition: uniform convergence precisely means the sup deviation tends to 0.

### Exercise 5.14  
Defined a piecewise triangular function f_n(x) and analyzed:

- f_n(x) → 0 pointwise 
- Not uniformly (since sup |f_n(x)| = n → ∞) 
- ∫ f_n(x) dx = 1 for all n ⇒ not converging to 0   

Key idea: convergence in pointwise sense doesn't imply uniform convergence or convergence of integrals.

### Exercise 5.15  
Used Theorem 5.3 to construct independent events A_n with P(A_n) = p_n → 0 and ∑ p_n = ∞.  
By Borel–Cantelli Lemma II ⇒ P(A_n i.o.) = 1.  
This gives a counterexample to the converse of Theorem 5.2(ii): convergence in probability does not imply almost sure convergence.

### Exercise 5.16  
(Conceptually similar, skipped detailed proof here.)

### Exercise 5.17(a)  
Showed: if X_n →_P X and f is continuous, then f(X_n) →_P f(X).  
Used ε–δ continuity definition and Markov inequality logic.  
Important because it demonstrates stability of convergence under continuous mappings.

### Exercise 5.17(b)  
Proved: if E[|X_n − X|] → 0 then X_n →_P X  
(using Markov inequality).  
Then gave a counterexample where X_n →_P X but E[|X_n − X|] does **not** → 0:  
spike-at-n example with P(X_n = n) = 1/n.  
Key idea: convergence in probability is weaker than L¹ convergence.

## Key Ideas

- Borel–Cantelli Lemma II is central for constructing probabilistic counterexamples.
- Supremum norms distinguish uniform convergence from pointwise.
- Convergence in probability can behave counterintuitively without implying almost sure or L¹ convergence.
- Continuous functions preserve convergence in probability.

## Reflections

These exercises sharpened the distinction between modes of convergence and trained me to use counterexamples strategically. The 5.14 and 5.15 examples are likely to reappear in more advanced measure-theoretic probability discussions.

