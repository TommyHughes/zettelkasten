---
type: lemma
date: 2026-08-01
tags: [math, mathematics, lemma, theorem, monotone, derivative, interval, point]
---

# Lemma: Non-zero Derivative Implies Relative Monotonicity

Let $f$ be differentiable at $a \in \mathbb{R}$ and $f'(a) > 0$ (alternatively $f'(a) < 0$). Then there exists an n-hood of $a$ on which 

$$\text{sgn}(x-a) = \text{sgn}(f(x) - f(a))$$

(alternatively $\text{sgn}(x-a) = -\text{sgn}(f(x) - f(a))$)

**Proof**

We have that, given $\epsilon > 0$, there is $\delta > 0$ such that $x \in B_{\delta}(a)$ implies

$$ \left\vert \frac{f(x) - f(a)}{x-a} - f'(a) \right\vert < \epsilon$$

so that for $\epsilon$ small enough

$$0 < f'(a)-\epsilon < \frac{f(x) - f(a)}{x-a}$$

(alternatively $\frac{f(x) - f(a)}{x-a} < f'(a) + \epsilon < 0$).

which implies the result. $\square$