---
type: theorem
date: 2026-09-15
tags: [math, mathematics, stochastic, process, probability, brownian motion, wiener process, quadratic, variation]
---

# Quadratic Variation

**Theorem** Let $W_t$ be a [Wiener Process](./brownian_motion_wiener_process.md) and $s,t \in \mathbb{R}$ with $s < t$. Then

$$
\sum_{i=0}^{n-1} \left( W_{s+(i+1)\frac{t-s}{n}} - W_{s+i\frac{t-s}{n}} \right)^2 \overset{\mathbb{P}}{\underset{n \rightarrow \infty}{\rightarrow}} t-s \in \mathbb{R}
$$

**Proof**

We need to show that

$$
\lim_{n \rightarrow \infty} \mathbb{P} \left( \left\vert \sum_{i=0}^{n-1} \left( \underbrace{W_{s+(i+1)\frac{t-s}{n}} - W_{s+i\frac{t-s}{n}}}_{\Delta W_i} \right)^2 - (t-s) \right\vert < \epsilon  \right) = 1
$$

To begin we'll observe that it is equivalent to show that

$$
\lim_{n \rightarrow \infty} \mathbb{P} \left( \left\vert \sum_{i=0}^{n-1} \Delta W_i^2 - (t-s) \right\vert \geq \epsilon \right) = 0
$$

Since $W_t$ is a Weiner process, it follows that

$$\Delta W_i^2 = \left(\frac{t-s}{n}\right) Z^2 = \left(\frac{t-s}{n}\right) \chi_{1}^2$$

where $Z \sim \mathcal{N}(0,1)$. So

$$
\mathbb{E}[\Delta W_i^2] = \mathbb{E}\left[\left( \frac{t-s}{n} \right) \chi_1^2 \right] = \frac{t-s}{n}
$$

and

$$
\operatorname{Var}(\Delta W_i^2) = \operatorname{Var}\left( \left( \frac{t-s}{n} \right) \chi_1^2 \right) = 2 \left( \frac{t-s}{n} \right) ^2
$$

Let $\epsilon > 0$ and $\delta > 0$ be given. Then for $n > 2 \frac{(t-s)^2}{\epsilon \delta^2}$, by Cheybshev's Inequality, we get

$$\mathbb{P} \left( \left\vert \sum_0^{n-1} \Delta W_i^2 - (t-s) \right\vert \geq \delta \right) \leq 2 \frac{(t-s)^2}{n \delta^2} < \epsilon$$

which implies the conclusion. 

$\blacksquare$

## Comments

- If we set $s=0$ then $t-s = t$ is just the total time the wiener process has had to evolve. Then this theorem is saying if you sum up the squared differences of infinitesimal segments within that duration, you get back that total duration; you get back the time variable. Letting $s \neq 0$ is just an affine transformation; it moves the origin somewhere else.