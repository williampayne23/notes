# B5 General Relativity and Cosmology <!-- omit in toc -->
- [Curved Spacetime](#curved-spacetime)
  - [The Maths of Curved spacetime](#the-maths-of-curved-spacetime)
    - [Transformation laws](#transformation-laws)
    - [The Covariant Derivative](#the-covariant-derivative)
  - [Gravity](#gravity)
    - [Gravitational and Inertial Mass](#gravitational-and-inertial-mass)
    - [Equivalence Principles](#equivalence-principles)
    - [The Geodesic Equation](#the-geodesic-equation)
    - [The Metric](#the-metric)
    - [The Newtonian Limit](#the-newtonian-limit)

# Curved Spacetime
## The Maths of Curved spacetime
### Transformation laws

The simplest vector we can write is the differential coordinate $dx^\mu$ if we transform to some primed frame

$$
dx^{\prime\mu} = \frac{\partial x^{\prime\mu}}{\partial x^\nu}dx^\nu
$$

> Here $dx^\nu$ is a true vector and $x^\nu$ is a component. So the whole vector is $x^\nu dx^\nu$.

We can now define an arbitrary contravariant vector transformation as...

$$
V^{\prime\mu} = \frac{\partial x^{\prime\mu}}{\partial x^\nu}V^\nu
$$

and a covariant vector transformation is...

$$
V^\prime_\mu =  \frac{\partial x^\nu}{\partial x^{\prime\mu}}V_\nu
$$

> Remember this with CO LOW PRIME BELOW.

Any contravariant tensor, covariant tensor, or mixed tensor is transformed by stacking these transformations (in fact this is what defines them as Tensors).

### The Covariant Derivative

Looking at the covariant transformation you can expect it would have a different kind of derivative. You'd be right! Let's try it...

$$
\frac{dA^{\prime\alpha}}{d\tau} = \frac{d}{d\tau}\bigg(\frac{\partial\xi^\alpha}{\partial x^\mu}A^\mu\bigg) = \frac{\partial\xi^\alpha}{\partial x^\mu}\frac{dA^\mu}{d\tau} + \frac{\partial^2\xi^\alpha}{\partial x^\mu\partial x^\nu}\frac{dx^\nu}{d\tau}A^\mu
$$

If we transform this result back to the unprimed frame we get...

$$
\frac{\partial x^\lambda}{\partial\xi^\alpha}\frac{dA^{\prime\alpha}}{d\tau} = \frac{dA^\lambda}{d\tau} + \Gamma^\lambda_{\mu\nu}A^\mu\frac{dx^\nu}{d\tau}
$$

Where we've used the affine connection...
$$
\Gamma^\rho_{\mu\nu} = \frac{\partial x^\rho}{\partial\xi^\alpha}\frac{\partial^2\xi^\alpha}{\partial x^\mu \partial x^\nu}
$$

We can now define the covariant derivative as...
$$
\nabla_\mu A^\lambda = A^\lambda_{;\mu} = \frac{dA^\lambda}{dx^\mu} + \Gamma^\lambda_{\mu\nu}A^\mu
$$

Finally the covariant derivative of tensors is given by...

$$
T^{\lambda\kappa}_{;\mu} = \frac{\partial T^{\lambda\kappa}}{\partial x^\mu} + \Gamma^\lambda_{\mu\nu}T^{\nu\kappa} + \Gamma^\kappa_{\nu\mu}T^{\lambda\nu}\\
\ \\
T_{\lambda\kappa;\mu} = \frac{\partial T_{\lambda\kappa}}{\partial x^\mu} - \Gamma_{\lambda\mu}^\nu T_{\nu\kappa} - \Gamma^\nu_{\kappa\mu}T_{\lambda\nu}\\
\ \\
T^\lambda_{\kappa;\mu} = \frac{\partial T^\lambda_\kappa}{\partial x^\mu} + \Gamma^\lambda_{\nu\mu}T^\nu_\kappa - \Gamma^\nu_{\kappa\mu}T^\lambda_\nu\\
$$
## Gravity

If General relativity is meant to be an improvement on the Newtonian view of gravity it helps to know what we're improving on. The force due to newtonian gravity is given by...

$$
\bold{F} = Gm_1m_1\frac{\bold{x}_2-\bold{x}_1}{|\bold{x}_2-\bold{x}_1|^3}
$$

If we say the resulting gravitational acceleration experienced by $m_1$ is $\bold{g}$ then we can write $\bold{g}$ in terms of a potential $\bold{g} = -\nabla\phi$ such that

$$
\phi(\bold{x}) = \sum_i\frac{Gm_i}{|\bold{x}-\bold{x}_i|}
$$

for a distribution of point masses $m_i$. If we want to generalise this to a continuous distribution then we have

$$
\nabla^2\phi = 4\pi G\rho
$$

Where $\rho$ is the density of mass. It is going to be important to get some relationship like that in the newtonian limit if we want general relativity to work as an explanation of gravity.

### Gravitational and Inertial Mass

In the above we used the mass in Newton's Law of Gravitation and Newton's second law were the same. This is not necessarily the case. We call the mass in the former *Gravitational Mass* and in the latter *Inertial Mass*. Imagine we have two masses suspended on a rod. They will be subject to a gravitational force $g$ in the direction that rotates the rod. If their gravitational and inertial masses are different we would expect them to accelerate in that direction...

$$
m_{I1}a_1 = m_{G1}g\\
m_{I2}a_2 = m_{G2}g
$$

We can rearrange these accelerations to a dimensionless quantity and measure it in experiment...

$$
R = \frac{a_1-a_2}{a_1+a_2} = \frac{(m_{G1}/m_{I1} - m_{G2}/m_{I2})}{(m_{G1}/m_{I1} + m_{G2}/m_{I2})}\approx(0.3\pm1.8)\times 10^{-13}
$$

This value is so small we can construct some Equivalence Principles..

### Equivalence Principles

+ Weak Equivalence Principle: All uncharged freely falling particles follow the same trajectory if given the same initial conditions.
+ Einstein Equivalence Principle: WEP but also in all freely falling frames we recover (locally) special relativistic physics.
+ Strong Equivalence Principle: WEP is valid for massive gravitating objects and also test particles and in all freely falling frames we recover special relativistic physics.

This is basically a statement that if you fall freely you can no longer notice the effects of gravity. Freely falling frames are in flat spacetime and regain special relativistic physics. What's more is that since accelerating to meet gravity cancels it out accelerating from a freely falling frame produces an indistinguishable effect from gravity!

$$
\begin{aligned}
\frac{d^2x}{dt^2}&=0\\
x &= x^\prime + \frac{gt^2}{2}\\
\implies \frac{d^2x^\prime}{dt^2} &= -g
\end{aligned}
$$


### The Geodesic Equation

Remember the weird way the equivalence principle was phrased?

It meant a particles path through a gravitational field is the same as if it's path was a straight line through an accelerated frame. Finding a trajectory then is as simple as drawing the equivalent of a straight line in curved spacetime. The straight line through curved space is called a geodesic and is (like a line in Minkowski spacetime) the shortest path between two points.

So for our local inertial coordinates we have...

$$
\frac{d^2\xi^\alpha}{d\tau^2} = 0
$$

Where $\xi^\mu$ represents local inertial coordinates

Our straight line through local Mincowski like spacetime is simply a stationary point w.r.t proper time...

Now we transform to general coordinates using the chain rule.

$$
0 = \frac{d}{d\tau}\bigg(\frac{\partial\xi^\alpha}{\partial x^\mu}\frac{dx^\mu}{d\tau}\bigg) = 
\frac{\partial\xi^\alpha}{\partial x^\mu}\ddot{x}^\mu + \dot{x}^\mu\dot{x}^\nu\frac{\partial^2\xi^\alpha}{\partial x^\mu \partial x^\nu} = 
\frac{\partial\xi^\alpha}{\partial x^\mu}\frac{\partial x^\rho}{\partial\xi^\alpha}\ddot{x}^\mu + \dot{x}^\mu\dot{x}^\nu\frac{\partial^2\xi^\alpha}{\partial x^\mu \partial x^\nu}\frac{\partial x^\rho}{\partial\xi^\alpha}
$$

Where the last expression is just multiplied through by $\frac{\partial x^\rho}{\partial\xi^\alpha}$ This helps us rewrite the first term as $\frac{\partial\xi^\alpha}{\partial x^\mu}\frac{\partial x^\rho}{\partial\xi^\alpha} = \delta^\rho_\mu$. This gives the full geodesic...

$$
\frac{d^2x^\rho}{d\tau^2} + \Gamma^\rho_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}=0\\\ \\
\Gamma^\rho_{\mu\nu} = \frac{\partial x^\rho}{\partial \xi^\alpha}\frac{\partial^2\xi^\alpha}{\partial x^\mu\partial x^\nu}
$$

This fully describes the trajectory of a particle through curved spactime. As we saw before $\Gamma^\rho_{\mu\nu}$ is the affine connection. It is not actually a tensor but it does clearly contain a lot of information about the curvature of the system.


### The Metric

General relativity is all about curved spacetime. We need some way to describe this spacetime and luckily we basically already have it! Remember in special relativity we had the metric...

$$
g_{\mu\nu} = \eta_{\mu\nu} = \begin{pmatrix}
    -1 & 0 & 0 & 0\\
     0 & 1 & 0 & 0\\
     0 & 0 & 1 & 0\\
     0 & 0 & 0 & 1\\
\end{pmatrix}
$$

If we go back to our local inertial coordinates

$$
-c^2d\tau^2 = \eta_{\alpha\beta}d\xi^\alpha d\xi^\beta = d\xi_\beta d\xi^\beta
$$

And we can generalise this for any coordinate system...

$$
-c^2d\tau^2 = g_{\mu\nu}dx^\mu dx^\nu\\
\text{where}\\
g_{\mu\nu} = \eta_{\alpha\beta}\frac{\partial\xi^\alpha}{\partial x^\mu}\frac{\partial\xi^\beta}{\partial x^\nu}
$$

Notice we recover $g_{\mu\nu} = \eta_{\mu\nu}$ in flat space time (where $dx^\nu = d\xi$) plus we still have the identities...

$$
g_{\mu\nu} = g_{\nu\mu}\\
g_{\mu\nu}g^{\nu\rho} = \delta_\mu^\rho\\
\ \\
\partial_\mu = \frac{\partial}{\partial x^\mu}\implies
\partial_\mu x_\nu = g_{\mu\nu}
$$

We can now write the affine connection in terms of the metric...

$$
\Gamma^\rho_{\mu\nu} = \frac{1}{2}g^{\rho\sigma}(\partial_\mu g_{\nu\sigma} + \partial_\nu g_{\nu\sigma} - \partial_\sigma g_{\nu\mu})
$$

So for a diagonal metric...

$$
\begin{aligned}
\Gamma^a_{ba} = \Gamma^a_{ab} &= \frac{1}{2g_{aa}}\frac{\partial g_{aa}}{\partial x^b}\text{ No sum here despite repeated indices}\\
\Gamma^a_{bb} &= -\frac{1}{2g_{aa}}\frac{\partial g_{bb}}{\partial x^a}\text{ No sum}\\
\Gamma^a_{bc} &= 0 
\end{aligned}
$$

### The Newtonian Limit

So now we have the geodesic and a metric to describe it with but what do we do with it?? Well let's first check it still fits in the Newtonian limit. We can describe the newtonian limit as having...

+ **Weak Gravity**: The metric is close to the minckowski metric. So $g_{\mu\nu} = \eta_{\mu\nu} + h_{\mu\nu}$ and $g^{\mu\nu} = \eta^{\mu\nu} - h^{\mu\nu}$ with $|h_{\mu\nu}| \llless 1$
+ **Slow Motion**: $\bold{v}\llless c$ or $cdt\llless dx^i$ of $\tau\approx t$.
+ **Slowly Varying Gravitational Fields**: This means that derivatives of metrics can be ignored.

This gives for $g_{00}$

$$
\frac{d^2x^\rho}{d\tau^2} + \Gamma^\rho_{00}\bigg(\frac{dx^0}{d\tau}\bigg)^2\approx0\\\ \\
\Gamma^\rho_{00} = -\frac{1}{2}g^{\rho\mu}\frac{\partial g_{00}}{\partial x^\mu} = -\frac{1}{2}\eta^\rho\mu\frac{\partial h_{00}}{\partial x^\mu} = \frac{1}{2}\frac{\partial h_{00}}{\partial x^\rho}\\\ \\
\implies \frac{d^2\bold{x}}{d\tau^2} = \frac{1}{2}\bigg(\frac{dx^0}{d\tau}\bigg)^2\nabla h_{00}
$$

Which is comparable to the Newtonian result! All we need is...

$$
g_{00} = -\bigg(1+\frac{2\phi}{c^2}\bigg) \implies h_{00} = -\frac{2\phi}{c^2}
$$