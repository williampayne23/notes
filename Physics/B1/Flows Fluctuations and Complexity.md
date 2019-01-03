# B1 Flows Fluctuations and Complexity <!-- omit in toc -->

- [Rules, Definitions, and Equations](#rules-definitions-and-equations)
  - [Diagrams of flows](#diagrams-of-flows)
    - [Flow Fields](#flow-fields)
    - [Streamlines](#streamlines)
    - [Stream Function](#stream-function)
    - [Velocity Potential](#velocity-potential)
  - [Fluxes and Conservation principles](#fluxes-and-conservation-principles)
    - [Conservation of Mass](#conservation-of-mass)
    - [Hydraulic Jumps](#hydraulic-jumps)
  - [Navier Stokes Equation](#navier-stokes-equation)
    - [Pressure Gradient Force](#pressure-gradient-force)
    - [Viscous Force](#viscous-force)
    - [External force](#external-force)
    - [A correction to acceleration](#a-correction-to-acceleration)
    - [Navier Stokes](#navier-stokes)
    - [Solutions to Navier Stokes](#solutions-to-navier-stokes)
      - [Poiseuille Flow](#poiseuille-flow)
    - [Reynolds Number and Dynamical Similarity](#reynolds-number-and-dynamical-similarity)
    - [Boundary Layers](#boundary-layers)
      - [Impulsive Boundary Layers](#impulsive-boundary-layers)
      - [Blasius Boundary Layers](#blasius-boundary-layers)
      - [Boundary Separation](#boundary-separation)
  - [Vorticity and Circulation](#vorticity-and-circulation)
    - [Kelvins Circulation Theorem](#kelvins-circulation-theorem)
    - [Bernouli's Theorem](#bernoulis-theorem)
    - [Lift Force](#lift-force)
- [Ideal Fluid Examples](#ideal-fluid-examples)
  - [Bath Plug Vortex](#bath-plug-vortex)
- [Very Viscous Flows](#very-viscous-flows)
  - [Stokes Equations](#stokes-equations)
  - [EXAMPLE Stokes flow past a sphere](#example-stokes-flow-past-a-sphere)
  - [Biological Motility At Low Reynolds Number](#biological-motility-at-low-reynolds-number)

# Rules, Definitions, and Equations
A fluid is a gas or a liquid whose molecules can slide past each other (unlike a solid whose molecules are regularly bound) a gas is compressible whereas a liquid can be considered mostly incompressible.

## Diagrams of flows

### Flow Fields
A useful way to diagram flows is to draw flow fields, or arrows, a good way to do this is to evaluate the arrows on the axis and work from there.

### Streamlines
Another useful way is to draw *streamlines* which are curves in the direction of $\underline{u}$ for any given t. They are defined by 

$$
\frac{dx}{u_x} = \frac{dy}{u_y} = \frac{dz}{u_z} = dt
$$

### Stream Function

A Stream function can be defined as

$$
\underline{u} = \nabla\times(\psi\underline{e}_z)
$$

Which seems a little weird but basically comes to

$$
u_x = \frac{\partial\psi}{dy},\ u_y = \frac{\partial\psi}{dx}
$$

The definition using curl means that a fluid defined with a stream function would be incompressible ($\nabla\cdot\underline{u}=0$)

### Velocity Potential

If the flow is irrotational we have $\nabla\times\underline{u} = 0$ (we'll see that later) so we can define a velocity potential.

$$
\underline{u} = \nabla\phi
$$

Lines of constant $\phi$ are equipotential lines and are perpendicular to streamlines.


## Fluxes and Conservation principles

There are two forms of conservation in this topic, **Lagrangian** and **Flux-form** conservation.
+ **Lagrangian conservation** is something like conservation of momentum where we are thinking about particles. In a fluid we use the material derivative and think about fluid particles.
  + $\frac{D\rho}{Dt} = 0$, here $D/Dt$ refers to rate of change w.r.t time following a fluid parcel.
+ **Flux-Form conservation** is conservation in a continuum. A quantity is conserved if it's rate of change and divergence of flux sum to zero, the kind of equation we see a lot.
  + $\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\underline{u})$

### Conservation of Mass
If mass is conserved we get a simple conservation law:
$$
\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\underline{u}) = 0 
$$

We can say that if the fluid is incompressible $\rho$ is constant in time and space, which leads to:

> Incompressible $\implies \nabla\cdot\underline{u} = 0$

Liquids generally aren't very compressible so this is a useful condition.

### Hydraulic Jumps
A hydraulic jumps are produced when a fast moving region encounters a slow moving region. The result is a rising water level sort of like a water traffic jam. I'm not sure how much we're meant to know since it's in none of the notes.

## Navier Stokes Equation

Let's look for an equation of fluid motion! Lets think of a small fluid parcel (differential volume $\delta x\delta y\delta z$) and apply some classical mechanics. The force on the parcel is given by Newtons second law.

$$
\delta\underline{F} = \rho(\delta x\delta y\delta z)\underline{a}
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
a_\nu = \nu\bigg(\nabla^2\underline{u} + \frac{1}{3}\nabla\nabla\cdot\underline{u}\bigg)
$$
If we assume incompressibility (which we often can) then the condition $\nabla\cdot\underline{u} = 0$ can be used.

### External force

Often the external force to consider is gravity so here the acceleration due to external force can be written as $\underline{a}_{ext} = -\underline{g}$

### A correction to acceleration

Typically we think of acceleration as $\underline{a} = \frac{d\underline{u}}{dt}$ with $\underline{u}(t)$ but here we have been thinking of fluid parcels so we need to think of following that fluid parcel through space (i.e the *material derivative*) when we calculate $\underline{a}$.
$$
\begin{aligned}
    \frac{d}{dt}\underline{u}(x, y, z, t) &= \frac{\partial\underline{u}}{\partial x}\frac{dx}{dt} + \frac{\partial\underline{u}}{\partial y}\frac{dy}{dt}  + \frac{\partial\underline{u}}{\partial z}\frac{dz}{dt} + \frac{\partial\underline{u}}{\partial t}\\
    \frac{Du}{Dt}=\underline{a} &= \frac{\partial\underline{u}}{\partial t} + (\underline{u}\cdot \nabla)\underline{u}
\end{aligned}
$$

### Navier Stokes

To get something out of this we need to put all these accelerations together.

$$
\underline{a} = \underline{a}_p + \underline{a}_\nu + \underline{a}_{ext}\\
\ \\
\frac{\partial \underline{u}}{\partial t} + (\underline{u}\cdot\nabla)\underline{u} + \frac{\nabla p}{\rho} + \underline{g} = \nu\nabla^2\underline{u}
$$

This is the navier stokes equation for incompressible fluids (as we used $\nabla\cdot\underline{u} = 0$ to simplify $\underline{a}_\nu$)

### Solutions to Navier Stokes
#### Poiseuille Flow

Poiseuille flow is tough to spell but otherwise it's pretty simple, it just means pressure induced flow, or laminar flow between two plates.

Let's consider poiseuille flow through two plates (at $y=\pm h$) since our fluid is incompressible and gravity is ignored we have,

$$
\frac{\partial \underline{u}}{\partial t} + (\underline{u}\cdot\nabla)\underline{u} + \frac{\nabla p}{\rho} = \nu\nabla^2\underline{u}
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

$|\underline{u}| \sim U$

$\nabla \sim 1/L$

if we write the terms of the equation in non-dimensional versions we can solve for a non-dimensional navier stokes.

$$
\underline{\tilde{u}} = \frac{\underline{u}}{U},\ \underline{\tilde{x}} = \frac{\underline{x}}{L},\ \tilde{t} = \frac{U}{L}t,\ \tilde{p} = \frac{p}{\rho U^2}, \tilde{\nabla} = L\nabla\\
\ \\
\implies \frac{\partial\underline{\tilde{u}}}{\partial\tilde{t}} + \underline{\tilde{u}} \cdot\tilde{\nabla}\underline{\tilde{u}} + \tilde{\nabla}\tilde{p} = \frac{1}{Re}\tilde{\nabla}^2\underline{\tilde{u}}\\
\text{if }\  \tilde{\nabla} \cdot \underline{\tilde{u}} = 0
$$

The only dimensional number here is Re, **Reynolds Number**.
$$
Re = \frac{UL}{\nu}
$$
 Physical systems with the same Reynolds number, are geometrically scaled in the same way, and applied forces and pressure gradients also scale together, will be dynamically similar and will behave similarly.
 It is clear that for high Re viscosity can be ignored and for low Re it dominates. Reynold conducted an experiment where he increased Reynolds number and observed a stream of ink and showed this very clearly.

<img src="./Figs/Reynolds.jpg" alt="Figure Missing" height="200"/>

(a) is low Re, (b) is critical and (c) is high Re.

(a) is described as **Steady laminar flow**, (b) as **Unsteady Laminar flow** and (c) as **Turbulence**. Transitions between regimes are called Bifurcations but we'll get to those later.

### Boundary Layers

A key Boundary condition for solving navier stokes is the no normal flow (and sometimes the no slip) boundary condition. That is that velocity perpendicular (and sometimes parallel)
to a fixed surface is $0$. A boundary layer of velocity zero must then exist.

#### Impulsive Boundary Layers
Imagine a fluid adjacent to a plate which starts moving with speed $u=U_0$ at time $t=0$. Thanks to the no-slip condition the fluid touching the plate has speed $U_0$ what gives us the width $\delta$ defined as the distance until the speed is $1\%$ of $U_0$?

The relevant terms of Navier Stokes (as we'll see later) are:

$$
\frac{\partial u}{\partial t} = \nu\frac{\partial^2u}{\partial y^2}
$$

The solution can't depend on U_0 (The notes aren't specific as to why >:( but I guess it's because it needs to scale dimensionally) so the only dimensionally sane result from this is

$$
\delta = \kappa(\nu t)^{1/2}
$$

Where $\kappa$ is a dimensionless constant. This is experimentally confirmed with $\kappa\approx4.99$

#### Blasius Boundary Layers

Now consider a uniform flow approaching a finite plate (I'm sure you can so I'm not including a picture) the flow far from the plate is $u=U_0$. We can now interpret $t$ from above as the time a fluid particle has been in contact with the plate ($x/U_0$) which gives 
$$
\delta = \kappa\bigg(\frac{\nu x}{U_0}\bigg)^2
$$

This is correct and agrees with an analytical solution to navier stokes!

#### Boundary Separation

When flow just outside the boundary layer slows down the boundary layers separate which leads to some interesting effects.
<img src="./Figs/BoundarySeperation.jpeg" width="100%"/>

## Vorticity and Circulation

*Vorticity* is defined as the curl of velocity
$$
\underline{\omega} = \nabla\times\underline{u}
$$

*Circulation* around a closed contour is defined as the line integral of velocity along that contour:

$$
\Gamma_C = \oint_C\underline{u}\cdot d\underline{l} = \iint_S\underline{\omega}\cdot d\underline{S}
$$

Vorticity is a local measure of spin. I.e the spin of a small fluid parcel around it's own axis. If you placed a little paddle in a fluid it's angular speed would be $\omega/2$.

### Kelvins Circulation Theorem

The rate of change of a circulation for a closed contour is:


$$
\frac{D\Gamma_C}{Dt} = \oint_C\bigg(\frac{D\underline{u}}{Dt}\bigg)\cdot d\underline{l} + \oint_C\underline{u}\cdot\bigg(\frac{Dd\underline{l}}{Dt}\bigg)
$$

Looking at the way the contour changes we can evaluate our terms:

<img src="./Figs/Circulation1.jpg" alt="Figure Missing" width="42.1%"/><img src="./Figs/Circulation2.jpg" alt="Figure Missing" width="57%"/>

So we get

$$
\dfrac{Dd\underline{l}}{Dt} = d\underline{l}\cdot\nabla\underline{u}
$$

So

$$
\oint_C\underline{u}\cdot\bigg(\frac{Dd\underline{l}}{Dt}\bigg)=\oint_C\underline{u}\cdot(d\underline{l}\cdot\nabla\underline{u})=\oint\nabla\bigg(\frac{\underline{u}\cdot\underline{u}}{2}\bigg)\cdot d\underline{l} = 0
$$

We can use navier stokes to get $D\underline{u}/Dt$ so we end up with Kelvin's Circulation Theorem:

$$
\frac{D\Gamma_C}{Dt} = -\oint_C\frac{dp}{\rho} + \oint_c\nu\nabla^2\underline{u}\cdot d\underline{l}
$$

In the absence of density and viscosity variations circulation is conserved which is apparently very useful, yay us!

### Bernouli's Theorem

If we take the scalar product of $\underline{u}$ with Navier Stokes we get the KE equation:

$$
\frac{\partial}{\partial t}\bigg(\frac{\underline{u}\cdot\underline{u}}{2}\bigg) + \underline{u}\cdot\nabla\bigg(\frac{\underline{u}\cdot\underline{u}}{2} + \frac{p}{\rho} + gz\bigg)=\nu\underline{u}\cdot\nabla^2\underline{u}
$$

Without time dependence or viscosity we have:

$$ 
\underline{u}\cdot\nabla\bigg(\frac{\underline{u}\cdot\underline{u}}{2} + \frac{p}{\rho} + gz\bigg) = 0
$$

or

$$ 
\frac{\underline{u}\cdot\underline{u}}{2} + \frac{p}{\rho} + gz = B(\psi)
$$

This is a form of *Bernoulli's theorem* basically along a streamline of constant height (potential enrgy) when pressure is low velocity is high and vice versa. It's basically a statement of conservation of energy:

$$
\underbrace{\overbrace{P_1}^\text{Pressure Energy} + \overbrace{\frac{1}{2}\rho v^2_1}^\text{KE density} + \overbrace{\rho gh_1}^\text{Potential Density}}_\text{Energy Density Before} = \underbrace{\overbrace{P_2}^\text{Pressure Energy} + \overbrace{\frac{1}{2}\rho v^2_2}^\text{KE density} + \overbrace{\rho gh_2}^\text{Potential Density}}_\text{Energy Density After}
$$

### Lift Force

A result of Bernouli's theorem is lift force, if a fluid is flowing faster on the lower edge to the upper edge of an object then the pressure differential creates a lift force.

# Ideal Fluid Examples
An ideal fluid is a fluid is inviscid ($\nu = 0$) and of uniform density ($\nabla\rho=0$ and $\nabla\cdot\underline{u}=0$) In this limit we have

$$
\frac{D\Gamma_C}{Dt} = 0
$$

And in two dimensional flow it is irrotational ($D\omega/Dt = 0$)


## Bath Plug Vortex

<!-- TODO: IDEAL FLUID EXAMPLE LECTURE 5 or 6 @20m-->

# Very Viscous Flows

## Stokes Equations 

Very viscous flows a flows with $Re<<1$ this allows us to neglect $\underline{u}\cdot\nabla\underline{u}$ the *inertial acceleration* term of Navier Stokes as well as assume $\rho$ is constant and neglect time dependence and gravity! This is a useful set of assumptions and gives us the momentum equation:

$$
\nabla p = \mu\nabla^2\underline{u}
$$

We can also use the incompressibility equation:

$$
\nabla\cdot\underline{u} = 0
$$

These are known as **Stokes Equations**

If we take the divergence of the former we get a laplace equation for pressure but if we do the curl instead we get

$$
\nabla^2(\nabla\times\underline{u}) = \nabla^2\underline{\omega} = 0
$$

A set of laplacian equations in the components of vorticity! We can couple this with the boundary conditions no-slip and no-normal-flow to use $\underline{u}=0$ at solid boundaries!

## EXAMPLE Stokes flow past a sphere
<!-- TODO: STOKES FLOW PAST A SPHERE LECTURE 7-->
## Biological Motility At Low Reynolds Number
In viscous flows we have *Purcell's scallop theorem* which states that viscous flows are reversible this means an animal with just one hinge like a scallop will open and close and be in the exact same space. Motion is only possible if movement is non-reciprocal.