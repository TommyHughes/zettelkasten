---
type: theorem
date: 2026-08-15
tags: [math, mathematics, analysis, sequence, functions, cauchy, uniform, convergence]
---

# Cauchy Criterion for Uniform Convergence

A sequence of functions $(f_n)$ defined on a set $A \subseteq \mathbb{R}$ converges uniformly on $A$ if and only if for every $\epsilon > 0$ there exists an $N \in \mathbb{N}$ such that $\vert f_n(x) - f_m(x) \vert < \epsilon$ for all $m,n \geq N$ and all $x \in A$.

**Proof**

Suppose $f_n \rightarrow f$ uniformly on $A$. Then for all $n,m$ large enough we have

$$\vert f_n(x) - f_m(x) \vert \leq \vert f_n(x) - f(x) \vert + \vert f(x) - f_m(x) \vert < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon $$

for all $x \in A$.

Alternatively, given $\epsilon > 0$ suppose there exists $N \in \mathbb{N}$ such that

$$\vert f_n(x) - f_m(x) \vert < \epsilon$$

for all $m,n \geq N$ and all $x \in A$. This implies that for every $x \in A$

$$(f_n(x))$$

is a Cauchy Sequence of real numbers. This, in turn, implies $(f_n(x))$ is a convergent sequence of real numbers. Define

$$f(x) = \lim_{n \rightarrow \infty} f_n(x)$$

for $x \in A$. Moreover, we have that there is an $N \in \mathbb{N}$ such that for $n,m \geq N$ and $x \in A$ we have

$$\vert f_n(x) - f_m(x) \vert < \epsilon$$

which implies

$$\lim_{m \rightarrow \infty} \vert f_n(x) - f_m(x) \vert = \vert f_n(x) - \lim_{m \rightarrow \infty} f_m(x) \vert = \vert f_n(x) - f(x) \vert \leq \epsilon$$

Thus there is an $N \in \mathbb{N}$ such that $n \geq N$ and $x \in A$ imply

$$\vert f_n(x) - f(x) \vert \leq \epsilon$$

so that $(f_n)$ is uniformly continuous.

## Comments

- Note that we can move the limit into the absolute value by continuity of the absolute value function.