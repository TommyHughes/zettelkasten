---
type: note
date: 2026-09-01
tags: [math, mathematics, stochastic, process, probability, brownian motion, wiener process]
---

# Definition of Brownian Motion/Wiener Process

[`Brownian Motion`]([wiki1](https://en.wikipedia.org/wiki/Wiener_process)), also known as a [`Wiener process`](https://en.wikipedia.org/wiki/Wiener_process) is a continuous-time stochastic process characterized by

1. $W_0 = 0$ almost surely.

1. W has independent increments: $$W_{t'} - W_{s'} \perp W_t - W_s$$ where $s < t \leq s' < t'$.

1. $W_t - W_s \sim \mathcal{N}(0, t-s)$.

1. $W_t$ is almost surely continuous in $t$.

## Comments

- Interestingly, the assumption that increments are independent actually necessitates that the variance be linearly proportional to the size of the increment. The idea is that independence of increments implies that the variance is additive. That is, given $t < t+h - \delta < t+h$ $$\operatorname{Var}(W_{t+h} - W_t) = \operatorname{Var}(W_{t+h} - W_{t+h-\delta}) + \operatorname{Var}(W_{t+h-\delta} - W_t)$$. This means if we partition $[t, t+h]$ into n equally sized increments we get $$\sigma^2(h) = \operatorname{Var}[W_{t+h} - W_t] = \sum_{0}^{n-1} \operatorname{Var}[W_{t+(k+1) \frac{h}{n}} - W_{t+k \frac{h}{n}}] = nf\left(\frac{h}{n}\right)$$. Since $\sigma^2(h)$ is a non-zero constant (if it were zero there would be no variance and the process wouldn't be random) if we let $\frac{h}{n} = \Delta t$, then this implies $$\frac{\sigma^2(h)}{h} \Delta t = f(\Delta t)$$ where $\frac{\sigma^2}{h} > 0$ is a constant. This means that the sum of the variances of the sub-increments, $f(\Delta t)$, must equal the variance of the increment $\sigma^2(h)$. Furthermore, the variance of each sub-increment increases linearly with the size of the sub-increment, $\Delta t$. By extension, the variance of the increment increases linearly with the size of the increment $h$.