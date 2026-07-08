---
type: theorem
date: 2026-07-08
tags: [math, lagrange multiplier, optimization, multivariable, calculus, analysis, proof]
---

# Theorem: The Lagrange Multiplier

*Theorem*: Suppose $g:\mathbb{R}^n \rightarrow \mathbb{R}$ is continuously differentiable, and let $M$ be the set of all those points $\mathbf{x} \in \mathbb{R}^n$ at which both $g(\mathbf{x}) = 0 $ and $\nabla g(\mathbf{x}) \neq \mathbf{0}$. If the differentiable function $f:\mathbb{R}^n \rightarrow \mathbb{R}$ attains a local maximum or minimum on $M$ at the point $\mathbf{a} \in M$, then

$$\nabla f(\mathbf{a}) = \lambda \nabla g(\mathbf{a})$$

for some number $\lambda$ (called the "Lagrange Multiplier").

*Proof*: Let By the Implicit Function Theorem (TODO link), near $\mathbf{a}$, we have that 

$$x_n = F(x_1, \ldots, x_{n-1})$$

for some differentiable function $F$ defined on an n-hood of $\mathbf{a}$. So, let's define $h: \mathbb{R}^{n-1} \rightarrow \mathbb{R}^n$ by

$$h(x_1, \ldots, x_{n-1}) = (x_1, \ldots, x_{n-1}, F(x_1, \ldots, x_{n-1}))$$

Observe that

$$
\begin{align*}
h'(x_1,\ldots, x_{n-1}) &= 
    \begin{bmatrix}
        1 & 0 & \ldots & 0 \\
        0 & 1 & \ldots & 0 \\
        0 & 0 & \ldots & 1 \\
        \frac{\partial F}{\partial x_1}(x_1, \ldots, x_{n-1}) & \frac{\partial F}{\partial x_2}(x_1, \ldots, x_{n-1}) & \ldots & \frac{\partial F}{\partial x_{n-1}}(x_1, \ldots, x_{n-1})
    \end{bmatrix}_{n \times n-1} \\
    &= \begin{bmatrix}
            I_{n-1} \\
            \nabla F(x_1, \ldots, x_{n-1})^T
        \end{bmatrix}
\end{align*}
$$

Again, by the Implicit Function Theorem, we have that

$$(g \circ h)(x_1, \ldots, x_{n-1}) = 0$$

and so

$$
\begin{align*}
    g'(h(a_1, \dots, a_{n-1})) \cdot h'(a_1, \dots, a_{n-1}) &= \nabla g(h(a_1, \dots, a_{n-1}))^T \cdot h'(a_1, \ldots, a_{n-1}) \\
    &= \nabla g(\mathbf{a})^T \cdot  h'(a_1, \ldots, a_{n-1})\\
    &= 0 
\end{align*}
$$

Furthermore, since $f$ obtains it's extremum at $\mathbf{a}$ it follows

$$
\begin{align*}
    f'(h(a_1, \dots, a_{n-1})) \cdot h'(a_1, \dots, a_{n-1}) &= \nabla f(h(a_1, \dots, a_{n-1}))^T \cdot h'(a_1, \ldots, a_{n-1}) \\
    &= \nabla f(\mathbf{a})^T \cdot  h'(a_1, \ldots, a_{n-1})\\
    &= 0 
\end{align*}
$$

so that both $\nabla f(\mathbf{a})$ and $\nabla g(\mathbf{a})$ belong to the orthogonal complement of $\operatorname{Im}(h'(a_1, \ldots, a_{n-1}))$. Since $\operatorname{Im}(h'(a_1, \ldots, a_{n-1}))$ is an $n-1$-dimensional subspace of $\mathbb{R}^n$ (TODO link), it follows $\nabla f(\mathbf{a})$ and $\nabla g(\mathbf{a})$ belong to the same 1-dimensional subspace of $\mathbb{R}^n$ and since $\nabla g(\mathbf{a}) \neq 0 $, the result follows.