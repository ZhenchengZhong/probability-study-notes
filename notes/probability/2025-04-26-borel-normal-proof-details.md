# Study Notes: Strong Law of Large Numbers and Normal Numbers

Date: 2025-04-26  
Textbook: Billingsley, *Probability and Measure*, 3rd Ed.  
Section: The Strong Law of Large Numbers (pp. 8–11)

---

## Key Ideas

- Define the set

  **N = { ω : lim (1/n) Σ_{i=1}^n d_i(ω) = 1/2 }**,  
  where each **d_i(ω) ∈ {0,1}** is the binary digit of **ω**.

- Elements of **N** are called **normal numbers**.

- The goal is to prove that the set of normal numbers has **measure 1**.

---

- **Key difficulty**:  
  The set **N** is **not** a finite or countable union of intervals.  
  Thus, **P(N) = 1** cannot be proved using elementary probability tools.

---

- Introduce the notion of **negligibility**:
  - A set **A ⊂ Ω** is **negligible** if, for every **ε > 0**, there exists a collection of intervals **{I_k}** such that:
    - **A ⊂ ⋃_k I_k**
    - **Σ_k |I_k| < ε**
  - This idea corresponds to the notion of **measure zero**.
  - Any countable union of negligible sets is negligible.
  - **Single points** and **countable sets** are negligible.

---

- **Theorem 1.2 (Borel's Normal Number Theorem)**:
  
  **The set of normal numbers has negligible complement.**

---

## Proof Sketch of Theorem 1.2

- Replace **d_i(ω)** with **r_i(ω) = 2d_i(ω) - 1 ∈ {-1, +1}**.

- Define:

  **s_n(ω) = Σ_{i=1}^n r_i(ω)**

- Goal: show that

  **lim (1/n) s_n(ω) = 0** for almost all **ω**.

---

- Use probabilistic inequalities:
  - Key inequality:

    **P(ω : |s_n(ω)| ≥ nε) ≤ (1 / n⁴ε⁴) ∫₀¹ s_n⁴(ω) dω**  
    (Equation 1.25)

---

- Expand **s_n⁴(ω)** into sums of products of Rademacher functions:

  **s_n⁴(ω) = Σ r_α(ω) r_β(ω) r_γ(ω) r_δ(ω)**  
  (Equation 1.26)

---

- Analyze different cases depending on how the indices match:
  - Some forms integrate to 1
  - Others integrate to 0

---

- Estimate the integral:

  **∫₀¹ s_n⁴(ω) dω ≤ 3n²**  
  (Equation 1.28)

---

- Conclude:

  **P(ω : |(1/n) s_n(ω)| ≥ ε) ≤ (3 / n²ε⁴)**  
  (Equation 1.29)

---

- Choose a sequence **ε_n** such that **Σ ε_n^{-4} n^{-2} < ∞**, for example:

  **ε_n = n^{-1/8}**

- Then, by Borel–Cantelli type arguments:
  - For almost all **ω**, eventually **|n^{-1} s_n(ω)| < ε_n**.
  - Thus **ω** is normal.

- Cover **Nᶜ** using intervals from sets **A_n** and prove **Nᶜ** is negligible.

---

## Reflections

- Important concept: a set can be **uncountable** but still **have measure zero**.
- The proof links elementary probability bounds to Lebesgue measure ideas.
- Borel's theorem shows the power of technical estimates in probability theory.
