---
type: exercise
date: 2026-06-30
tags: [calculus, analysis, minimization, ]
book title: Advanced Calculus of Several Variables
book author: C. H. Edwards Jr.
book solution: 2.1.2
---

# Solution to Exercise 2.1.2

## Exercise

1. Let $f: \mathbb{R} \rightarrow \mathbb{R}^n$ and $g: \mathbb{R} \rightarrow \mathbb{R}^n$ be two differentiable curves, with $f'(t) \neq \mathbf{0}$ and $g'(t) \neq \mathbf{0}$ for all $t \in \mathbb{R}$. Suppose the two points $\mathbf{p} = f(s_0)$ and $\mathbf{q} = g(t_0)$ are close than any other pair of points on the two curves. Then prove that the vector $\mathbf{p-q}$ is orthogonal to both velocity vectors $f'(s_0)$ and $g'(t_0)$.

1. Apply the result above to find the closest pair of points on the "skew" straight lines in $\mathbb{R}^3$ defined by $f(s) = (s, 2s, -s)$ and $g(t)=(t+1, t-2, 2t+3)$

## Solution

1. Let $\mathbf{p}$ be fixed. Then by a [previous exercise](acsv_e_ex_2_1_1.md), $\langle \mathbf{p-q}, g'(t_0) \rangle = 0$. Similar for $\langle \mathbf{q-p}, f'(s_0) \rangle$.

1. We want to find the solution to the following system of equations: $$\begin{cases} \langle f(s_0) - g(t_0), g'(t_0) \rangle &= 0 \\ \langle g(t_0) - f(s_0), f'(s_0) \rangle &= 0 \end{cases}$$ Observe that $$\begin{cases} g'(t) &= (1, 1, 2) \\ f'(s) &= (1, 2, -1) \end{cases}$$ Substituting into the above formulas and solving the system yields $$\begin{cases} t_0 &= -\frac{36}{35} \\ s_0 &= -\frac{41}{35} \end{cases}$$ so that plugging into respective equations produces the desired points.