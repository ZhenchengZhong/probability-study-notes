# Study Notes: Indicator Functions and Set-Theoretic Identities

Date: 2025-05-18  
Textbook: Probability and Measure (3rd Edition, Patrick Billingsley)  
Section: Section 2 – Probability Measures (pp. 32–33, Problems 2.1–2.2)

---

> **Note**:  
> Today's focus is on translating set operations into indicator function logic (Problem 2.1), and analyzing a combinatorial identity involving unions of intersections and intersections of unions (Problem 2.2).

## Content logic

The two problems studied today focus on understanding set operations from two distinct but complementary perspectives:

- **Problem 2.1**: Expressing standard set operations via pointwise operations on indicator functions.
- **Problem 2.2**: Identifying a symmetry between k-wise intersections and (n−k+1)-wise unions in finite set systems.

---

## Key Ideas

### Problem 2.1

- Each event A ⊆ Ω can be identified with its indicator function I_A(ω), taking values in {0,1}.
- Set-theoretic operations correspond directly to pointwise numerical operations:
  - A ∪ B → I_A ∨ I_B = max(I_A, I_B)
  - A ∩ B → I_A ∧ I_B = min(I_A, I_B)
  - Aᶜ → 1 − I_A
  - A △ B → |I_A − I_B|
- Inclusion A ⊆ B holds iff I_A ≤ I_B for all ω.
- Distributive laws such as A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C) follow from verifying the equivalent pointwise identities.

### Problem 2.2

Let A₁, ..., Aₙ be events. Define:

- U_k = union of all k-wise intersections:  
  U_k = ⋃ (A_{i₁} ∩ ... ∩ A_{i_k}) over all 1 ≤ i₁ < ... < i_k ≤ n

- I_k = intersection of all k-wise unions:  
  I_k = ⋂ (A_{i₁} ∪ ... ∪ A_{i_k}) over all such k-tuples.

Then the identity:

U_k = I_{n − k + 1}

is valid for all 1 ≤ k ≤ n.

This equality reflects a deep symmetry: the elements that lie in some k-wise intersection are precisely those that lie in every (n−k+1)-wise union.

---

## Proof Sketch

### Problem 2.1

- Fix ω ∈ Ω, and evaluate both sides of each identity.
- Use the definitions of max, min, absolute value, and complement.
- For the distributive identity, verify all 8 cases of indicator values (0 or 1) for (I_A, I_B, I_C).
- Inclusion is shown to correspond to pointwise inequality: I_A(ω) ≤ I_B(ω) ⇔ ω ∈ A ⇒ ω ∈ B.

### Problem 2.2

- Direction 1 (U_k ⊆ I_{n−k+1}):  
  If ω lies in the intersection of some k sets, then it must appear in all (n−k+1)-wise unions.

- Direction 2 (I_{n−k+1} ⊆ U_k):  
  If ω fails to appear in all k-wise intersections, then one can find a (n−k+1)-wise union that does not contain ω.

- The equality thus reflects a duality between intersecting few sets and covering many sets via unions.

---

## Reflections

- Problem 2.1 was the first time I independently constructed a full logical argument using only hints. It helped strengthen my trust in my internal reasoning system.
- Problem 2.2 felt abstract at first, but became clearer once I rephrased the identity as a duality in inclusion structure. It's a beautifully symmetric statement about finite set systems.
- Both problems support the transition from naive set operations to more algebraic and combinatorial reasoning about sets.

## Questions & Confusions

- No confusion remained on Problem 2.1 after completing the pointwise reasoning.
- Problem 2.2's identity is subtle, and while the logic is sound, I want to revisit it later with diagrammatic or algebraic visualization to deepen my intuition.
