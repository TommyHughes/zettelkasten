---
type: exercise
date: 2026-06-30
tags: [calculus, analysis, physics, conservation of energy]
book title: Advanced Calculus of Several Variables
book author: C. H. Edwards Jr.
book solution: 2.1.3
---

# Solution to Exercise 2.1.3

## Exercise

Let $F:\mathbb{R}^n \rightarrow \mathbb{R}^n$ be a *conservative* force field on $\mathbb{R}^n$, meaning that there exists a continuously differentiable *potential function* $V: \mathbb{R}^n \rightarrow \mathbb{R}$ such that $F(x) = - \nabla V(\mathbf{x})$ for all $\mathbf{x} \in \mathbb{R}^n$ [recall that $\nabla V = (\partial V/\partial x_1, \ldots, \partial V/\partial x_n)$]. Call the curve $\phi:\mathbb{R} \rightarrow \mathbb{R}^n$ a "quasi-Newtonian particle" if and only if there exist constants $m_1, m_2, \ldots, m_n$ called its "mass components" such that

$$F_i(\phi(t)) = m_i \phi_i''(t) \hspace{1em} (F=ma)$$

for each $i=1,\ldots,n$. Thus, with respect to the $x_i$-direction, it behaves as though it has mass $m_i$. Define its *kinetic energy* $K(t)$ and *potential energy* $P(t)$ at time $t$ by

$$K(t) = \frac{1}{2} \sum_{i=1}^n m_i[\phi_i'(t)]^2, \hspace{2em} P(t)=V(\phi(t))$$

Now prove that the law of the *conservation of energy* holds for quasi-Newtonian particles, that is, $K+P=$ constant.

## Solution

Observe that

$$
\begin{align*}
    \frac{dK}{dt} &= \frac{1}{2} \sum_{i=1}^n m_i \frac{d}{dt}[\phi_i'(t)^2] \\
    &= \sum m_i \phi_i'(t)\phi_i''(t) \\
    &= \sum F_i(\phi(t)) \phi_i'(t)
\end{align*}
$$

and

$$
\begin{align*}
    \frac{dP}{dt} &= \langle \nabla V(\phi(t)), \phi'(t) \rangle \\
    &= \langle -F(\phi(t)), \phi'(t) \rangle \\
    &= \sum_{i=1}^n -F_i(\phi(t))\phi_i'(t)
\end{align*}
$$

so that

$$ \frac{dK}{dt} + \frac{dP}{dt} = \frac{d (K+P)}{dt} = 0 $$

implying $(K+P)(t)$ is a constant. $\blacksquare$