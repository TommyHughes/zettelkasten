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
