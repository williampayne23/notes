# B5 General Relativity and Cosmology <!-- omit in toc -->
- [Curved Spacetime](#curved-spacetime)
  - [Newtonian Gravity](#newtonian-gravity)
    - [Gravitational and Inertial Mass](#gravitational-and-inertial-mass)
      - [Equivalence Principles](#equivalence-principles)

# Curved Spacetime
## Newtonian Gravity

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

This value is so small we can construct some Equivalence Principles...

#### Equivalence Principles

+ Weak Equivalence Principle: All uncharged freely falling particles follow the same trajectory if given the same initial conditions.
+ Einstein Equivalence Principle: WEP but also in all freely falling frames we recover (locally) special relativistic physics.
+ Strong Equivalence Principle: WEP is valid for massive gravitating objects and also test particles and in all freely falling frames we recover special relativistic physics.

This is basically a statement that spacetime is flat locally to the first order (like with a sphere) and that gravitational fields are indistinguishable from acceleration.