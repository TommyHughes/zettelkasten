---
type: solution
date: 2026-06-29
tags: [calculus]
book title: Advanced Calculus of Several Variables
book author: C. H. Edwards Jr.
book solution: 1.1
---

# Solution to Exercise 1.1

## Exercise

Let $f: \mathbb{R} \rightarrow \mathbb{R}^n$ be a differentiable mapping with $f'(t) \neq \mathbf{0}$ for all $t \in \mathbb{R}$. Let $\mathbf{p}$ be a fixed point not on the image curve of $f$ as in Fig. If $\mathbf{q}=f(t_0)$ is the point of the curve closest to $\mathbf{p}$, that is, if $\vert \mathbf{p} - \mathbf{q}\vert \leq \vert \mathbf{p}-f(t) \vert$ for all $t \in \mathbb{R}$, show that the vector $\mathbf{p} - \mathbf{q}$ is orthogonal to the curve at $\mathbf{q}$.

<insert figure here>

## Solution

Let $ \phi(t) = \vert \mathbf{p} - f(t) \vert^2$, then
$$
\begin{align*}

\phi'(t_0) &= \lim_{t \rightarrow t_0} \frac{\phi(t) - \phi(t_0)}{t-t_0} \\
&= -2\langle \mathbf{p}, f'(t_0) \rangle + 2 \langle \mathbf{q}, f'(t_0) \rangle
\end{align*}
$$

and since $\phi: \mathbb{R} \rightarrow \mathbb{R}$ is minimized at $t_0$ it follows that $\phi'(t_0) = 0$ so that

$$
\begin{align*}
-2 \langle \mathbf{p}, f'(t_0) \rangle + 2\langle \mathbf{q}, f'(t_0) \rangle &= 0 \\
\langle \mathbf{p} - \mathbf{q}, f'(t_0) \rangle &= 0 
\end{align*}
$$

which implies the result.

## Comments

The intuition might go something like:

- Orthogonality here would mean $\langle \mathbf{p} - \mathbf{q}, f'(t_0) \rangle =0$ so we want an inner product equaling 0.

- Something is being minimized. That something is the length of the point to the curve. We know the derivative at a minimum is 0. Doubly interesting is that the minimum corresponds to the point on the curve $\mathbf{q}$ that corresponds to where we are supposed to get our orthogonality.

- Write an expression for the distance from $\mathbf{p}$ to the image of $f$ as $\vert \mathbf{p} - f(t) \vert$. Recognize that minimizing the distance is equivalent to minimizing $\phi(t) = \vert \mathbf{p} - f(t) \vert^2$.

- Recognize that $\phi: \mathbb{R} \rightarrow \mathbb{R}$ and therefore, being minimized at $t_0$, implies that

$$0 = \phi'(t_0) = \lim_{t \rightarrow t_0} \frac{\phi(t) - \phi(t_0)}{t-t_0}$$

- Calculate and the expression falls out.