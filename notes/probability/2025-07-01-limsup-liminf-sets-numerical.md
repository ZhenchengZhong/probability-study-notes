# Study Notes: Limit Superior, Limit Inferior, and Set Limit Operations

Date: 2025-07-01  
Textbook: Probability and Measure by Patrick Billingsley  
Section: Problems 4.1, 4.2

---

> **Note:**  
> Today's focus is on understanding the definition, computation, and properties of lim sup, lim inf for numerical sequences and set sequences, and on verifying the numerical analogues and set operation limits systematically.

## Content logic

### Problem 4.1
- Reviewed the definitions:
  lim sup x_n = inf_n sup_{k >= n} x_k,
  lim inf x_n = sup_n inf_{k >= n} x_k.
- Connected these with:
  lim sup x_n = intersection over n of union over k >= n of x_k,
  lim inf x_n = union over n of intersection over k >= n of x_k,
  highlighting their set operation analogues.
- Proved:
  I_{lim sup_n A_n} = lim sup_n I_{A_n},
  I_{lim inf_n A_n} = lim inf_n I_{A_n},
  using indicator function arguments and the equivalence between pointwise limits of indicators and the definitions of lim sup, lim inf.

- Verified:
  lim_n A_n exists in the sense of 4.6 if and only if lim_n I_{A_n}(omega) exists for each omega, using the pointwise convergence criterion for indicators and the condition lim sup = lim inf.

### Problem 4.2 (a)
- Analyzed and proved the four key relations:
  (lim sup A_n) ∩ (lim sup B_n) ⊇ lim sup (A_n ∩ B_n),
  (lim sup A_n) ∪ (lim sup B_n) = lim sup (A_n ∪ B_n),
  (lim inf A_n) ∩ (lim inf B_n) = lim inf (A_n ∩ B_n),
  (lim inf A_n) ∪ (lim inf B_n) ⊆ lim inf (A_n ∪ B_n),
  using the definitions of lim sup and lim inf with countable unions and intersections and translating the logical structure: intersection = "and", union = "or".
- Constructed explicit counterexamples to show the inclusions can be strict (using alternating set membership constructions).

### Problem 4.2 (b)
- Wrote out and verified the numerical analogues:
  (lim sup x_n) ∧ (lim sup y_n) ≥ lim sup (x_n ∧ y_n),
  (lim sup x_n) ∨ (lim sup y_n) = lim sup (x_n ∨ y_n),
  (lim inf x_n) ∧ (lim inf y_n) = lim inf (x_n ∧ y_n),
  (lim inf x_n) ∨ (lim inf y_n) ≤ lim inf (x_n ∨ y_n),
  using the substitutions sup = max, inf = min, and lim sup = inf_n sup_{k >= n} x_k, lim inf = sup_n inf_{k >= n} x_k, combined with epsilon arguments for rigorous inequality handling.

### Problem 4.2 (c)
- Proved De Morgan-like relations for lim sup and lim inf under complements:
  lim sup A_n^c = (lim inf A_n)^c,
  lim inf A_n^c = (lim sup A_n)^c,
  by using De Morgan's laws with countable unions and intersections.
- Verified:
  lim sup A_n - lim inf A_n = lim sup (A_n ∩ A_{n+1}^c) = lim sup (A_n^c ∩ A_{n+1}),
  illustrating the "sometimes in, sometimes out" set difference interpretation under lim sup and lim inf.

### Problem 4.2 (d)
- Showed that A_n → A and B_n → B imply:
  A_n ∪ B_n → A ∪ B,
  A_n ∩ B_n → A ∩ B,
  by using:
  lim sup (A_n ∪ B_n) = lim sup A_n ∪ lim sup B_n,
  lim inf (A_n ∪ B_n) = lim inf A_n ∪ lim inf B_n,
  and
  lim sup (A_n ∩ B_n) ⊆ lim sup A_n ∩ lim sup B_n,
  lim inf (A_n ∩ B_n) = lim inf A_n ∩ lim inf B_n,
  and verifying that when lim sup = lim inf holds individually, the equality extends to unions and intersections.

## Key Ideas
- lim sup and lim inf for numerical sequences and set sequences can be computed using inf sup / sup inf formulations and unions/intersections, respectively.
- Set operations under limits reflect logical structures: union = "or", intersection = "and", complement with lim sup/lim inf flips between them.
- Epsilon arguments provide rigorous justification for inequalities in numerical analogues.
- Convergence of set sequences under lim sup = lim inf allows operations to pass to the limit.

## Reflections
- Understanding these foundational limit properties strengthens my ability to handle advanced topics in measure theory and probability limits.
- The systematic structure across sets and numerical analogues aids in recognizing patterns in proofs.
- The epsilon argument for sup/inf transitions is a key practical tool in rigorous proof writing.

## Questions
- Further explore conditions under which the strict inclusions in lim sup/lim inf operations can be equalities without additional assumptions.
- Analyze how these limit operations extend under measures and in the context of almost everywhere convergence.

