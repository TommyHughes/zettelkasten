---
type: theorem
date: 2026-08-01
tags: [math, mathematics, proof, theorem, darboux, intermediate value, derivative, analysis]
---

# Darboux's Theorem

Let $f$ be differentiable on $[a,b] \subset \mathbb{R}$. If there exists $\alpha$ such that $f'(a) < \alpha < f'(b)$ (or $f'(a) > \alpha > f'(b)$) then there exists $c \in (a,b)$ such that $f'(c) = \alpha$.

**Proof**

Let $g(x) = f(x) - \alpha x$. Then we have that

$$g'(a) = f'(a) - \alpha < 0 < f'(b) - \alpha = g'(b)$$

so that

$$g'(a) < 0 < g'(b)$$

(alternatively $g'(a) > 0 > g'(b)$). From [properties of differentiability](lemma__monotonicity_from_derivative.md), it follows that there exist $x,y \in (a,b)$ such that

$$ g(x) < g(a) \text{ and } g(y) < g(b) $$

(alternatively $g(a) < g(x) \text{ and } g(b) < g(y)$)

so that, by compactness of $[a,b]$ and continuity of $g$, $g$ has a minimum (alternatively maximum), $c \in (a,b)$. By the Interior Extremum Theorem, it follows that

$$0 = g'(c) = f'(c) - \alpha$$

implying the result. $\square$

## Comments
- $g(x)$ is doing several things at once, but perhaps most importantly the assumption of $f'(a) < \alpha < f'(b)$ is forcing that $g$ does not have extrema at the boundary points $a$ and $b$. This is the crucial element of the construction. It guarantees we can use the Interior Extremum. Otherwise we'd have to worry about extrema occuring at the boundaries.
    - If you add functions $f(x) + h(x)$ and you know that $h$ is decreasing faster than $f$ is increasing at a given point, then their sum is decreasing relative to the point; their sum has a negative derivative and so is decreasing relative to the point ($(f+h)(x) < (f+h)(a)$ when $x > a$) on some n-hood of the given point. Similar but relative increasing if $h$ is increasing faster than $f$ is decreasing.