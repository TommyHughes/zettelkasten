---
type: lecture note
date: 2026-07-25
tags: [math, mathematics, stochastic, process, lecture, note]
lecturer: V.K. Balakrishnan
lecture series: Physical Applications of Stochastic Processes
---

# Description

These are just my notes on the lectures in the lecture series. You'll find commentary on the topics - trying to work out for myself what the lecture materials are saying and how to think about them, and potentially worked examples and questions. These are very informal so don't expect much.

# Lecture 6: Stochastic Processes
[YouTube](https://youtu.be/FWe5uk5NA5I?si=3RW6S4RrWb1RxC5L)

The main object of our study here are **Stochastic Processes**: random variables indexed by time; processes that evolve randomly across time.

We'll start by introducing a little notation. We won't be too diligent about notation here but it's nice to have something to start off with.

We'll assume the random variables take on values denoted by $x_i$ located in some state space. The sampled time instances, sometimes called **sample epochs**, are denoted $t_i$. You can also think of the instantiations as sampling instances (sample space, sample epoch resp.).

Rather than always writing $x_i, x_j$ we can simplify our notation and use the index in place of the variable. When multiple instances occur in a specified order we may denote the index as e.g. $j_1, j_2,$ etc. That is

$$ p(x_j, t_j) = p(j, t_j)$$

Thus our primary investigations regarding such objects will take the form of asking questions like

$$ p(j, t_j) \text{ and } p(j_2, t_2; j_1, t_1) $$

where the right hand expression refers to the joint distribution. More generally

$$p(j_n, t_n ; j_{n-1}, t_{n-1}; \ldots ; j_1, t_1)$$

which is the probability that we get $j_1$ at time $t_1$ and $j_2$ at time $t_2$ and so on, where $t_1 < t_2 < \ldots < t_n$.

Obviously the class of all stochastic processes is far too general and complex for us to approach in useful application and so we find it necessary to begin by narrowing our exploration to a much smaller and simpler collection of stochastic processes. That is, we'll start by looking at stochastic processes with *short memories*. That is

$$p(j_n, t_n \vert j_{n-1}, t_{n-1}; \ldots; j_1, t_1) = p(j_n, t_n \vert j_{n-1}, t_{n-1})$$

so that

$$p(j_n, t_n ; \ldots ; j_1, t_1) = p(j_n, t_n | j_{n-1}, t_{n-1}) p(j_{n-1}, t_{n-1}; \ldots;j_1, t_1) = \prod_{i=1}^{n-1} \left[ p(j_{i+1}, t_{i+1} | j_i, t_i) \right] p(j_1, t_1)$$



What this means is that the probability distribution at time $t_n$ is no longer dependent on everything that preceded it (a memory of a sort). Instead it is only dependent on the state that immediately preceded it. This simplification is not arbitrary either. Much if not most of physics is modeled but these types of short-memory processes. Processes that depend only on their previous state are called **Markovian** or **Markov processes**.

To make our initial exploration even simpler we'll also impose a further restriction on the types of stochastic processes we'll consider. In particular we'll require that

$$p(j, t_j \vert k, t_k) = p(j, t_j - t_k \vert k , 0) = p(j, \Delta t \vert k)$$

What this means is that the probabilistic features/distribution of the system are not changing with time; "the randomness is not aging". For this reason, it does not matter where you start (here at $t_k$) all that matters is the elapsed time $t_j - t_k = \Delta t$. Such processes are called **stationary processes**.

An important tool used for handling such processes is known as the **Chapman-Kolmogorov equation** (CK) which is given by

$$p(k,t \vert j) = \sum_l p(k, t-t' \vert l) p(l, t' \vert j)$$

where $0 < t' < t$. Note that in the continuous case we would take the integral.

Balakrishan asks us to observe that this equation is non-linear in $p$, which I take to mean that, if we're trying to solve for the distribution $p$, there are two factors in each term which makes it non-linear. This makes it very difficult to solve for $p$ directly.

Again, if we make a simplifying assumption we can find a class of processes that are much more tractable. The idea is as follows: imagine that we take transitions across smaller and smaller time intervals $\Delta t$ while keeping $k \neq j$ fixed. Then if assume $p(k, t \vert j)$ is differentiable at $t = 0$, continuous at $t$, and we let $t-t' = \Delta t$, then we can use Taylor to expand

$$p(k, \Delta t \vert l) = p(k, 0 \vert l) + p'(k, 0 \vert l) \Delta t + o(\Delta t)$$

where we assume

$$\lim_{\Delta t \rightarrow 0} \frac{o(\Delta t)}{\Delta t} = 0$$

Now let us observe that

$$
p(k, 0 \vert j ) = \begin{cases} 1 & ,k = j \\ 0 & ,\text{otherwise} \end{cases}
$$

so that we may write

$$
p(k, t' \vert j) = p(k, t - \Delta t \vert j) = \sum_l p(k, 0 \vert l) p(l, t' \vert j)
$$

Taken within the context of the CK we can substract and divide to get

$$
\begin{align*}
\frac{p(k, t \vert j) - p(k, t-\Delta t \vert j)}{\Delta t} &= \frac{\sum_l p(k, \Delta t \vert l) p(l, t - \Delta t \vert j) - \sum_l p(k, 0 \vert l) p(l, t - \Delta t \vert j)}{\Delta t} \\
&= \frac{\sum_l p(l, t - \Delta t \vert j) \left( p(k, \Delta t \vert l) - p(k, 0 \vert l) \right)}{\Delta t} 
\end{align*}
$$

If we take the limit of both sides, and assume we can exchange the order of the limits (move the limit into the sum) on the right-hand side, we obtain

$$
\frac{\partial p}{\partial t} (k, t \vert j) = \sum_l \lim_{\Delta t \rightarrow 0} p(l, t - \Delta t \vert j)\frac{p(k, \Delta t \vert l) - p(k, 0 \vert l)}{\Delta t} = \sum_l p(l,t \vert j) p'(k, 0 \vert l)
$$

If we denote $p'(k, 0 \vert l) = w_{kl}$ then the above becomes

$$
\frac{\partial p}{\partial t} (k, t \vert j) = \sum_l p(l,t \vert j) w_{kl}
$$

This is called the **Forward Evolution Equation** (FEE) or the **Master Equation** (ME).

This equation can be rewritten:

$$
\frac{\partial p}{\partial t} (k, t \vert j) = \sum_{l \neq k} p(l,t \vert j) w_{kl} + w_{kk} p(k, t \vert j)
$$

Now observe that $p(k) + p(l\neq k) = 1$ for all $t$. That is, it is constant with respect to $t$. Thus the derivative with respect to $t$ is given by $p'(k, 0 \vert k) + p'(l \neq k, 0 \vert k) = w_{kk} + \sum_{l \neq k}w_{lk}$. Thus we have

$$
0 = w_{kk} + \sum_{l \neq k} w_{lk}
$$

implying

$$
w_{kk} = - \sum_{l \neq k} w_{lk}
$$

so that the above becomes

$$
\frac{\partial p}{\partial t} (k, t \vert j) = \sum_{l \neq k} \underbrace{w_{kl}p(l,t \vert j)}_{\text{gain term}} - \underbrace{w_{lk} p(k, t \vert j)}_{\text{loss term}}
$$

In fact, we can express this equation as a matrix equation in the following way. Suppose our state space is finite and discrete. That is $\vert S \vert = n$. Then we may write

$$\mathbf{\mathbf{P}}(t) = \begin{bmatrix} p(1) \\ p(2) \\ \vdots \\ p(n) \end{bmatrix}$$

which is just a vector of the probabilities for each state in the state space at time $t$. Then, if we suppress the conditional $\vert j$ notation in the interest of generality, we get

$$\frac{\partial \mathbf{P}}{\partial t}(t) = W \mathbf{P}(t)$$

where $\left[ W \right]_{ij} = w_{ij} = w(i \vert j)$. 

Since $p(k, 0 \vert j)$ is an indicator function, then for $j$ given we will have

$$\left[ \mathbf{P}(0) \right]_k = \begin{cases} 1 & ,k=j \\ 0 &,\text{otherwise}  \end{cases}$$

That is

$$\mathbf{P}(0) = \begin{bmatrix} 0 \\ \vdots \\ 1 \\ \vdots \\ 0 \end{bmatrix} = \mathbf{e}_j$$

Thus, with the initial value $\mathbf{P}(0)$, we can find a solution to this equation in the form of an exponential:

$$\mathbf{P}(t) = e^{Wt}\mathbf{P}(0) $$

## Comments

# Lecture 7: Markov Processes (P1)

[YouTube](https://youtu.be/l4FKjOfF8qs?si=yr6mdgpHdB9wof-n)

