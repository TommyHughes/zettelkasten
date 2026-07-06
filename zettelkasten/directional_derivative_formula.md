---
type: theorem
date: 2026-07-06
tags: [math, multivariable, calculus, analysis, directional derivative, derivative]
---

# Theorem: The Directional Derivative from the Derivative

*Theorem*: $$D_\mathbf{v} f(\mathbf{a}) = D f(\mathbf{a})(\mathbf{v})$$

*Proof*: Let $h:\mathbb{R} \rightarrow \mathbb{R}^n$ be defined by $h(t) = \mathbf{a} + t\mathbf{v}$. Then

$$
\begin{align*}
    D_\mathbf{v} f(\mathbf{a}) &= D (f \circ h)(0) \\
    &= D f(h(0)) \circ D h(0) \\
    &= D f(\mathbf{a})(\mathbf{v})
\end{align*}
$$

## Comments

- Note that we *may* be slightly abusing notation if we take $D_v f(a) \in \mathbb{R}$ and not a linear map $D(f \circ h)(0): \mathbb{R} \rightarrow \mathbb{R}$. Obviously there is an isomorphism between the two spaces but it's worth noting.