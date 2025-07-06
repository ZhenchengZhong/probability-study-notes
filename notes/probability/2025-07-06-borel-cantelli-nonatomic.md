# Study Notes: Independence, limsup, Borel-Cantelli, and Nonatomic Measures

Date: 2025-07-06  
Textbook: Billingsley, Probability and Measure (3rd Edition)  
Section: Exercises 4.3 – 4.14

---

> **Note:**  
> Today's focus is on independence, limsup and liminf geometric interpretation, the Borel-Cantelli lemmas, Kolmogorov 0-1 Law, and the construction of nonatomic measures using infinite sequences of independent events.

## Content Logic

- Review and solve Exercises 4.3 to 4.14 systematically.
- Understand how limsup and liminf behave under rotation and geometric transformation (4.3, 4.4).
- Apply the Borel-Cantelli lemmas in identifying measure-zero vs measure-one limsup sets.
- Learn how to connect Kolmogorov 0-1 Law with independence and tail events.
- Construct explicit small positive measure sets to verify nonatomicity of a measure under infinite independent event structures.

## Key Ideas

- Limsup and liminf are geometrically intuitive when visualized using rotations of squares in (0,1) under rational and irrational rotations.
- The first Borel-Cantelli lemma: if the sum of probabilities is finite, the limsup set has measure zero.
- The second Borel-Cantelli lemma: if the sum of probabilities is infinite and events are independent, the limsup set has measure one.
- Kolmogorov 0-1 Law ensures that tail events under independence have probabilities in {0, 1}.
- To prove a measure is nonatomic, it suffices to construct, using independence, intersections of events with positive measure that can be made arbitrarily small.

## Proof Sketch

- For 4.3, examined limsup and liminf under rational and irrational rotations and their geometric interpretation.
- For 4.4, constructed a sequence to satisfy strict inequalities in measure limit relations.
- For 4.5 and 4.6, solidified the concept of convergence in measure and independence of events that do not extend to independence as a whole.
- For 4.7–4.9, explored the implications of partitions and sigma-algebra generation, connecting to measure-theoretic properties.
- For 4.10 and 4.11, examined nonmeasurable sets with inner measure zero and outer measure one, used in constructing examples illustrating Borel-Cantelli applications.
- For 4.12, learned to use integral test techniques to determine convergence, relevant for boundary classifications (inner vs outer boundaries).
- For 4.13, applied Borel-Cantelli to measure-zero sets under infinite approximations and diophantine conditions.
- For 4.14, demonstrated that under infinite sequences of independent events with infinite sums of min(p, 1-p), it is possible to construct arbitrarily small positive measure intersections, thus proving the measure is nonatomic.

## Questions & Confusions

- The technical distinctions between limsup sets in measure zero vs measure one under different independence and summability conditions.
- The precise intuitive role of the tail sigma-algebra in applying Kolmogorov 0-1 Law vs the practical sufficiency of Borel-Cantelli in most constructions.
- How independence and small upper bounds on probabilities collaborate to construct nonatomicity proofs without needing Kolmogorov 0-1 Law explicitly.

## Reflections

- Geometric visualizations greatly help in understanding limsup, liminf, and their measure-theoretic interpretations.
- Borel-Cantelli lemmas are deeply practical tools and serve as bridges from combinatorial intuition to measure-theoretic rigor.
- Learning to construct explicit intersections to demonstrate nonatomicity strengthens the understanding of measure structures in probability spaces.
- Maintaining clear notation when dealing with infinite sequences, independence, and intersections is critical to avoid logical errors in measure arguments.

