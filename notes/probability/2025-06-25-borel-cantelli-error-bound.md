# Study Notes: Borel–Cantelli Lemmas and Binary Approximation Error

Date: 2025-06-25  
Textbook: Probability and Measure by Patrick Billingsley  
Section: Examples 4.12 to 4.17 (incomplete)  

---

> **Note**:  
> Today's focus is on understanding how Borel–Cantelli lemmas apply to bounding approximation errors in dyadic expansions, including the rate at which binary approximations approach real numbers. The discussion is centered on the behavior of the run-length function l_n(ω) and the associated error e_n(ω).

## Content logic

- Example 4.12 introduces the approximation error e_n(ω) in dyadic expansion and connects it to the run length l_n(ω), with inequalities:
  - 1 / 2^{l_n(ω) + 1} ≤ e_n(ω) ≤ 1 / 2^{l_n(ω)}
- This leads to understanding how l_n(ω) controls the size of the approximation error.

- Example 4.13 applies the first Borel–Cantelli lemma to the Normal Number Theorem. If a real number fails to be normal, then a long block of 1s or 0s must appear too often. The event probabilities decay exponentially, and thus the sum of their probabilities converges. The theorem then implies that these irregularities occur only finitely often almost surely.

- Theorem 4.4 (Second Borel–Cantelli Lemma) is introduced and proven using the independence of events and a standard product-to-exponential bound.

- Example 4.14 applies the second Borel–Cantelli lemma to show that the event {l_n(ω) = 1 i.o.} occurs with probability 1, after adjusting for non-independence by considering even-numbered events.

- Example 4.15 provides a stronger version of Example 4.14 by constructing a sparse subsequence {n_k} such that:
  - n_{k+1} = n_k + r_{n_k}
  - Events A_k = {l_{n_k}(ω) ≥ r_{n_k}} are independent
  - If the series ∑ 2^{-r_n}/r_n diverges, then ∑ 2^{-r(n_k)} diverges as well
  - So by the second Borel–Cantelli lemma, these events occur infinitely often with probability 1
  - This implies that limsup l_n(ω)/log₂n = 1 almost surely

- Example 4.16 uses the inequality from (4.22). If l_n(ω) ≥ log₂ n, then e_n(ω) ≤ 1/n. This relates the binary approximation error directly to the run length.

- Equation (4.23) shows that for any ε > 0, the event {e_n(ω) ≤ 1 / n^{1+ε} i.o.} has probability zero. That is, although e_n(ω) can be smaller than 1/n occasionally, it cannot be so "too often".

- Together, (4.23) and (4.28) show that e_n(ω) has 1/n as a "lower envelope": the smallest asymptotic scale it can reach infinitely often, but not go below faster than that.

- Example 4.17 begins to reinterpret (4.23) in the context of Diophantine approximation. The substitution of x_n = 1 / n^{1+ε} by x_n = 1 / ((n-1) log 2)^{1+ε} is intended to better fit the structure of binary expansions, as the run length l_n(ω) is defined in base 2 and relates to powers of 2.

## Key Ideas

- The run length l_n(ω) determines how well ω can be approximated by its first n digits in base 2.
- The error term e_n(ω) is squeezed between exponential bounds derived from l_n(ω).
- Using Borel–Cantelli lemmas, especially the second one (under independence), we can characterize the long-run behavior of l_n(ω) and e_n(ω).
- The “envelope” interpretation gives a precise asymptotic description of how fast the approximation error can shrink.
- Subsequence construction (e.g. sparse {n_k}) is a common technique to recover independence and apply strong probabilistic results.

## Proof Sketch (for Example 4.15)

- Assume r_n is nondecreasing and ∑ 2^{-r_n} / r_n diverges.
- Define n_1 = 1, and n_{k+1} = n_k + r_{n_k}, so that the intervals [n_k, n_{k+1}) are disjoint.
- Define A_k = {d_i(ω) = 0 for all i in [n_k, n_{k+1})}, i.e. l_{n_k}(ω) ≥ r_{n_k}.
- These events are independent due to non-overlapping indices.
- Use the second Borel–Cantelli lemma to conclude P[A_k i.o.] = 1.
- Since the log₂n scale corresponds to the average maximum run of zeros, the result limsup l_n(ω)/log₂n = 1 follows.

## Reflections

- This section beautifully combines number theory, binary expansions, and probability theory through Borel–Cantelli lemmas.
- The term "lower envelope" might be counterintuitive at first, because 1/n acts as an upper bound numerically—but in probability, it describes the minimal asymptotic scale that the error term can reach repeatedly.
- The switch from 1/n^{1+ε} to 1 / ((n-1) log 2)^{1+ε} reveals how notation can be optimized to better reflect the binary structure of the problem.

