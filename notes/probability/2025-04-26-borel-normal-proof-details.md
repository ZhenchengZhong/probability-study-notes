# Study Notes: Strong Law of Large Numbers and Normal Numbers

Date: 2025-04-26  
Textbook: Billingsley, *Probability and Measure*, 3rd Ed.  
Section: The Strong Law of Large Numbers (pp. 8–11)

---

> **Note**:  
> Today's focus is on familiarizing with the English expressions used in the mathematical exposition, rather than detailed derivations or proofs.  
> The goal is to improve English comprehension and academic writing style through reading and summarizing original texts.

---

## Key Ideas

Define the set

N = { ω : lim (1/n) Σ_{i=1}^n d_i(ω) = 1/2 },

where each d_i(ω) ∈ {0,1} is the binary digit of ω.

Elements of N are called normal numbers.

The goal is to prove that the set of normal numbers has measure 1.

---

Key difficulty:  
The set N is not a finite or countable union of intervals.  
Thus, P(N) = 1 cannot be proved using elementary probability tools.

---

Introduce the notion of negligibility:

- A set A ⊂ Ω is negligible if, for every ε > 0, there exists a collection of intervals {I_k} such that:
  - A ⊂ ⋃_k I_k
  - Σ_k |I_k| < ε

This corresponds to the notion of measure zero.

Any countable union of negligible sets is negligible.  
Single points and countable sets are negligible.

---

Theorem 1.2 (Borel's Normal Number Theorem):  
The set of normal numbers has negligible complement.

---

## Proof Sketch of Theorem 1.2

Replace d_i(ω) with r_i(ω) = 2d_i(ω) - 1 ∈ {-1, +1}.

Define

s_n(ω) = Σ_{i=1}^n r_i(ω).

Goal: show that

lim (1/n) s_n(ω) = 0 for almost all ω.

---

Use probabilistic inequalities:

Key inequality:

P(ω : |s_n(ω)| ≥ nε) ≤ (1 / n⁴ε⁴) ∫₀¹ s_n⁴(ω) dω  
(Equation 1.25)

---

Expand s_n⁴(ω) into sums of products of Rademacher functions:

s_n⁴(ω) = Σ r_α(ω) r_β(ω) r_γ(ω) r_δ(ω)  
(Equation 1.26)

Depending on how the indices match:

- Some forms integrate to 1.
- Other forms integrate to 0.

---

Estimate the integral:

∫₀¹ s_n⁴(ω) dω ≤ 3n²  
(Equation 1.28)

---

Conclude:

P(ω : |(1/n) s_n(ω)| ≥ ε) ≤ (3 / n²ε⁴)  
(Equation 1.29)

---

Choose a sequence ε_n such that Σ ε_n^{-4} n^{-2} < ∞, for example:

ε_n = n^{-1/8}.

By Borel–Cantelli type arguments:

- For almost all ω, eventually |n^{-1} s_n(ω)| < ε_n.
- Thus ω is normal.

Finally, covering N^c using intervals based on A_n shows that N^c is negligible.

---

## Reflections

- An important concept is that a set can be uncountable but still have measure zero.
- The proof connects probabilistic estimates with measure-theoretic ideas.
- Borel's theorem illustrates the power of precise technical bounds in probability theory.
