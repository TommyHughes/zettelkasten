---
type: lemma
date: 2028-09-01
tags: [mathematics, math, stochastic, process, probability, ito, integral, lemma]
---

# An Intuitive Explanation of Ito's Lemma

We'll start with a [Wiener process](./brownian_motion_wiener_process.md), $W_t$ and a smooth (analytic?) function $f: \mathbb{R} \rightarrow \mathbb{R}$.

Here is the stupid version of it:

$$
f(W_t) - f(W_s) = \int_s^t f'(W_u) dW_u + \frac{1}{2} \int_s^t f''(W_u) du
$$

Note that, structurally, this looks like the fundamental theorem of calculus, only with an extra integral term on the right.

The basic idea is that we set up a telescoping sum

$$
f(W_t) - f(W_s) = \sum_{i=0}^{n-1} f(W_{i+1}) - f(W_i)
$$

where $W_i = W_{s+i\left( \frac{t-s}{n} \right)}$. The idea is that we are going to take the limit of this sum with respect to $n$ and this should then be something like our Riemann integral. To get there, first we have to make it *look right* (height $\times$ width). To that end recall that, since $f$ is smooth we can write

$$
f(W_t) - f(W_s) = \sum_{i=0}^{n-1} \sum_{k=1}^\infty \frac{f^{(k)}(W_i)}{k!} \Delta W_i^k
$$

where $\Delta W_i = W_{i+1} - W_i$. Taking the limit should yield

$$
\begin{align*}
    f(W_t) - f(W_s) &= \lim_{n \rightarrow \infty} \sum_{i=0}^{n-1} f(W_{i+1}) - f(W_i) \\
    &= \lim_{n \rightarrow \infty} \sum_{i=0}^{n-1} \sum_{k=1}^\infty \frac{f^{(k)}(W_i)}{k!} \Delta W_i^k
\end{align*}
$$

Now, for $k>2$ we'll get $\sum\Delta W_i^k \rightarrow 0$ as $n \rightarrow \infty$ (TODO). However, by [Quadratic Variation](./quadratic_variation.md), we get $\sum \Delta W_i^2 \rightarrow (t-s)$ as $n \rightarrow \infty$. This means we can ignore the terms in the Taylor expansion **after** $k=2$ (see comment below). Thus we get

$$
\lim_{n \rightarrow \infty} \sum_{i=0}^{n-1} \sum_{k=1}^\infty \frac{f^{(k)}(W_i)}{k!} \Delta W_i^k = \lim_{n \rightarrow \infty} \sum_{i=0}^{n-1} f'(W_i) \Delta W_i + \frac{1}{2} \sum_{i=0}^{n-1} f''(W_i) \Delta W_i^2
$$

Should the limit on the right exist, then we have

$$
f(W_t) - f(W_s) = \int_s^t f'(W_u) dW_u + \frac{1}{2} \int_s^t f''(W_u)\left(dW_u\right)^2
$$

Again, by Quadratic variation, we have the notational shorthand

$$
dW_t^2 = dt
$$

so that we get **Ito's Lemma:**

$$
f(W_t) - f(W_s) = \int_s^t f'(W_u) dW_u + \frac{1}{2} \int_s^t f''(W_u)du
$$

## Comments

- Using Quadratic Variation to explain why we need to keep the $f''$ term has left me wondering why we don't exclude the $f'$ term. TODO.
    - TODO: actually we haven't really shown that the weighted sums will vanish so we need to do that too.