---
type: intuition
date: 2026-07-14
tags: [math, thermodynamics, heat, equation, intuition, sketch, proof]
---

# A Sketch & Intuition for the Heat Equation

Let's imagine we had a bar of some sort, idealized as the $x$-axis. Assume there is a fixed quantity of heat associated with the bar; at any point along the bar you could touch a thermometer to it and measure the heat held at that location on the bar at any given moment in time $\tau$.

**Here are the fundamental assumptions**:

- Heat is neither created nor destroyed. It is "conserved". The heat can move around the bar but the total heat distributed across the entire bar at any given moment, $\tau$, is always the same across time.
- Heat cannot be *teleported* to other locations across the bar. If the heat moves it must pass through the intermediate points between its initial position and its destination.
    - The details of how the heat moves will be specified later. They are important and will dictate the nature of the equation we arrive at, but this premise captures the primary idea.

As mentioned, space is identified with the variable $x$ and time with $\tau$. Heat is a function of both space and time and is denoted by $\rho(x, \tau)$.

<TODO viz: 3d space-time axes with heat equation surface>

The goal is going to be to show that

$$\frac{\partial \rho}{\partial \tau} (x,\tau) \propto \frac{\partial^2 \rho}{\partial x^2} (x, \tau)$$

To that end, Let's start off by considering what our assumptions actually mean. Consider a single point, $x$, on our bar. Our second assumption tells us that, if we assume the temperature is changing at $x$ across time, then it will be because its *neighboring* points have either distributed some of their heat to $x$, or absorbed some of $x$'s heat. That is, if the temperature at $x$ is changing across time it is because **heat is flowing into and out of $x$ on either side**.

<TODO viz: a small cylinder labeled $x$ with arrows indicating inflow and outflow on both left and right faces>

Now, here is the part that is *constructed*: we *stipulate* that **the rate of change of $\rho$ with respect to time** is determined entirely by the way $\rho$ is distributed across space. Specifically, that **regions with unbalanced temperature concentrations will disperse their heat until the region has a uniform temperature**; when one point on the bar has a higher temperature than its neighbors, then, across time, it will disperse its heat to its neighbors until the temperature of the region is constant. The rate at which this happens will be proportional to the temperature gradient from the point to its neighbors. Let's elaborate on the specifics.

Let $J_l(x, \tau)$ denote the net flow into and out of $x$ on from the left at time $\tau$. Let's also assume that there is a *resistance* or *rate* at which heat flows which is constant across the bar. Then we get that

$$J_l(x, \tau) = \frac{k}{\Delta x}(\underbrace{\rho(x-\Delta x, \tau)}_{\text{Flow into }x \text{ from the left}} - \underbrace{\rho(x, \tau)}_{\text{Flow out of x to the left}})$$

Similarly, for the right side, we get

$$J_r(x, \tau) = \frac{k}{\Delta x}(\rho(x+\Delta x, \tau) - \rho(x, \tau))$$

Let's pause a moment and make sure we understand what these equations are saying. $k$ here is acting as our constant of proportionality. It determines the rate at which heat is transferring across the bar. Crucially,

$$\frac{k}{\Delta x} \rho(y, \tau)$$

is telling us that the amount of heat that is getting transferred to-or-from at any given point, $y$, across time is proportional to the temperature gradient from $x$ to $y$ (assuming a fixed $x$). This means that if the $\rho(y) > \rho (x)$ and $y$ is nearby $x$, then heat will be transferred from $y$ to $x$ at a rate that is proportional to the difference of their temperatures. If the situation is reversed, then $x$ will transfer heat to $y$.

Why the "gradient"? Why are we dividing by $\Delta x$? Well, naturally, it will take longer for heat to disperse across a larger region. It is much faster for a 10-degree temperature difference to disperse across 10 mm than to disperse across 10 miles. Imagine you have two pans over hot burners. One of them has a very short handle and the other has a very long handle. Suppose you let the pan sit over the flame for 5 minutes. Which pan would you rather have to pick up, the short handled or the longer handled pan? Another way of thinking of it is that this is a way of saying a point's most immediate neighbors have the greatest influence on its temperature and flow; points that are far away have an influence that scales inversely by distance.

Now then, given $x$, for $\Delta \tau$ small enough, there will not have been enough time for heat to disperse very far across the bar, and so the change in $\rho$ over time can be approximated by the total flux at $(x, \tau)$. That is,

$$
\begin{align*}
\lim_{\Delta \tau \rightarrow 0} \frac{\rho (x, \tau + \Delta \tau) - \rho(x, \tau)}{\Delta \tau} &= \lim_{\Delta x \rightarrow 0} \frac{J_l(x, \tau) + J_r(x, \tau)}{2 \Delta x} \\
&= \frac{k}{2} \lim_{\Delta x \rightarrow 0} \frac{\rho(x + \Delta x, \tau) + \rho(x - \Delta x, \tau) -  2\rho(x, \tau)}{\Delta x^2}
\end{align*}
$$

The limit on the right can be evaluated by assuming that $\rho$ is a *nice* function of $x$ and that therefore

$$
\begin{align*}
\rho(x + \Delta x) &= \rho(x) + \rho'(x)\Delta x + \frac{\rho''(x)}{2} \Delta x^2 + \frac{\rho^{(3)}(x)}{3!} \Delta x^3 + \ldots \\
\frac{\rho(x + \Delta x) - \rho(x) - \rho'(x)\Delta x}{\Delta x^2} &= \frac{\rho''(x)}{2 \Delta x^2} \Delta x^2 + \frac{\rho^{(3)}(x)}{3! \Delta x^2} \Delta x^3 + \ldots \\
&= \frac{\rho''(x)}{2} + \frac{\rho^{(3)}(x)}{3!} \Delta x + \ldots
\end{align*}
$$

If we do the same expansion for $\rho(x-\Delta x) = \rho(x + (-\Delta x))$ we get

$$
\frac{\rho(x -\Delta x) - \rho(x) + \rho'(x)\Delta x}{\Delta x^2} = \frac{\rho''(x)}{2} - \frac{\rho^{(3)}(x)}{3!} \Delta x + \ldots
$$

so that adding produces

$$
\frac{\rho(x + \Delta x) + \rho(x - \Delta x) - 2\rho(x)}{\Delta x^2} = 2 (\frac{\rho''(x)}{2} + \frac{\rho^{(4)}(x)}{4!}\Delta x^2 + \ldots)
$$

so that

$$
\lim_{\Delta x \rightarrow 0} \frac{\rho(x + \Delta x, \tau) + \rho(x - \Delta x, \tau) -  2\rho(x, \tau)}{\Delta x^2} = \rho''(x)
$$

Therefore

$$ \frac{\partial \rho}{\partial \tau} (x,\tau) = \lim_{\Delta \tau \rightarrow 0} \frac{\rho (x, \tau + \Delta \tau) - \rho(x, \tau)}{\Delta \tau} = \lim_{\Delta x \rightarrow 0} \frac{J_l(x, \tau) + J_r(x, \tau)}{2 \Delta x} =  c \frac{\partial^2 \rho}{\partial x^2} (x,\tau)$$

or simply

$$
\frac{\partial \rho}{\partial \tau} (x,\tau) = c \frac{\partial^2 \rho}{\partial x^2} (x,\tau)
$$

## Comments

- I think the really tricky part is recognizing that the behavior driving this equality is **constructed**. It is **stipulated**. It is not derived. When we say that heat is distributed to equalize the temperature across space, we have artificially imposed a relationship between the time-dynamics and the space-dynamics. This is where the heat equation is really coming from. The other assumptions just add constraints to this fundamental dynamic.