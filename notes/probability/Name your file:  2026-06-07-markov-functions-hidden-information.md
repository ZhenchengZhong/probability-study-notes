# Study Notes: Markov Chains, Hidden Information, and Functions of Markov Chains

Date: 2026-06-07  
Textbook: Billingsley, Probability and Measure  
Section: Chapter 1, Section 8, Problems 8.2–8.3

---

> **Note**:  
> Today's focus is on understanding why a process can fail to be Markov even when some non-adjacent variables are independent, and why a function of a Markov chain need not remain Markov.

## Content Logic

Problem 8.2 considers a sequence Y_0, Y_1, ... of independent and identically distributed random variables, where

P(Y_n = 1) = p,

P(Y_n = 0) = q = 1 - p,

with p ≠ q.

The new process is defined by

X_n = Y_n + Y_{n+1} mod 2.

This means that X_n records whether two consecutive Y-values are the same or different:

X_n = 0 if Y_n = Y_{n+1},

X_n = 1 if Y_n ≠ Y_{n+1}.

The problem asks us to show that X_0, X_1, ... is not a Markov chain, even though

P(X_{n+1} = j | X_{n-1} = i) = P(X_{n+1} = j).

The key point is that independence between X_{n-1} and X_{n+1} is not the same as the Markov property.

## Key Ideas

The Markov property says that, once the present state is known, the earlier past should no longer give extra information about the future.

For this process, knowing X_n only tells us whether Y_n and Y_{n+1} are equal or different. It does not tell us the actual hidden values of Y_n and Y_{n+1}.

For example, if X_1 = 0, then we know

Y_1 = Y_2.

But we do not know whether

Y_1 = Y_2 = 0

or

Y_1 = Y_2 = 1.

When p ≠ q, these two possibilities are not equally likely. Therefore, earlier information such as X_0 can still change our belief about the hidden value Y_2, and Y_2 affects X_2.

This is why the process X_0, X_1, ... is not Markov.

## Proof Sketch for Problem 8.2

To disprove the Markov property, it is enough to find one case where the past still matters after the present is known.

Compare

P(X_2 = 1 | X_1 = 0)

with

P(X_2 = 1 | X_1 = 0, X_0 = 0).

If the process were Markov, these two conditional probabilities should be equal.

First, X_1 = 0 means

Y_1 = Y_2.

So either

Y_1 = Y_2 = 1,

with probability p^2,

or

Y_1 = Y_2 = 0,

with probability q^2.

Therefore,

P(X_1 = 0) = p^2 + q^2.

Also, X_2 = 1 means

Y_2 ≠ Y_3.

So

P(X_2 = 1, X_1 = 0) = p^2 q + q^2 p = pq.

Hence

P(X_2 = 1 | X_1 = 0) = pq / (p^2 + q^2).

Now add the extra condition X_0 = 0. Since

X_0 = 0 means Y_0 = Y_1,

and

X_1 = 0 means Y_1 = Y_2,

together they imply

Y_0 = Y_1 = Y_2.

Thus

P(X_0 = 0, X_1 = 0) = p^3 + q^3.

Also,

P(X_2 = 1, X_1 = 0, X_0 = 0) = p^3 q + q^3 p.

Therefore,

P(X_2 = 1 | X_1 = 0, X_0 = 0)
= (p^3 q + q^3 p) / (p^3 + q^3)
= pq(p^2 + q^2) / (p^3 + q^3).

So we have

P(X_2 = 1 | X_1 = 0) = pq / (p^2 + q^2),

but

P(X_2 = 1 | X_1 = 0, X_0 = 0)
= pq(p^2 + q^2) / (p^3 + q^3).

These two quantities are not equal when 0 < p < 1 and p ≠ q, because equality would require

(p^2 + q^2)^2 = p^3 + q^3,

but in fact

p^3 + q^3 - (p^2 + q^2)^2 = pq(p - q)^2 > 0.

Therefore,

P(X_2 = 1 | X_1 = 0, X_0 = 0)
≠
P(X_2 = 1 | X_1 = 0).

This proves that X_0, X_1, ... is not a Markov chain.

## Why the Given Independence Relation Still Holds

The relation

P(X_{n+1} = j | X_{n-1} = i) = P(X_{n+1} = j)

holds here because X_{n-1} and X_{n+1} depend on disjoint groups of Y-variables.

Specifically,

X_{n-1} depends on Y_{n-1} and Y_n,

while

X_{n+1} depends on Y_{n+1} and Y_{n+2}.

These two pairs do not overlap. Since the Y-variables are independent, X_{n-1} and X_{n+1} are independent.

However, this is only a statement about variables two steps apart. It does not imply the Markov property.

## Does This Relation Hold for All Markov Chains?

No.

A Markov chain does not require X_{n-1} and X_{n+1} to be independent. It only requires that the future depends on the past through the present state.

For example, consider the two-state chain where

X_{n+1} = X_n

for every n, and

P(X_0 = 0) = 1/2,

P(X_0 = 1) = 1/2.

This is a Markov chain, because the next state is completely determined by the current state.

But

P(X_{n+1} = 1 | X_{n-1} = 1) = 1,

while

P(X_{n+1} = 1) = 1/2.

So

P(X_{n+1} = 1 | X_{n-1} = 1) ≠ P(X_{n+1} = 1).

Therefore, the relation in Problem 8.2 does not hold for all Markov chains.

## Problem 8.3: A Function of a Markov Chain Need Not Be Markov

Problem 8.3 asks us to give an example showing that a function of a Markov chain does not have to be a Markov chain.

Problem 8.2 provides a natural example.

Define

Z_n = (Y_n, Y_{n+1}).

Then Z_0, Z_1, ... is a Markov chain.

To see why, note that

Z_{n+1} = (Y_{n+1}, Y_{n+2}).

If we know

Z_n = (a, b),

then the next state must have the form

Z_{n+1} = (b, c),

where c is a new independent Bernoulli variable with

P(c = 1) = p,

P(c = 0) = q.

So the distribution of Z_{n+1} depends only on Z_n, not on the earlier history. Hence Z_n is Markov.

Now define a function f on pairs by

f(a, b) = a + b mod 2.

Then

f(Z_n) = f(Y_n, Y_{n+1})
= Y_n + Y_{n+1} mod 2
= X_n.

But Problem 8.2 already showed that X_0, X_1, ... is not a Markov chain.

Therefore,

Z_0, Z_1, ... is a Markov chain,

but

f(Z_0), f(Z_1), ...

is not a Markov chain.

This proves that a function of a Markov chain need not be Markov.

## Symbols and Terms

Y_n: the original independent Bernoulli random variables.

p: the probability that Y_n = 1.

q: the probability that Y_n = 0, with q = 1 - p.

X_n: the derived process defined by X_n = Y_n + Y_{n+1} mod 2.

Z_n: the pair-valued process Z_n = (Y_n, Y_{n+1}).

f: a function applied to the state of a Markov chain.

mod 2: arithmetic where even sums become 0 and odd sums become 1.

Markov chain: a stochastic process where the conditional distribution of the next state depends only on the current state, not on the full past.

Hidden information: information about the original state that is lost after applying a function.

Function of a Markov chain: a new process formed by applying the same function to each state of a Markov chain.

## Reflection

The most important lesson is that the Markov property depends on whether the current observed state contains enough information to predict the next observed state.

The process Z_n = (Y_n, Y_{n+1}) is Markov because it keeps enough information. But the function f(Z_n) only records whether the two coordinates are equal or different. This compression loses information.

Once information is lost, the earlier past may become useful again. That is why f(Z_n) can fail to be Markov even when Z_n itself is Markov.

This example is an early warning that coarse observations of a Markov chain do not automatically preserve the Markov property.
