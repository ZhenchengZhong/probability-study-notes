# Study Notes: Bold Play and Dubins–Savage (pp. 101–108)

Date: 2025-08-13  
Textbook: Probability and Measure, Billingsley (3rd ed.)  
Section: Section 7 — Gambling Systems (pp. 101–108)

---

> Note:  
> Today's focus is on the bold-play policy, the function Q(x) and its recursion, the proof strategy for optimality in the subfair case, the timid-play contrast via SLLN, and quick reads of Examples 7.8–7.9 and Problems 7.1–7.2.

## Content logic
- Start from the bold-play policy: at fortune x in [0,1], bet all your fortune if x ≤ 1/2, and bet just enough to reach 1 if you win when x ≥ 1/2. Stop when fortune hits 0 or 1.
- Define Q_π(x) = P[F_τ = 1 | F_0 = x] for a policy π; Q(x) is the same under bold play.
- Goal (Dubins–Savage theorem here): in the subfair case p ≤ q, Q_π(x) ≤ Q(x) for every policy π and all x.
- Key step: show Q(x) satisfies a simple recursion that mirrors “win then continue” vs “lose then continue,” and prove an averaging inequality that forces optimality.
- Then interpret Q(x) as a distribution function of a Bernoulli–binary series, identify the fair case p = 1/2 where Q(x) ≡ x, and compare with timid play where success probability collapses.

## Key Ideas
- Stopping time: τ = min{n ≥ 0 : F_n ∈ {0,1}}.
- Bold-play stake function: β(x) = x for x ≤ 1/2; β(x) = 1 − x for x ≥ 1/2.
- Recursion for Q(x) (eq. 7.30):
  - Q(x) = p Q(2x), for 0 ≤ x ≤ 1/2.
  - Q(x) = p + q Q(2x − 1), for 1/2 ≤ x ≤ 1.
- Monotonicity and continuity: Q is increasing and continuous on [0,1]. Dyadic differences satisfy
  - Q(.u_1…u_n + 2^{−n}) − Q(.u_1…u_n) = p_{u_1} p_{u_2} … p_{u_n}, where p_0 = p, p_1 = q and .u_1…u_n is the binary fraction.
- Subfair optimality is reduced to verifying the inequality (eq. 7.28):
  - Q(x) ≥ p Q(x + t) + q Q(x − t), whenever 0 ≤ x − t ≤ x ≤ x + t ≤ 1.
- Case analysis proves the last inequality by mapping (r, s) = (x − t, x + t) through the recursion and induction on dyadic scales.
- Interpretation (eq. 7.33): for independent {Z_i} with P[Z_i = 0] = p, P[Z_i = 1] = q,
  - Q(x) = P[ Σ_{i=1}^∞ Z_i 2^{−i} ≤ x ].
- Fair case p = 1/2: Q(x) ≡ x for all policies that stop at {0,1}.
- Timid play (ε-timid): W_n = min{ε, F_{n−1}, 1 − F_{n−1}}. If p < q, then by the strong law, lim_{ε→0} Q_ε(x) = 0 for 0 ≤ x < 1.

## Proof Sketch
- Martingale/conditioning step: for any policy π, write F_n^* and show E[Q(F_n^*)] ≤ E[Q(F_{n−1}^*)]. With optional stopping at τ, obtain E[Q(F_τ)] ≤ Q(F_0).
- Since Q(1) = 1 and Q(0) = 0, we get P[F_τ = 1] ≤ Q(F_0) under any π; hence Q is optimal if we can build Q with the bold-play recursion and continuity.
- Establish the recursion by conditioning on the first stake under bold play:
  - If x ≤ 1/2, you must first win (probability p) to move to 2x, then continue: Q(x) = p Q(2x).
  - If x ≥ 1/2, you either win immediately (probability p) or lose and continue from 2x − 1: Q(x) = p + q Q(2x − 1).
- Prove continuity/monotonicity via dyadic increments (binary expansion) and the positive differences in 7.32.
- Prove the averaging inequality by setting r = x − t, s = x + t, a = (r + s)/2 and showing Δ(r,s) = Q(a) − p Q(s) − q Q(r) ≥ 0 across four cases:
  - Case 1: s ≤ 1/2 → Δ(r,s) = p Δ(2r, 2s).
  - Case 2: 1/2 ≤ r → Δ(r,s) = q Δ(2r − 1, 2s − 1).
  - Case 3: r ≤ a ≤ 1/2 ≤ s → reduce to max of two earlier Δ’s.
  - Case 4: r ≤ 1/2 ≤ a ≤ s → reduce using identities Q(2a − 1) = p Q(4a − 2) and Q(2a − 1/2) = p + q Q(4a − 2).
- Conclusion: Q_π(x) ≤ Q(x) for all π when p ≤ q (Dubins–Savage optimality of bold play).

## Examples
- Example 7.8: target from 0.9 to 1. Fair game p = 1/2 gives success probability 0.9 for any boundary-stopping policy; at red–black p = 18/38, bold play yields Q(.9) ≈ 0.88 (much larger than unit-stake chance 0.00003).
- Example 7.9: capital 100, goal 20,000. Unit stakes: success 0.005 (fair) and about 3 × 10^{−911} (red–black). Bold play at red–black still gives about 0.003. Moral: when you must gamble in a subfair game, bold play maximizes survival probability.
- Non-unique optimal policies: one can scale bold play on [0, 1/2] (bet x for x ≤ 1/4 and 1/2 − x for 1/4 ≤ x ≤ 1/2), then switch to ordinary bold play once at 1/2; overall success probability still equals Q(x).

## Exercises noted
- Problem 7.1: if initial capital a is replaced by infinity in the classical ruin/increase-by-b model with ρ > 1, the success chance is multiplied by 1 + θ. Show 0 < θ < (ρ^{a} − 1)^{−1} < (a (ρ − 1))^{−1}. Link back to Example 7.3.
- Problem 7.2: show that termination (hit c or ruin) has probability 1. For p ≠ q use the strong law; for all p use Borel–Cantelli by noting that non-termination would forbid a run of c consecutive +1’s.

## Questions & Confusions
- I want to re-derive 7.32 carefully from 7.31 and check the role of p_0, p_1 in the binary-expansion argument.
- Optional stopping invocation (via Theorem 5.4) deserves a clean write-up with precise measurability steps for Q(F_n^*).

## Reflections
- Intuition is sharp: in subfair games, fewer rounds help; bold play minimizes exposure time. Timid play is defeated by the negative drift (p − q < 0) in S_n via the strong law. The binary interpretation of Q(x) is a neat bridge to measure theory and will reappear later as a singular distribution function.
