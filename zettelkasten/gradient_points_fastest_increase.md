---
type: theorem
date: 2026-07-06
tags: [mathematics, theorem, proof, analysis, multivariable, calculus, gradient, increase]
---

# Theorem: The Gradient Points in the Direction of Fastest Increase


*Theorem*: Let $f: \mathbb{R}^n \rightarrow \mathbb{R}$ be differentiable at $\mathbf{a}$ and $\nabla f(\mathbf{a}) \neq \mathbf{0}$. Then

$$\max_{\vert \mathbf{v} \vert=1} \left\langle \nabla f(\mathbf{a}), \mathbf{v} \right\rangle = \left\langle \nabla f(\mathbf{a}), \frac{\nabla f(\mathbf{a})}{\vert \nabla f(\mathbf{a}) \vert} \right\rangle$$

and the solution is unique.

*Proof*: By Cauchy-Schwarz, 

$$ \langle \nabla f(\mathbf{a}), \mathbf{v} \rangle \leq \vert \langle \nabla f(\mathbf{a}), \mathbf{v} \rangle \vert \leq \vert \nabla f(\mathbf{a}) \vert \vert \mathbf{v} \vert \leq \frac{\vert \nabla f(\mathbf{a}) \vert^2}{\vert \nabla f(\mathbf{a})\vert} = \vert \nabla f(\mathbf{a}) \vert$$

where the equality holds uniquely for $\frac{\nabla f(\mathbf{a})}{\vert \nabla f(\mathbf{a}) \vert}$.

## Comments
- I like to think of it like: The gradient points in the direction the tangent plane looks like it's pointing to; the direction in which the tangent plane is *most pointy*.

- This is just **Cauchy-Schwarz**. That is the reason: "because Cauchy-Schwarz".

- It's not obvious why this implies the description of the theorem. It follows from the fact that $$D_v f(a) = D f(a)(v) = \langle \nabla f(a), v \rangle$$ (see [this](./directional_derivative_formula.md) zettel) So maximizing $D_v f(a)$ is tantamount to finding the unit vector $v$ that maximizes $Df(a)(v)$ which is equivalent to the statement of the theorem.
    - We'd want to maximize $D_v f(a)$ since this is finding the direction $v$ that maximizes the rate of change of $f$ at $a$, which is what "points in the direction of fastest increase" is intended to mean.