# Study Notes: Princess Selection Problem and Optimal Stopping Threshold

Date: 2026-06-05  
Textbook: Probability and Measure, Patrick Billingsley  
Section: Chapter 1, Section 8, Markov Chains – Optimal Stopping, p138-139

---

> **Note**:  
> Today's focus is on the princess selection problem, the stopping set M, the role of the excessive function, and why the optimal threshold satisfies i_r ≈ r/e.

## Content Logic

The princess selection problem is a version of the classical secretary problem.

There are r suitors appearing in a random order. The princess observes them one by one. Once she rejects a suitor, she cannot return to him. At each stage, she only knows whether the current suitor is better than all previous suitors. Her goal is not to choose a good suitor, but to maximize the probability of choosing the single best suitor among all r suitors.

The final optimal strategy is:

Reject the first i_r - 1 suitors. Starting from position i_r, accept the first suitor who is better than all previous suitors.

When r is large, the threshold satisfies:

i_r ≈ r/e.

Since 1/e ≈ 0.3679, this means that the princess should reject about the first 36.8% of the suitors and then accept the next record-breaking suitor.

Strictly speaking, the number rejected is i_r - 1, not i_r. However, when r is large, the difference of one person is negligible, so people often describe the rule as "reject the first r/e candidates."

## Key Ideas

The problem is studied as an optimal stopping problem.

At a state i, the current suitor is a record-breaking suitor, meaning that he is better than all previous suitors. The princess has two options:

- Stop now and accept the current suitor.
- Continue waiting for a later record-breaking suitor.

The payoff function is:

f(i) = i/r.

This means that if the current record-breaking suitor appears at position i, then the probability that he is also the best among all r suitors is i/r.

The value function is:

v(i).

It means the best possible probability of success starting from state i, assuming the princess uses the optimal strategy from that point onward.

The continuation value is:

g(i) = Σ_{j=i+1}^r i/[j(j-1)] v(j).

This is the expected value of continuing to wait. The term i/[j(j-1)] is the probability that the next record-breaking suitor appears at position j.

Therefore, the basic dynamic programming relation is:

v(i) = max{f(i), g(i)}.

In simple words:

The best value at state i is the better one between stopping now and continuing.

## Excessive Function

The excessive function condition is:

v(i) ≥ Σ_j p_ij v(j).

This means that the current value v(i) is at least as large as the average value after taking one more Markov chain step.

In this problem, i is not itself an "optimal point." It is just an arbitrary current state.

A state i becomes a stopping state only when:

v(i) = f(i).

That means stopping now gives the same value as the optimal value. In that case, accepting the current record-breaking suitor is optimal, or at least tied with continuing.

The stopping set is:

M = {i : v(i) = f(i)}.

In plain language:

M is the set of states where the princess should stop.

## Deriving the Stopping Set M

The main goal is to show that the stopping set has the form:

M = {i_r, i_r + 1, ..., r, r + 1}.

This means that once the princess reaches a certain threshold i_r, every later record-breaking suitor should be accepted.

Suppose i is in M. Then:

v(i) = f(i).

Since v(i) is the optimal value and g(i) is only the value of continuing, we have:

f(i) = v(i) ≥ g(i).

Also,

g(i) ≥ Σ_{j=i+1}^r i/[j(j-1)] f(j).

This is because v(j) ≥ f(j) for every j. Replacing v(j) by f(j) can only reduce the sum.

Now use:

f(j) = j/r.

Then:

Σ_{j=i+1}^r i/[j(j-1)] f(j)
= Σ_{j=i+1}^r i/[j(j-1)] · j/r
= Σ_{j=i+1}^r i/[r(j-1)]
= (i/r) Σ_{j=i+1}^r 1/(j-1).

Since f(i) = i/r, this becomes:

Σ_{j=i+1}^r i/[j(j-1)] f(j)
= f(i) Σ_{j=i+1}^r 1/(j-1).

Therefore:

f(i) ≥ f(i) Σ_{j=i+1}^r 1/(j-1).

Since f(i) > 0, divide both sides by f(i):

Σ_{j=i+1}^r 1/(j-1) ≤ 1.

So if i is a stopping state, then the tail harmonic sum must be at most 1.

Conversely, suppose:

Σ_{j=i+1}^r 1/(j-1) ≤ 1,

and suppose all later states i+1, ..., r are already in M. Then for those later states:

v(j) = f(j).

So:

g(i) = Σ_{j=i+1}^r i/[j(j-1)] f(j)
= f(i) Σ_{j=i+1}^r 1/(j-1)
≤ f(i).

Therefore continuing is no better than stopping. Hence:

v(i) = max{f(i), g(i)} = f(i).

So:

i is in M.

This argument works backward from r, because r is certainly in M. At position r, if the current suitor is a record-breaking suitor, he must be the best overall, because there is nobody left.

Thus the stopping set is a final block:

M = {i_r, i_r + 1, ..., r, r + 1}.

## The Definition of i_r

The threshold i_r is determined by:

1/i_r + 1/(i_r + 1) + ... + 1/(r - 1) ≤ 1
< 1/(i_r - 1) + 1/i_r + ... + 1/(r - 1).

This says:

Starting at i_r, the remaining harmonic sum is already small enough, so stopping can be optimal.

But starting one step earlier, at i_r - 1, the remaining harmonic sum is still larger than 1, so it is still too early to stop.

In plain words:

i_r is the first position where it becomes reasonable to start accepting record-breaking suitors.

## Why i_r ≈ r/e

The key condition is approximately:

1/i_r + 1/(i_r + 1) + ... + 1/(r - 1) ≈ 1.

This is a harmonic sum. When r is large, it can be approximated by an integral:

1/i_r + 1/(i_r + 1) + ... + 1/(r - 1)
≈ ∫ from i_r to r of 1/x dx.

The integral is:

∫ from i_r to r of 1/x dx = log r - log i_r.

So the threshold condition becomes:

log r - log i_r ≈ 1.

This is the same as:

log(r/i_r) ≈ 1.

Since log e = 1, we get:

r/i_r ≈ e.

Therefore:

i_r ≈ r/e.

This is the source of the famous 36.8% rule.

Because:

1/e ≈ 0.3679,

the threshold is approximately 36.8% of the way through the sequence.

## Value Function Before the Threshold

For i < i_r, the state i is not in M. Therefore the princess should not stop at i.

So:

v(i) > f(i),

and by the dynamic programming equation:

v(i) = g(i).

The continuation value can be split into two parts:

v(i) = g(i)
= Σ_{j=i+1}^{i_r-1} i/[j(j-1)] v(j)
+ Σ_{j=i_r}^r i/[j(j-1)] f(j).

The first sum corresponds to the case where the next record-breaking suitor appears before i_r. In that case, the princess still should not stop, so the value remains v(j).

The second sum corresponds to the case where the next record-breaking suitor appears at or after i_r. In that case, the princess should stop, so the value is f(j).

Using f(j) = j/r, the second part becomes:

Σ_{j=i_r}^r i/[j(j-1)] f(j)
= Σ_{j=i_r}^r i/[j(j-1)] · j/r
= (i/r)(1/(i_r - 1) + ... + 1/(r - 1)).

So:

v(i)
= Σ_{j=i+1}^{i_r-1} i/[j(j-1)] v(j)
+ (i/r)(1/(i_r - 1) + ... + 1/(r - 1)).

Now start with:

i = i_r - 1.

At this point, the first sum is empty, because it would run from j = i_r to j = i_r - 1. An empty sum is 0.

Therefore:

v(i_r - 1)
= ((i_r - 1)/r)(1/(i_r - 1) + ... + 1/(r - 1)).

This value is denoted by:

p_r.

So:

p_r = ((i_r - 1)/r)(1/(i_r - 1) + ... + 1/(r - 1)).

By backward induction, the same value holds for every i before the threshold:

v(i) = p_r, for 1 ≤ i < i_r.

This means that before the threshold, all early states have the same optimal value. The reason is intuitive: before i_r, the princess is still in the observation period and will not accept anyone anyway.

## Final Strategy

The original problem starts at:

X_1 = 1.

The first suitor is automatically the best among the people seen so far, so the initial state is 1.

The optimal strategy is:

Stop the first time X_n enters M.

In ordinary language:

Reject the first i_r - 1 suitors. Then accept the first later suitor who is better than all previous suitors.

The optimal success probability is:

p_r = ((i_r - 1)/r)(1/(i_r - 1) + ... + 1/(r - 1)).

For large r:

i_r ≈ r/e,

and:

p_r ≈ 1/e.

So the success probability is also about 36.8%.

## Questions & Confusions

A useful confusion today was the difference between i_r and i_r - 1.

The threshold i_r is the first position where the princess starts considering acceptance. But the number of automatically rejected suitors is i_r - 1.

So the rejected proportion is:

(i_r - 1)/r.

Since i_r ≈ r/e,

(i_r - 1)/r ≈ 1/e - 1/r.

This is not the same as "36.8% minus 1 percentage point" in general. It is 36.8% minus one person as a fraction of the total number of suitors.

For large r, 1/r is very small, so the simpler phrase "reject about 36.8%" is acceptable as an approximation.

Another useful clarification was about the excessive function condition:

v(i) ≥ Σ_j p_ij v(j).

Here i is not necessarily an optimal stopping point. It is just an arbitrary state. A state becomes a stopping state only when:

v(i) = f(i).

## Reflections

This example is a good illustration of how optimal stopping works.

The solution does not come from guessing the 36.8% rule directly. It comes from comparing two values at every state:

- the value of stopping now,
- the value of continuing.

The stopping set M then emerges as a threshold region. Once the current record-breaking suitor appears late enough, the value of waiting becomes too small, and stopping becomes optimal.

The most important technical step is the harmonic sum condition:

1/i_r + 1/(i_r + 1) + ... + 1/(r - 1) ≈ 1.

The famous r/e threshold is just the large-r approximation of this condition using:

Σ 1/j ≈ ∫ 1/x dx.

This makes the result feel much less mysterious. The number e appears because the integral of 1/x is log x, and log(r/i_r) ≈ 1 implies r/i_r ≈ e.
