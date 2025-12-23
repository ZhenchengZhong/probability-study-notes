# Study Notes: Gambling Systems — Timid Play, Optional Stopping, and Betting Schemes

Date: 2025-12-23  
Textbook: Feller, An Introduction to Probability Theory and Its Applications (Vol. 1)  
Section: Section 7 (Gambling Systems), Problems 7.1–7.7 + related remarks on selection systems

---

> Note:  
> Today's focus is on proof logic (SLLN / Borel–Cantelli / optional stopping) and on translating English arguments into clean probabilistic reasoning.

## Content logic
- Timid play (ε-timid betting) and why it collapses under negative drift (p < q).
- Gambler’s ruin probabilities: finite boundary vs “infinite capital” hitting probability.
- Theorem 7.2 as an “expectation cannot be beaten” principle (fair/subfair cases).
- Concrete strategies:
  - Von Neumann extraction (biased coin -> fair coin).
  - Proportional betting (multiplicative wealth process).
  - Doubling strategy with finite capital.
  - “Progress and pinch” (wager random walk) and when termination is certain.

## Key ideas

### 1) ε-timid policy: why “small bets” can be worse when p < q
The ε-timid policy sets the wager as:
W_n = min{ ε, F_{n-1}, 1 - F_{n-1} }  
and the game stops when F_n hits 0 or 1.

Heuristic: away from the boundaries, W_n ≈ ε, so the wealth behaves like
F_n ≈ x + ε S_n, where S_n = X_1 + ... + X_n and X_i is +1 for a win, -1 for a loss.

If p < q, then E[X_1] = p - q < 0, and SLLN gives:
(1/n) S_n -> p - q  (almost surely),
so S_n -> -∞ and the partial maxima sup_k S_k stay finite (almost surely).

This implies: for small enough ε, with very high probability the path never reaches 1, but it will eventually be pushed below 0 in the linearized model. In the actual wealth process you cannot go below 0, so “trying to go negative” translates into hitting 0 first (ruin). Hence the success probability Q_ε(x) goes to 0 as ε -> 0 (for 0 ≤ x < 1).

What I took away:
- Negative drift + “need many small steps to reach 1” is a losing combination.
- The proof structure is: SLLN (drift) -> control of sup -> pick ε -> show ruin dominates.

### 2) Infinite capital vs finite capital: the probability boost is limited (Problem 7.1 / Example 7.3)
For biased random walk with p < q, the probability to ever gain b units with unlimited capital is:
P(sup_n S_n ≥ b) = (p/q)^b.

With finite initial capital a and upper goal a + b, the success probability is smaller; letting “capital go infinite” multiplies success by a factor 1 + θ, but θ is small when a is large.
Key inequality in the problem: 0 < θ < (ρ^a - 1)^(-1) < (a(ρ - 1))^(-1), with ρ = q/p > 1.

Interpretation:
- Unlimited capital does not magically fix negative drift; it only removes the absorbing boundary at 0.
- In “red-and-black” roulette style examples, (p/q)^b can already be tiny; removing bankruptcy does not change the fact that the target event is rare.

### 3) Theorem 7.2: the “expectation cannot be beaten” rule
The version used in the later problems can be read as:
- If p ≤ 1/2, then for any policy, expected wealth does not increase at stopping: E[F_τ] ≤ F_0.
- If p = 1/2 and the policy is bounded (so the stopped wealth has finite range), then E[F_τ] = F_0.

This is the backbone behind “Martingale / optional stopping” style arguments:
- In a fair game, you can reshuffle outcomes but not improve expected value (under reasonable stopping rules).
- In a subfair game, expected value only goes down.

### 4) Von Neumann extraction (Problem 7.4): biased coin -> fair coin
Pair outcomes (X_1, X_2), (X_3, X_4), ... and:
- discard ++ and --,
- keep the second element of +- and -+.

Reason it becomes fair:
- P(+-) = p q and P(-+) = q p, which are equal.
- Conditional on “a discordant pair happened”, output +1 and -1 are equally likely, so P(Z = +1) = P(Z = -1) = 1/2.
Independence comes from using non-overlapping pairs (fresh independent blocks each time).

Practical note:
- Output rate is 2 p q, so it slows down when p is close to 0 or 1.

### 5) Proportional betting (Problem 7.5): multiplicative decay in subfair case
If W_n = θ F_{n-1} with 0 < θ < 1 and X_n ∈ {+1, -1}, then:
F_n = Π_{k=1}^n (1 + θ X_k).

Taking logs turns the product into a sum:
log F_n = Σ_{k=1}^n log(1 + θ X_k).

The given identity rewrites log F_n in terms of S_n/n plus constants, and in the subfair case (p < 1/2),
S_n/n -> p - q < 0 (SLLN),
which forces log F_n -> -∞ and therefore F_n -> 0 with probability 1.

Key intuition:
- Additive drift is already negative, and multiplicative dynamics amplify this into exponential decay.

### 6) Doubling with finite capital (Problem 7.6)
Doubling scheme:
W_1 = 1, W_n = 2 W_{n-1}, stop after the first win.

If capital were infinite, you eventually win (for any p > 0), and net profit is always +1 because:
(last win) - (sum of previous losses) = 2^{m-1} - (2^{m-1} - 1) = 1.

With finite initial wealth F_0 = 2^k - 1 and constraint W_n ≤ F_{n-1}:
- The only way to fail is to lose k times in a row.
- In the fair case p = 1/2, that failure probability is 2^{-k}, so
P(F_τ = F_0 + 1) = 1 - 2^{-k}.

Two proof styles:
- Direct: “success iff not all first k are losses.”
- Via Theorem 7.2 (fair case): terminal wealth is either 0 or F_0 + 1, and E[F_τ] = F_0 forces
P(success) = F_0 / (F_0 + 1) = 1 - 2^{-k}.

### 7) Progress and pinch (Problem 7.7): termination depends on drift direction
Rule:
- after a loss, increase next wager by 1,
- after a win, decrease next wager by 1,
- stop when the next wager would be 0.

This makes the wager process W_n behave like a random walk on positive integers:
- step -1 with prob p,
- step +1 with prob q.

Termination is “hitting 0”.
- If p ≥ 1/2, there is no upward drift, and hitting 0 happens with probability 1.
- If p < 1/2, there is upward drift, and there is a positive chance of escaping to infinity, so termination is not certain.

Wealth identity:
Using W_{n+1} = W_n - X_n and squaring:
W_{n+1}^2 = W_n^2 - 2 W_n X_n + 1,
so W_n X_n = (1/2)(W_n^2 - W_{n+1}^2 + 1).

Since F_n - F_{n-1} = W_n X_n, summing from 1 to τ - 1 telescopes and yields:
F_τ = F_0 + (1/2) W_1^2 + (1/2)(τ - 1),
with the stopping condition giving W_τ = 0.

Why infinite capital is required:
Even if termination is almost sure (p ≥ 1/2), the wager can spike to arbitrarily large values before it eventually comes back down. To guarantee the strategy can be followed on all paths, you need unbounded resources.

## Proof sketch patterns I want to remember
- Drift + SLLN:
  If S_n/n -> μ, then S_n behaves like μ n, so it forces hitting behavior for one-sided boundaries.
- “Make products additive”:
  For multiplicative wealth, log converts products to sums and reveals long-run growth rate.
- Optional stopping (Theorem 7.2):
  If the game is fair and stopping is bounded, E[F_τ] = F_0 is often enough to solve for a probability.
- “Telescoping by algebra”:
  If you can rewrite a gain term as a difference of squares, summing becomes painless.

## Questions & confusions
- In the “timid play” argument, the step that upgrades pathwise statements about sup_k S_k to a probability bound P(sup_k(x + ε S_k) < 1) > 1 - η feels like a dominated convergence move; I want to restate it cleanly as: since M = sup_k S_k < ∞ a.s., x + ε M < 1 eventually for each path, so the indicator converges to 1 a.s.
- For “effective selection systems” (Problem 7.3), the key is countability of algorithms; I should revisit the exact wording of “effective” and how measurability is handled in the formal setup.

## Reflections
This section is a good reminder that “strategy” is mostly about changing the distribution of outcomes, not creating expected value out of nowhere. When drift is negative, small-bet caution can backfire by requiring many steps; when wealth is multiplicative, the right object is log-growth, not raw expected gain.
