## Problem

A dragon and a soldier are having a turned-based fight. The dragon starts with three heads. On each turn, one of three things can happen:

1. The soldier chops off two of the dragon's heads,
2. The soldier chops off one of the heads, and the head grows back,
3. The soldier misses, and the dragon grows an additional head.

The dragon wins if it has five heads. The soldier wins if the dragon reaches $0$ heads.

## Assumptions

- If the dragon has one head, the soldier will always miss.
- Given that the dragon has at least two heads, the probability of a miss always equals the likelihood of killing two heads.

## Question

What's the probability the soldier wins?

## Solution

Let $p(n)$ be the probability the soldier wins when the dragon has $n$ heads. We can write out the probability for each value of $n$ by referring to the probabilities of the actions that can happen on each turn. We get,

- $p(0) = 1$,
- $p(1) = p(2)$,
- $p(2) = \frac{1}{2} p(0) + \frac{1}{2} p(3)$,
- $p(3) = \frac{1}{2} p(1) + \frac{1}{2} p(4)$,
- $p(4) = \frac{1}{2} p(2) + \frac{1}{2} p(5)$,
- $p(5) = 0$.

By substitution, we have

- $p(4) =  \frac{1}{2} p(2)$,
- $p(3) = \frac{1}{2} p(2) + \frac{1}{4} p(2)$, which gives us $p(3) = \frac{3}{4} p(2)$,
- $p(2) = \frac{1}{2} + \frac{3}{8} p(2)$, which gives us $p(2) = \frac{4}{5}$.

Finally, we combine these results to get $p(3) = \frac{3}{5}$.

For completeness, we state the probability of the soldier winning from every game state:

- $p(0) = 1$,
- $p(1) = \frac{4}{5}$,
- $p(2) = \frac{4}{5}$,
- $p(3) = \frac{3}{5}$,
- $p(4) = \frac{2}{5}$,
- $p(5) = 0$.
