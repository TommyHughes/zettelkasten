---
type: theorem
date: 2026-08-03
tags: [math, mathematics, theorem, proof, mean value theorem, general, analysis]
---

# Generalized Mean Value Theorem

If $f$ and $g$ are continuous on the closed interval $[a,b]$ and differentiable on the open interval $(a,b)$, then there exists a point $c \in (a,b)$ where

$$[f(b) - f(a)] g'(c) = [g(b) - g(a)] f'(c)$$

If $g'$ is never zero on $(a,b)$, then the conclusion can be stated as

$$\frac{f'(c)}{g'(c)} = \frac{f(b) - f(a)}{g(b) - g(a)}$$

**Proof**

Let

$$h(x) = [f(b) - f(a)]g(x) - [g(b) - g(a)]f(x)$$

Then it is easy to show that $h(b) = h(a)$ and that

$$h'(x) = [f(b) - f(a)]g'(x) - [g(b) - g(a)]f'(x)$$

By Rolle's Theorem it follows that there exists a $c \in (a,b)$ such that $h'(c) = 0$ so that

$$[f(b) - f(a)]g'(c) - [g(b) - g(a)]f'(c)$$

$\square$

## Comments
- So algebraic intuition led me to the function $h = \Delta f g - \Delta g f$; it's derivative was needed and just so happened to satisfy Rolle's. That said, I still think it's important to understand what $h$ is doing or how to think of it conceptually/geometrically. To that end, I'm still unsure. That said it seems to be related to thinking of the slope of a curve traced out by $(g(x), f(x))$. That is, a plane with horizontal axis $g(x)# and vertical axis $f(x)$. Then $\frac{\Delta f}{\Delta g}$ can be thought of as the slope of the secant of parametric curve given by $(g(x), f(x))$. We can even think of it as an inner product: $$h(x) = \left\langle (\Delta f, -\Delta g), (g(x), f(x))\right\rangle$$. I feel like somewhere in here there is a nice explanation of what's going on, but i'm not quite sure what yet.