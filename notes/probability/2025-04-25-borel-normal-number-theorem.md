# Study Notes: Strong Law of Large Numbers and Normal Numbers
Date: 2025-04-25# Study Notes: Strong Law of Large Numbers and Normal Numbers

Date: 2025-04-25  
Textbook: Billingsley, *Probability and Measure*, 3rd Ed.  
Section: The Strong Law of Large Numbers (pp. 8–11)

---

## Key Ideas

- Define the set  
  **N = { ω : lim (1/n) ∑_{i=1}^n d_i(ω) = 1/2 }**,  
  where each d_i(ω) ∈ {0,1} is a binary digit of ω ∈ [0,1].

  - Elements of N are called **normal numbers**.
  - The goal is to prove that the set of normal numbers has **measure 1**.

- **Key difficulty**: The set N is *not* a finite or countable union of intervals. So P(N) = 1 cannot be proved using elementary tools.

- Introduce the notion of **negligibility**:
  - A set A ⊆ Ω is *negligible* if, for every ε > 0, there exists a collection of intervals {I_k} such that:
    - A ⊆ ∪_k I_k  
    - ∑_k |I_k| < ε  
  - This idea corresponds to the notion of **measure zero**.
  - Any countable union of negligible sets is also negligible.
  - **Single points and countable sets are negligible.**

- **Theorem 1.2 (Borel's Normal Number Theorem)**:  
  The set of normal numbers has **negligible complement**.

---

## Proof Sketch of Theorem 1.2

- Replace d_i(ω) with r_i(ω) = 2d_i(ω) - 1 ∈ {−1, +1}, and define:  
  **s_n(ω) = ∑_{i=1}^n r_i(ω)**

- Goal becomes to show:  
  **lim (1/n) s_n(ω) = 0** for almost all ω

- Apply Chebyshev’s inequality:  
  **P(|s_n(ω)| ≥ nε) ≤ (1 / n²ε²) ∫₀¹ s_n²(ω) dω = 1 / (nε²)**  
  (This shows weak convergence)

- To prove negligibility of complement set N^c, use a **stronger bound**:  
  **P(|s_n(ω)| ≥ nε) ≤ (1 / n⁴ε⁴) ∫₀¹ s_n⁴(ω) dω**

- Compute s_n⁴(ω) by expanding and using pairwise orthogonality of r_i(ω), based on earlier integrals:
  - ∫₀¹ r_i(ω) r_j(ω) dω = 0 when i ≠ j
  - ∫₀¹ r_i²(ω) dω = 1
  - All terms involving 4 distinct indices vanish when integrated
  - Result:  
    **∫₀¹ s_n⁴(ω) dω ≤ n + 3n(n−1) ≤ 3n²**

- So finally we have:  
  **P(|s_n(ω)| ≥ nε) ≤ 3 / (n²ε⁴)**

---

## Constructing the Negligible Cover

- Let ε_n = n^(−1/8), then the series ∑ ε_n⁴ n^(−2) converges.

- Let A_n = { ω : |s_n(ω)/n| ≥ ε_n }, then  
  P(A_n) ≤ 3ε_n⁴ n^(−2) → ∑ P(A_n) < ∞

- So only finitely many A_n occur with high probability ⇒ ω eventually lies in the complement of all A_n ⇒ ω ∈ N

- Construct intervals covering each A_n with total length < ε, take countable union ⇒ N^c is negligible.

---

## Reflections

- Billingsley’s approach rigorously proves the **strong law** by converting probability bounds to **measure estimates** over [0,1].
- The concept of **negligible sets** (instead of assigning probabilities) avoids abstract measure theory early on.
- This connects normal numbers with practical randomness in binary expansions.
  
Textbook: Billingsley, *Probability and Measure*, 3rd Ed.  
Section: The Strong Law of Large Numbers (pp. 8–11)

## Key Ideas

- Define the set \( N = \left\{ \omega : \lim_{n \to \infty} \frac{1}{n} \sum_{i=1}^n d_i(\omega) = \frac{1}{2} \right\} \), where \( d_i(\omega) \in \{0, 1\} \) are binary digits of \( \omega \in [0,1] \).
  - Elements of \( N \) are called **normal numbers**.
  - The goal: to prove that the set of normal numbers has **measure 1** (i.e., almost all reals are normal).
  
- The key difficulty: \( N \) is not a finite or countable union of intervals, so \( P(N) = 1 \) cannot be shown using elementary methods.

- **Negligibility** is introduced to handle this:
  - A set \( A \subset \Omega \) is *negligible* if for every \( \varepsilon > 0 \), it can be covered by intervals \( I_k \) such that:
    - \( A \subset \bigcup_k I_k \)
    - \( \sum_k |I_k| < \varepsilon \)
  - This is essentially the idea of **measure zero**.

- A countable union of negligible sets is negligible. A single point set is negligible. Thus, countable sets are negligible.

- **Theorem 1.2 (Borel's Normal Number Theorem):** The set of normal numbers has negligible complement.
  - So almost every \( \omega \in [0,1] \) is normal.
  - \( N^c \) is uncountable, but **not** negligible, so we must prove \( N^c \) negligible by constructing an explicit cover.

## Proof Sketch

- Use Chebyshev-style inequality:
  - \( P\left( |s_n(\omega)| \geq n\varepsilon \right) \leq \frac{1}{n^4\varepsilon^4} \int_0^1 s_n^4(\omega) \, d\omega \)
  - Show \( \int_0^1 s_n^4(\omega) \, d\omega \leq 3n^2 \)

- Decompose \( s_n^4(\omega) \) into terms of the form \( r_i(\omega)r_j(\omega)r_k(\omega)r_l(\omega) \), and analyze each based on how the indices match.
  - If all 4 indices are distinct, the integral is 0.
  - If 2 indices match (e.g. \( r_i^2(\omega) r_j^2(\omega) \)), integral is 1.
  - Total contribution bounded by \( n + 3n(n - 1) \leq 3n^2 \).

- Use this bound and Chebyshev to show \( P(|s_n(\omega)| \geq n\varepsilon) \leq \frac{3}{n^2\varepsilon^4} \).

- Construct events \( A_n = \{ \omega : |s_n(\omega)| \geq n\varepsilon_n \} \) with \( \varepsilon_n = n^{-1/8} \), so \( \sum P(A_n) < \infty \).

- Then \( \omega \) lies in only finitely many \( A_n \) almost surely \( \Rightarrow \frac{1}{n}s_n(\omega) \to 0 \), so \( \omega \in N \).

- Use countable union of intervals covering \( A_n \) with small total length to show \( N^c \) is negligible.

## Reflections

- Introduces the concept of negligibility to extend classical probability to more general sets.
- Stronger than the weak law: convergence almost surely instead of just in probability.
- Clever use of orthogonality and Chebyshev's inequality for bounding probabilities.
- This proof is elegant and foundational for understanding measure-theoretic probability.

## Reference
Patrick Billingsley, *Probability and Measure*, 3rd Edition, Wiley.  
Section 1.2: The Strong Law of Large Numbers and Normal Numbers.

