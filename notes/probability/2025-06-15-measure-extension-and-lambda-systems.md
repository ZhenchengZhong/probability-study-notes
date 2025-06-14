# Study Notes: Tarski's Theorem, Measure Extension, and λ-system Properties

Date: 2025-06-15  
Textbook: Probability and Measure (3rd Edition) by Patrick Billingsley  
Section: Problems 3.8–3.11  

---

> **Note**:  
> Today's focus is on understanding the extension of finitely and countably additive measures using Zorn's Lemma and on characterizing λ-systems via equivalent axioms.

## Content logic

This session focuses on Problems 3.8 to 3.11, which build on foundational ideas of measure extension and system characterizations.

- Problem 3.8 introduces Tarski's theorem and asks to prove it using Zorn’s Lemma.
- Problem 3.9 investigates the possibility and limitations of using Zorn’s Lemma in extending a countably additive measure.
- Problem 3.10 introduces the notion of complete extensions of probability measures, and the uniqueness of the minimal complete extension.
- Problem 3.11 revisits the definition of a λ-system and characterizes it via alternative but equivalent axioms.

## Key Ideas

- **Tarski's Theorem**: Any finitely additive probability measure on a field has a finitely additive extension to the full power set.
- **Zorn’s Lemma**: Often used to extend structures by identifying maximal elements in partially ordered sets, applicable in (3.8) but breaks down in (3.9).
- **σ-additivity and completeness**: Complete extensions preserve measure-zero sets and allow measurable sets to include subsets of null sets.
- **Minimal complete extension**: Constructed by equivalence classes modulo null sets using symmetric difference.
- **λ-system equivalence**: A system is a λ-system if and only if it satisfies the closure under increasing limits, contains the universal set, and is closed under relative complements within the system.

## Proof Sketch

### 3.8 – Tarski’s Theorem with Zorn’s Lemma

Let M be the set of all finitely additive extensions of a given finitely additive measure on a field, ordered by inclusion. Zorn’s Lemma implies a maximal extension exists. By standard transfinite argument, this maximal extension must be defined on the whole power set, proving the theorem.

### 3.9 – Limitations of Zorn’s Lemma for σ-additivity

Part (b) highlights the failure when trying to extend countably additive measures to all subsets using Zorn’s Lemma. The issue arises because countable additivity is not preserved under pointwise limits of arbitrary chains of extensions. This breaks the upward-closedness required in the Zorn’s Lemma argument.

### 3.10 – Uniqueness of the Minimal Complete Extension

Define F⁺ as the collection of all A such that A △ B ⊆ C for some B, C ∈ F and P(C) = 0. Then:

- F⁺ is a σ-field.
- P⁺(A) = P(B) is well-defined.
- (Ω, F⁺, P⁺) is a complete probability space.
- Any complete extension (Ω, F₁, P₁) of (Ω, F, P) satisfies F⁺ ⊆ F₁ and P₁ agrees with P⁺ on F⁺.
- This construction matches the completion via outer and inner measure.

### 3.11 – Equivalent Conditions for a λ-system

(a) Show a λ-system satisfies:

- λ₄: A, B ∈ L and A ∩ B = ∅ imply A ∪ B ∈ L
- λ₅: A₁, A₂, … ∈ L and Aₙ ↑ A imply A ∈ L
- λ₆: A₁, A₂, … ∈ L and Aₙ ↓ A imply A ∈ L

(b) Prove that L is a λ-system if and only if it satisfies:

- λ₁: Ω ∈ L
- λ₂′: A, B ∈ L and B ⊆ A imply A \ B ∈ L
- λ₅: Closure under increasing limits

This characterization is foundational in proving Dynkin's π-λ theorem.

## Questions & Confusions

- In Problem 3.9(b), is there a known counterexample that illustrates why the Zorn's Lemma argument fails for σ-additive extension?
- For 3.10(b), does the minimal complete extension coincide with the Carathéodory extension on σ-algebras generated from fields?

## Reflections

This set of problems makes clear the delicate difference between finite additivity and countable additivity. While Zorn's Lemma is powerful, it must be used with care—particularly when limit processes are involved, as in σ-additivity. The construction of F⁺ in 3.10 is not only elegant but also reinforces how null sets underpin the definition of completeness. Finally, the alternative axiomatization of λ-systems in 3.11 ties nicely into broader measure theory concepts and the structure of σ-algebras.
