# B1 Flows Fluctuations and Complexity <!-- omit in toc -->

- [Fluids and Flows](#fluids-and-flows)
  - [Fluxes and Conservation principles](#fluxes-and-conservation-principles)
    - [Conservation of Mass](#conservation-of-mass)
  - [Navier Stokes Equation](#navier-stokes-equation)
    - [Pressure Gradient Force](#pressure-gradient-force)
    - [Viscous Force](#viscous-force)
    - [External force](#external-force)
    - [A correction to acceleration](#a-correction-to-acceleration)
    - [Navier Stokes](#navier-stokes)
    - [Solutions to Navier Stokes](#solutions-to-navier-stokes)
      - [Poiseuille Flow](#poiseuille-flow)
    - [Reynolds Number and Dynamical Similarity](#reynolds-number-and-dynamical-similarity)

# Fluids and Flows
A fluid is a gas or a liquid whose molecules can slide past each other (unlike a solid whose molecules are regularly bound) a gas is compressible whereas a liquid can be considered mostly incompressible.


## Fluxes and Conservation principles

There are two forms of conservation in this topic, **Lagrangian** and **Flux-form** conservation.
+ **Lagrangian conservation** is something like conservation of momentum where we are thinking about particles. In a fluid we use the material derivative and think about fluid particles.
  + $\frac{D\rho}{Dt} = 0$, here $D/Dt$ refers to rate of change w.r.t time following a fluid parcel.
+ **Flux-Form conservation** is conservation in a continuum. A quantity is conserved if it's rate of change and divergence of flux sum to zero, the kind of equation we see a lot.
  + $\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\bold{u})$

### Conservation of Mass
If mass is conserved we get a simple conservation law:
$$
\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\bold{u}) = 0 
$$

We can say that if the fluid is incompressible $\rho$ is constant in time and space, which leads to:

> Incompressible $\implies \nabla\cdot\bold{u} = 0$

Liquids generally aren't very compressible so this is a useful condition.

## Navier Stokes Equation

Let's look for an equation of fluid motion! Lets think of a small fluid parcel (differential volume $\delta x\delta y\delta z$) and apply some classical mechanics. The force on the parcel is given by Newtons second law.

$$
\delta\bold{F} = \rho(\delta x\delta y\delta z)\bold{a}
$$

The force also can be written as the sum of the three components, 
+ Pressure gradient force
+ Viscous force
+ External Force

### Pressure Gradient Force

Consider a box with walls per unit area with a pressure gradient across it. In the x direction the force on the box is the force from the negative direction minus the force from the positive direction:

$$
F_{-x} - F_{+x}
=p\delta y \delta z-(p+\delta p)\delta y \delta z 
$$

This means the force per unit volume is:

$$
  \frac{dF_p}{dV} = -\frac{\delta p \delta y \delta z}{\delta x\delta y\delta z} = -\frac{\delta p}{\delta x} = -\nabla p\\
  \frac{da_p}{dM} = -\frac{\nabla p}{\rho}
$$


### Viscous Force

Viscous force is due to shear stress, i.e planes of different velocity rubbing into each other. The justification is similar to the one given in Kinetic Theory and is not very formal. Remember the picture of particles from high speed areas drifting into low speed areas and vice versa, producing a transfer of momentum.

$$
\frac{dF_\nu}{dA} = \rho\nu\frac{\partial u}{\partial y}
$$

Where $\frac{dF_\nu}{dA}$ is called viscous shear stress and $\nu$ is the coefficient of viscosity. Continuing for this we need to find an acceleration:
$$
F_\nu = \rho\nu\frac{\partial u}{\partial y}\delta x \delta z\\
a_\nu = \frac{F_\nu}{\rho \delta x \delta y \delta z} = v\frac{\partial^2 u}{\partial y^2}
$$ 

In general we find that viscous acceleration is more complicated.
$$
a_\nu = \nu\bigg(\nabla^2\bold{u} + \frac{1}{3}\nabla\nabla\cdot\bold{u}\bigg)
$$
If we assume incompressibility (which we often can) then the condition $\nabla\cdot\bold{u} = 0$ can be used.

### External force

Often the external force to consider is gravity so here the acceleration due to external force can be written as $\bold{a}_{ext} = -\bold{g}$

### A correction to acceleration

Typically we think of acceleration as $\bold{a} = \frac{d\bold{u}}{dt}$ with $\bold{u}(t)$ but here we have been thinking of fluid parcels so we need to think of following that fluid parcel through space (i.e the *material derivative*) when we calculate $\bold{a}$.
$$
\begin{aligned}
    \frac{d}{dt}\bold{u}(x, y, z, t) &= \frac{\partial\bold{u}}{\partial x}\frac{dx}{dt} + \frac{\partial\bold{u}}{\partial y}\frac{dy}{dt}  + \frac{\partial\bold{u}}{\partial z}\frac{dz}{dt} + \frac{\partial\bold{u}}{\partial t}\\
    \frac{Du}{Dt}=\bold{a} &= \frac{\partial\bold{u}}{\partial t} + (\bold{u}\cdot \nabla)\bold{u}
\end{aligned}
$$

### Navier Stokes

To get something out of this we need to put all these accelerations together.

$$
\bold{a} = \bold{a}_p + \bold{a}_\nu + \bold{a}_{ext}\\
\ \\
\frac{\partial \bold{u}}{\partial t} + (\bold{u}\cdot\nabla)\bold{u} + \frac{\nabla p}{\rho} + \bold{g} = \nu\nabla^2\bold{u}
$$

This is the navier stokes equation for incompressible fluids (as we used $\nabla\cdot\bold{u} = 0$ to simplify $\bold{a}_\nu$)

### Solutions to Navier Stokes
#### Poiseuille Flow

Poiseuille flow is tough to spell but otherwise it's pretty simple, it just means pressure induced flow, or laminar flow between two plates.

Let's consider poiseuille flow through two plates (at $y=\pm h$) since our fluid is incompressible and gravity is ignored we have,

$$
\frac{\partial \bold{u}}{\partial t} + (\bold{u}\cdot\nabla)\bold{u} + \frac{\nabla p}{\rho} = \nu\nabla^2\bold{u}
$$

we'll seek a *steady state solution*, and assume $u$ is independent of $z$ so we have $u(y)$ only. This means the equation simplifies to,

$$
\frac{1}{\rho}\frac{\partial p}{\partial x} = \nu\frac{\partial^2u}{\partial y^2} = G\\
G = \frac{1}{\rho}\frac{\partial p}{\partial x}
$$

The pressure gradient is in the x$ direction along our flow. This gives the solution,

$$
    u = \frac{G}{2\nu}(h^2 - y^2)
$$

This is a parabolic flow like so:

<img src="./Figs/Poisseuille.png" alt="Figure Missing" height="200"/>

### Reynolds Number and Dynamical Similarity

When we have an equation like Navier Stokes it helps to represent them in a dimensionless form so we can solve them generally and apply dimensions later. For example Navier Stokes uses a velocity and length scale which we can remove.

$|\bold{u}| \sim U$

$\nabla \sim 1/L$

if we write the terms of the equation in non-dimensional versions we can solve for a non-dimensional navier stokes.

$$
\bold{\tilde{u}} = \frac{\bold{u}}{U},\ \bold{\tilde{x}} = \frac{\bold{x}}{L},\ \tilde{t} = \frac{U}{L}t,\ \tilde{p} = \frac{p}{\rho U^2}, \tilde{\nabla} = L\nabla\\
\ \\
\implies \frac{\partial\bold{\tilde{u}}}{\partial\tilde{t}} + \bold{\tilde{u}} \cdot\tilde{\nabla}\bold{\tilde{u}} + \tilde{\nabla}\tilde{p} = \frac{1}{Re}\tilde{\nabla}^2\bold{\tilde{u}}\\
\text{if }\  \tilde{\nabla} \cdot \bold{\tilde{u}} = 0
$$

The only dimensional number here is Re, **Reynolds Number**.
$$
Re = \frac{UL}{\nu}
$$
 Physical systems with the same Reynolds number are dynamically similar and will behave similarly.
 It is clear that for high Re viscosity can be ignored and for low Re it dominates. Reynold conducted an experiment where he increased Reynolds number and observed a stream of ink and showed this very clearly.

<img src="./Figs/Reynolds.jpg" alt="Figure Missing" height="200"/>

(a) is low Re, (b) is critical and (c) is high Re.

(a) is described as **Steady laminar flow**, (b) as **Unsteady Laminar flow** and (c) as **Turbulence**. Transitions between regimes are called Bifurcations but we'll get to those later.