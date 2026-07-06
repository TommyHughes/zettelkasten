---
type: theorem
date: 2026-07-06
tags: [mathematics, theorem, proof, analysis, multivariable calculus, gradient, level curve, orthogonal]
---

# Theorem: The Gradient is Orthogonal to a Level Set

*Theorem* Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be differentiable and let $\phi:\mathbb{R} \rightarrow \mathbb{R}^n$ be differentiable and admit

$$(f \circ \phi) (t) = k$$

for all $t \in \mathbb{R}$, where $k \in \mathbb{R}$. Then

$$\langle \nabla f(\phi(t)), \phi'(t) \rangle = 0$$

for all $ t \in \mathbb{R} $.

*Proof* Observe that, by the chain rule,

$$
\begin{align*}
    D (f \circ \phi) (t) &= Df(\phi(t)) \circ D\phi(t) \\
    &= \langle \nabla f(\phi(t)), \phi'(t)\rangle \\
    &= 0
\end{align*}
$$

for all $t \in \mathbb{R}$ where the last equality comes from differentiating the constant $k$.

## Comments

- This demonstrates that orthogonality of the gradient and the level set is **just the chain rule**.