---
type: exercise
date: 2026-08-16
tags: [math, mathematics, real, analysis, sequence, series, function]
book title: Understanding Analysis
book author: Stephen Abbott
book exercise: 6.2.7
---

# Exercise

Assume the $(f_n)$ converges uniformly to $f$ on $A$ and that each $f_n$ is uniformly continuous on $A$. Prove that $f$ is uniformly continuous on $A$.

**Proof:**

Let $\epsilon > 0$ be given. Then uniform convergence of $(f_n)$ implies there exists $N \in \mathbb{N}$ such that for all $x,y \in A$

$$
\begin{align*}
\vert f(x) - f_n(x) \vert &< \frac{\epsilon}{3} \\
\vert f(y) - f_n(y) \vert &< \frac{\epsilon}{3} 
\end{align*}
$$

Uniform continuity implies that there is $\delta > 0$ such that $\vert x - y \vert < \delta$ implies

$$\vert f_n(x) - f_n(y) \vert < \frac{\epsilon}{3}$$

Together this implies, given $\epsilon > 0$ there is $N \in \mathbb{N}
$ and $\delta > 0$ such that $n \geq N$ and $\vert x- y \vert < \delta$ imply

$$\vert f(x) - f(y) \vert \leq \vert f(x) - f_n(x) \vert + \vert f_n(x) - f_n(y) \vert + \vert f_n(y) - f(y) \vert < \frac{\epsilon}{3} + \frac{\epsilon}{3} + \frac{\epsilon}{3} = \epsilon$$

so that f is uniformly continuous.

$\square$

## Comments