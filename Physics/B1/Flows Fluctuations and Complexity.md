# B1 Flows Fluctuations and Complexity <!-- omit in toc -->

- [Flows](#flows)
  - [Diagrams of flows](#diagrams-of-flows)
    - [Flow Fields](#flow-fields)
    - [Streamlines](#streamlines)
    - [Stream Function](#stream-function)
    - [Velocity Potential](#velocity-potential)
  - [Navier Stokes Equation](#navier-stokes-equation)
    - [Fluxes and Conservation principles](#fluxes-and-conservation-principles)
      - [Conservation of Mass](#conservation-of-mass)
    - [Derivation of the Formula](#derivation-of-the-formula)
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
  - [Special Cases](#special-cases)
    - [Very Viscous Flows](#very-viscous-flows)
      - [Stokes Equations](#stokes-equations)
      - [EXAMPLE Stokes flow past a sphere](#example-stokes-flow-past-a-sphere)
      - [Biological Motility At Low Reynolds Number](#biological-motility-at-low-reynolds-number)
    - [Thin-Film Approximation](#thin-film-approximation)
    - [Waves](#waves)
      - [Linear Wave Equations](#linear-wave-equations)
      - [Waves and incompressibility](#waves-and-incompressibility)
      - [Non-Linear Waves](#non-linear-waves)
        - [Physics](#physics)
  - [Instabilities and Turbulence](#instabilities-and-turbulence)
    - [Some instabilities](#some-instabilities)
      - [Convective Instability (Rayleigh-Bernard)](#convective-instability-rayleigh-bernard)
        - [Rayleigh-Benard convection](#rayleigh-benard-convection)
      - [Rayleigh-Plateau](#rayleigh-plateau)
      - [Rayleigh-Taylor](#rayleigh-taylor)
      - [Kelvin-Helmholtz](#kelvin-helmholtz)
    - [Turbulence](#turbulence)
      - [Kolmogorov Scaling](#kolmogorov-scaling)
- [Dynamical Systems](#dynamical-systems)
  - [Flows in Phase Space](#flows-in-phase-space)
  - [Two Dimensional Phase Space](#two-dimensional-phase-space)
  - [Liouvilles Theorem](#liouvilles-theorem)
  - [Attractors/Fixed Points and Their Stability](#attractorsfixed-points-and-their-stability)
    - [Limit Cycles](#limit-cycles)
    - [Classifying Fixed Points](#classifying-fixed-points)
  - [Bifurcations](#bifurcations)
    - [Saddle Node Bifurcation](#saddle-node-bifurcation)
    - [Transcritical Bifurcation](#transcritical-bifurcation)
    - [Pitchfork Bifurcation](#pitchfork-bifurcation)
      - [Supercritical Pitchfork](#supercritical-pitchfork)
      - [Subcritical Pitchfork](#subcritical-pitchfork)
      - [Imperfect Pitchfork Bifurcation](#imperfect-pitchfork-bifurcation)
    - [Hopf Bifurcations](#hopf-bifurcations)
      - [Supercritical Hopf](#supercritical-hopf)
      - [Subcritical Hopf](#subcritical-hopf)
  - [Aperiodicity and Predictability in Simple Chaotic Systems](#aperiodicity-and-predictability-in-simple-chaotic-systems)
  - [Lyapunov Exponents](#lyapunov-exponents)
  - [The Lorenz attractor](#the-lorenz-attractor)
    - [Fixed Points and Stability](#fixed-points-and-stability)
    - [The Strange Attractor](#the-strange-attractor)
    - [Lyapanov Exponents](#lyapanov-exponents)
- [Ideal Fluid Examples](#ideal-fluid-examples)
  - [Hydraulic Jumps](#hydraulic-jumps)
  - [Bath Plug Vortex](#bath-plug-vortex)

# Flows
A fluid is a gas or a liquid whose molecules can slide past each other (unlike a solid whose molecules are regularly bound) a gas is compressible whereas a liquid can be considered mostly incompressible.

## Diagrams of flows

### Flow Fields
A useful way to diagram flows is to draw flow fields, or arrows, a good way to do this is to evaluate the arrows on the axis and work from there.

### Streamlines
Another useful way is to draw *streamlines* which are curves in the direction of $\underline{u}$ for any given t. They are defined by 

$$
\frac{dx}{u_x} = \frac{dy}{u_y} = \frac{dz}{u_z} = dt
$$

But are obviously drawn very similarly to flow fields.

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



## Navier Stokes Equation

Let's look for an equation of fluid motion! Before we start though we need to look at some conservation principles.

### Fluxes and Conservation principles

There are two forms of conservation in this topic, **Lagrangian** and **Flux-form** conservation.
+ **Lagrangian conservation** is something like conservation of momentum where we are thinking about particles. In a fluid we use the material derivative and think about fluid particles.
  + $\frac{D\rho}{Dt} = 0$, here $D/Dt$ refers to rate of change w.r.t time following a fluid parcel.
+ **Flux-Form conservation** is conservation in a continuum. A quantity is conserved if it's rate of change and divergence of flux sum to zero, the kind of equation we see a lot.
  + $\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\underline{u})$

#### Conservation of Mass
If mass is conserved we get a simple conservation law:
$$
\frac{\partial\rho}{\partial t} + \nabla\cdot(\rho\underline{u}) = 0 
$$

We can say that if the fluid is incompressible $\rho$ is constant in time and space, which leads to:

> Incompressible $\implies \nabla\cdot\underline{u} = 0$

Liquids generally aren't very compressible so this is a useful condition.

### Derivation of the Formula

Lets think of a small fluid parcel (differential volume $\delta x\delta y\delta z$) and apply some classical mechanics. The force on the parcel is given by Newtons second law.

$$
\delta\underline{F} = \rho(\delta x\delta y\delta z)\underline{a}
$$

The force also can be written as the sum of the three components, 
+ Pressure gradient force
+ Viscous force
+ External Force

#### Pressure Gradient Force

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


#### Viscous Force

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

#### External force

Often the external force to consider is gravity so here the acceleration due to external force can be written as $\underline{a}_{ext} = -\underline{g}$

#### A correction to acceleration

Typically we think of acceleration as $\underline{a} = \frac{d\underline{u}}{dt}$ with $\underline{u}(t)$ but here we have been thinking of fluid parcels so we need to think of following that fluid parcel through space (i.e the *material derivative*) when we calculate $\underline{a}$.
$$
\begin{aligned}
    \frac{d}{dt}\underline{u}(x, y, z, t) &= \frac{\partial\underline{u}}{\partial x}\frac{dx}{dt} + \frac{\partial\underline{u}}{\partial y}\frac{dy}{dt}  + \frac{\partial\underline{u}}{\partial z}\frac{dz}{dt} + \frac{\partial\underline{u}}{\partial t}\\
    \frac{Du}{Dt}=\underline{a} &= \frac{\partial\underline{u}}{\partial t} + (\underline{u}\cdot \nabla)\underline{u}
\end{aligned}
$$

#### Navier Stokes

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

## Special Cases

### Very Viscous Flows

#### Stokes Equations 

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

#### EXAMPLE Stokes flow past a sphere
<!-- TODO: STOKES FLOW PAST A SPHERE LECTURE 7-->
#### Biological Motility At Low Reynolds Number
In viscous flows we have *Purcell's scallop theorem* which states that viscous flows are reversible this means an animal with just one hinge like a scallop will open and close and be in the exact same space. Motion is only possible if movement is non-reciprocal.

### Thin-Film Approximation
<!-- TODO: Thin film approx-->

### Waves

For a wave in a fluid (i.e sound waves) we clearly need it to be *compressible*

#### Linear Wave Equations

The equations for the motion of an inviscid ($\nu=0$) compressible fluid are:

$$
\begin{aligned}
\frac{\partial \rho}{\partial t} + \nabla\cdot(\rho\underline{u}) &= 0\\
\ \\
\rho\bigg(\frac{\partial \underline{u}}{\partial t} + \underline{u} \cdot \nabla\underline{u}\bigg) + \nabla p &= 0\\
\ \\
\bigg(\frac{\partial}{\partial t} + \underline{u}\cdot\nabla\bigg)\frac{p}{\rho^\gamma} &= 0
\end{aligned}
$$

If we suppose we're looking at a small perturbation from the simplest rest solution $\underline{u} = 0, \rho=\rho_0,$ and $p=p_0$. This gives:

$$
\underline{u} = \delta\underline{u}\\
\rho = \rho_0 + \delta\rho\\
p = p_0 + \delta p
$$

We can put these into the equations above to get:

$$
\begin{aligned}
\frac{\partial \delta\rho}{\partial t} + \rho_0\nabla\cdot(\delta\underline{u}) &= 0\\
\ \\
\rho_0\frac{\partial \delta\underline{u}}{\partial t} + \nabla\delta p &= 0\\
\ \\
\frac{\partial}{\partial t}\bigg(\delta p - \gamma\frac{p_0}{\rho_0}\delta\rho\bigg) &= 0
\end{aligned}
$$

If we make another assumption, that $p = p(\rho)$ which is the assumption that equation of state is a function of density from Kinetic Theory we can expand pressure about density:

$$
\nabla\delta p = \frac{\partial p}{\partial \rho}\bigg|_{\rho = \rho_0} \nabla\delta\rho
$$

By taking derivatives of the equations above we can get:

$$
\boxed{
  \frac{\partial^2\delta\rho}{\partial t^2} = c_s^2\nabla^2\delta p,\ \ c_s^2 = \frac{\partial p}{\partial\rho}\bigg|_{\rho=\rho_0}
}
$$

So we have sound waves with a phase velocity $c_s$.

#### Waves and incompressibility

We talk about incompressibility sometimes and waves are a good way to define that condition. We can define the incompressibility condition as:

>Pressure variation due to flow $\ll$ pressure variation due to sound waves $\implies$ incompressible

To formalise this we can use Bernoulli's equation:

$$
\frac{\underline{u}^2}{2} + \frac{p}{\rho} = constant\\
\implies \Delta p \sim u^2\Delta\rho
$$

From above we can find a similar relation for sound waves.

$$
\Delta p \sim c^2\Delta\rho
$$

So for incompressibility we can have

$$
u^2\ll c^2\\
Ma\ll1\\
\text{where } Ma=\frac{u}{c}
$$

#### Non-Linear Waves

Our wave equation derivation looked at small linear perturbations that remain small, Navier Stokes is not linear though and often creates chaotic systems that change quickly! What sort of thing do we get from this?

##### Physics

The speed of sound usually increases with increasing pressure so the collapse of the stable system is due to peaks catching up to troughs

<img src="./Figs/NonLinearWaves.jpg">

Sound waves can't break (peaks overtake troughs) like with water waves as those move in two dimensions and sound waves move only in one. instead a *wave shock* forms

## Instabilities and Turbulence

### Some instabilities

#### Convective Instability (Rayleigh-Bernard)

Think about an incompressible fluid whose density varies with height. If a fluid parcel is moved a small distance $\delta z$ in the vertical it would have a relative difference in density given by

$$
\delta\rho = -\frac{\partial\rho}{\partial z}\delta z
$$
> Note the difference between $\delta$ and $\partial$.

This would mean the acceleration due to buoyancy is...

$$
-\frac{g\delta\rho}{\rho} = \frac{g}{\rho}\frac{\partial\rho}{\partial z}\delta z
$$

If $\partial\rho/\partial z \lt 0$ then the fluid is *stably stratified* a small displacement results in an oscillation of angular frequency... 

$$
\omega = \sqrt{-\frac{g}{\rho}\frac{\partial\rho}{\partial z}}
$$

But if $\partial\rho/\partial z \gt 0$ then the fluid is *unstably stratified* buoyancy force increases the displacement! This is what we call **convective instability**. This can be generalised to a compressible fluid but we have to think about the adiabatic expansion.

Boiling a under a grill is stably stratified and on a hob is unstably stratified.

##### Rayleigh-Benard convection

Rayleigh-Benard convection is 2D convection between two isothermal plates at $z=0,H$ with temperatures $T_0, T_0 - \Delta T$ We get the equations of motion below:

$$
\frac{\partial u}{\partial t} + \bold{u}\cdot\nabla u + \frac{1}{\rho_0}\frac{\partial p}{\partial x} = \nu\nabla^2u,\\
\frac{\partial\omega}{\partial t} + \bold{u}\cdot\nabla\omega + \frac{1}{\rho_0}\frac{\partial p}{\partial z} + g\frac{\rho-\rho_0}{\rho_0} = \nu\nabla^2\omega,\\
\frac{\partial u}{\partial x} + \frac{\partial\omega}{\partial z} = 0,\\
\frac{\partial T}{\partial t} + \bold{u}\cdot\nabla T = \kappa\nabla^2T,\\
\rho = \rho_0[1-\alpha(T-T_0)]
$$

$\kappa$ is thermal diffusivity and  $\alpha$ is the thermal expansion coefficient. The *Boussinesq Approximation* is used here and says that all densities can be replaced with a constant reference value except when used in buoyancy.

The equilibrium solution (no convection is)

$$
T_{eq} = T_0 - \frac{z}{H}\Delta T,\ \ u_{eq} = \omega_{eq} = 0,\ \ p_{eq}(z) = p_0 - \frac{\rho_0g\alpha\Delta Tz^2}{2H}
$$

Next we would expand around this solution for a general linear solution but I'm not made of time so I won't do that.

The instability is controlled by a dimensionless parameter Ra called the *Reyleigh Number*. We can get an expression for this number by thinking about scaling arguments, if $\alpha=-\frac{1}{\rho_0}\frac{dp}{dT}$ and the length scale is $H$ then for a spherical fluid element of radius $r_0$:

+ The thermal relaxation time $\tau_Q$ can be approximated by the heat diffusion equation
$$
\kappa\nabla^2T = \frac{\partial T}{\partial t} \rightarrow \tau_Q\sim\frac{r_0^2}{\kappa}
$$
+ The distance moved over this time is
$$
\delta z \sim u_0\tau_Q
$$
+ The difference in temperature between the fluid particle and the rest of the fluid is
$$
\delta T = \frac{\partial T}{\partial z}\delta z \sim \frac{\Delta T}{H}u_0\tau_Q
$$
+ The corresponding difference in density is
$$
\delta\rho = \frac{\partial\rho}{\partial T}\delta T \sim \rho_0\alpha\frac{\Delta T}{H}\frac{u_0r_0^2}{\kappa}
$$
+ This gives an upthrust of
$$
\text{Upthrust} \sim \delta\rho Vg \sim \rho_0 g\alpha\frac{\Delta T}{H}\frac{u_0r_0^5}{\kappa}
$$
+ The upthrust must be balanced by stokes drag which is
$$
D \sim \nu r_0 u_0 \sim \rho_0\nu r_0 u_0
$$

For Rayleigh-Benard convection we need buoyancy force to be more than stokes drag so...

$$
\text{Ra} = \frac{\alpha \Delta T gd^3}{\kappa\nu} \gt \bigg(\frac{d}{r_0}\bigg)^4 = \text{Ra}_\text{crit}
$$

Experimentally $\text{Ra}_\text{crit} \sim 1708$ so there. The Rayleigh number is a measure of convective energy transport.

Actually there is a second non dimensional parameter the *Prandtl Number* this is given by $Pr = \frac{\nu}{\kappa}$. The prandtl number measures relative importance of molecular diffusion of momentum and heat. High $Pr$ means the fluid is viscous and unlikely to form convective rolls.

#### Rayleigh-Plateau

This instability explains why a falling stream of liquid breaks up into droplets and dew forms droplets instead of coating a surface.

<img src="./Figs/Rayleigh-Plateau.jpg"/>

It's due to one wavenumber of the normal modes of oscillations on the surface dominating over the others.

#### Rayleigh-Taylor

For two surfaces of different densities gravity is fighting with surface tension for how they move. For small wavelengths tension wins and a Rayleigh-Taylor instability occurs.

<img src="./Figs/Rayleigh-Taylor.gif"/>

#### Kelvin-Helmholtz

This occurs at the interface between two fluids or sheer across fluids and is tied to momentum transfer. Think wind over the surface of the sea.

<img src="./Figs/Kelvin-Helmholtz.gif"/>

### Turbulence

What is turbulence? There is not a complete theory of turbulence but it can be described by a few qualities:
+ Deterministic Chaos, described by N-S but in a way we can't quite understand.
+ Tied to thermal fluctuations as there is a sensitive dependence on initial conditions.
+ Velocity and vorticity fluctuate in an unpredictable but correlated way (not random)

#### Kolmogorov Scaling

Kolmogorov provides a useful scaling argument for turbulence approximately matches the experiment. Kolmogorov described turbulence in terms of an *energy cascade* energy injected into the system first goes to the largest vortex and then the next largest down to the smallest with no dissipation. Energy is only dissipated by viscosity at the scale of the smallest vortexes. For this scaling argument let:

+ $\epsilon$ be the rate of energy per unit mass flowing down the cascade.
+ $l$ be the characteristic vortex size.
+ $v_l$ be the velocity of vortices of size $l$
+ $\implies v_l^2$ is energy per unit mass of a vortex.

We can use dimensional analysis to say

$$
\epsilon \sim \frac{v^3_l}{l}=\frac{v_l^2}{(l/v_l)}
$$

The range over $l$ which this works (the *inertial subrange*) is bounded by the length scale at which $\epsilon$ is injected above and the length scale at which dissipation starts to happen below.

Let $\xi$ be the vortex size where dissipation begins to become important. This is where rate of energy flow is comparable to rate of energy dissipation.

$$
\begin{aligned}
\text{Rate of energy flow}&\sim\text{Rate of energy dissipation}\\
\epsilon\sim\frac{v_\xi^3}{\xi}&\sim\nu\frac{v_\xi^2}{\xi^2}
\end{aligned}
$$
Our dissipation value is because we expect it to be proportional to $\nu$ and the rest is just dimensional analysis. This comes together to give...
$$
\xi \sim \nu^{3/4}\epsilon^{-1/4}\\
v_\xi \sim (\nu\epsilon)^{1/4}
$$

We would expect these to give $Re=1$ and they do! So it's all working great!

<img src="./Figs/Kolmogorov.jpg"/>

The figure above shows the *energy cascade* across this length scale (these are log scales of both). Note that in the diagram $E\sim k^{-5/3}$ this can be explained with Kolomorogov reasoning...
+ $E(k)$ can't depend on $l$ as that doesn't allow energy to flow.
+ $E(k)$ can't depend on $\nu$ because there isn't any dissipation in the inertial range.
+ $\implies E(k)$ can only depend on $\epsilon$ and $k$. 

By dimensional analysis we get...
$$
E(k) \sim \epsilon^{2/3} \times k^{-5/3}
$$


# Dynamical Systems
A dynamical system is a set of equations which describe the time dependence of a point in geometric space. It is typically expressed as a set of differential equations applied to a vector for the state.

## Flows in Phase Space
Even when a system can be solved analytically to give $t(x)$ or $x(t)$ it is sometimes easier to visualise it's behavior in *phase space*. This is a plot of $\dot{x}$ by $x$ and can give a better understanding of the stability of the system. Points where $\dot{x} = 0$ are fixed points.

The example provided in the notes (David Marshall Lecture 10) is this
$$
\dot{x} = \sin x
$$

This gives:

$$
t = \ln\bigg(\frac{\sin x}{1+\cos x}\bigg) + C
$$

Which is a mess to follow but if we look at the phase diagram:

<img src="./Figs/PhaseEx.jpg"/>

It is clear from this where the fixed points are and which initial $x$ values will move in the $\pm$ directions. Phase diagrams only grow more useful as we look at more complicated examples.

Typically a fixed point is called an "attractor"


## Two Dimensional Phase Space

It is useful to represent two dimensional equations as a vector equation like so:

$$
\dot{\underline{x}} = \bold{A}\underline{x}
$$

This allows us to diagonalise the matrix to understand it the flow better.

## Liouvilles Theorem
<!-- TODO understand Liouvilles Theorem-->
Louivilles theorem states that for a hamiltonian:

$$
\sum^n_{i=1}\bigg(\frac{\partial \dot{p}_i}{\partial p} + \frac{\partial \dot{q}_i}{\partial q_i}\bigg) = 0
$$

Subbing into the continuity equation for phase space
$$
\frac{D}{Dt}\delta V = \delta V \sum_{i=1}^n\frac{\partial\dot{x}_i}{\partial x}
$$

We get

$$
\frac{D}{Dt}\delta V = 0
$$

So volume is conserved by elements moving in phase space so a Hamiltonian system can never conserve on an attractor i.e a system with no dissipation.

## Attractors/Fixed Points and Their Stability

Imagine we had a fixed point $\underline{r}_0$ and we wanted to know it's stability. The best thing to do is to look at what we get at small displacements from that fixed point. We can write this as $\underline{r} = \underline{r}_0 + \delta\underline{r}$ and then we can expand the equation $\underline{\dot{r}} = f(\underline{r})$

$$
\underline{\dot{r}} = \delta\underline{\dot{r}}= f(\underline{r}_0 + \delta\underline{r}) \approx \frac{\partial f}{\partial \underline{r}}\bigg|_{\underline{r}=\underline{r_0}}\cdot\delta\underline{r} = + ...
$$

This results in
$$
\delta\dot{\underline{r}} = \mathcal{J}\delta\underline{r}
$$

where $\mathcal{J}$ is the Jacobian matrix the two dimensional example is below.

$$
\mathcal{J} =
\begin{pmatrix}
  \frac{\partial\dot{x}}{\partial x} & \frac{\partial \dot{x}}{\partial y}\\
  \frac{\partial\dot{y}}{\partial x} & \frac{\partial \dot{y}}{\partial y} 
\end{pmatrix}
$$

We can then diagonalise $\mathcal{J}$ to eigenvalues $\lambda_1$ and $\lambda_2$ and their values allow us to classify any fixed point.

### Limit Cycles

Limit cycles are fixed orbits, almost like a fixed point but not quite, an example system would be

$$
\dot{r} = r(1-r^3)\\
\dot{\theta} = 1
$$

Which looks like this:

<img src="./Figs/LimitCycles.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="90%"/>

You can have stable and unstable limit cycles.

<img src="./Figs/LimitCycles2.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="90%"/>

### Classifying Fixed Points

+ $\lambda_1, \lambda_2$ real and positive $\rightarrow$ unstable node
+ $\lambda_1, \lambda_2$ real and negative $\rightarrow$ unstable node
+ $\lambda_1, \lambda_2$ real with opposite signs $\rightarrow$ saddle node
+ $\lambda_1, \lambda_2$ purely imaginary $\rightarrow$ stable orbit
+ $\lambda_1, \lambda_2$ complex with positive real parts $\rightarrow$ unstable spiral
+ $\lambda_1, \lambda_2$ complex with negative real parts $\rightarrow$ stable spiral

<img src="./Figs/Classification.jpg">

## Bifurcations

Bifurcations happen when varying a parameter has a large change on the behaviour of the system. It is easier to look at some examples of specific Bifurcations. We will take each system and create a Bifurcation diagram where we draw fixed points curves on an $x$ by $r$ plot

### Saddle Node Bifurcation

$$
\dot{x} = r - x^2
$$

Clearly has stable points only at $x_0 = \pm\sqrt{r}$ so at the boundary $r=0$ behaviour drastically changes! Let's look at the bifurcation diagram.

<img src="./Figs/Bifurcation1.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="50%"/>

We can look at the arrows to see that one of the nodes is stable and the other is not.

### Transcritical Bifurcation

In this example there is always a fixed point but their stabilities are exchanged with one another. A general form of this is:

$$
\dot{x} = rx - x^2
$$

Whose bifurcation diagram looks like this:

<img src="./Figs/Bifurcation2.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="50%"/>

### Pitchfork Bifurcation

The pitchfork bifurcation is one where one fixed point splits into three (like a pitchfork)

#### Supercritical Pitchfork

Here a stable fixed point becomes unstable

$$
\dot{x} = rx - x^3
$$

Which gives fixed points at $x_0=0,\ x_0\pm\sqrt{r}$ for $r>0$ which we'll see below.

#### Subcritical Pitchfork

The subcritical pitchfork is the opposite here a two unstable fixed points 'collide' with a stable fixed point and annihilate each other. It typically looks like:

$$
\dot{x} = rx + x^3
$$

It has fixed points at $x_0=0,\ x_0\pm\sqrt{-r}$ for $r<0$.

<img src="./Figs/Bifurcation3.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="90%"/>

This isn't very physical as $\dot{x}$ tends to infinity at large x which is some big bangish infinite energy bullshit. We can fix it with an extra term and get some hysteresis as we vary $r$.

$$
\dot{x} = rx + x^3 - x^5
$$

<img src="./Figs/Bifurcation4.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="50%"/>

Here the red line shows the hysteresis behaviour as we vary $r$

#### Imperfect Pitchfork Bifurcation

There's an even weirder pitchfork bifurcation created by adding a small imperfection parameter $\epsilon$.

$$
\dot{x} = \epsilon + rx - x^3
$$

This is a more difficult stability diagram to draw. If we start by assuming x is small then the stationary point equation becomes:

$$
0 = \epsilon + rx - x^3 \sim \epsilon + rx \rightarrow x \sim -\frac{\epsilon}{r}
$$

Here we've used $x^3\ll rx$ meaning $x\ll \sqrt{r}$ or $r\gg\epsilon^{2/3}$ so in that region we have the curve $x=-\epsilon/r$, also we know that for large $x$ and $r$ the curve tends towards the pitchfork. This gives the stability diagram below:

<img src="./Figs/Bifurcation5.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="50%"/>

If we want to look at how the graph changes with $\epsilon$ we need to look at intersections between $f(x) = rx-x^3$ and $g(x)=-\epsilon$. We can look at the critical point $\epsilon_c$ where the number of fixed points goes from $3$ to $1$ it will occur at the minimum of $f(x)$.

### Hopf Bifurcations

These are bifurcations which can lead to oscillations. 
#### Supercritical Hopf

There is the supercritical hopf where a stable spiral becomes am unstable spiral, which can go into a limit cycle.

<img src="./Figs/Hopf1.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="90%"/>

#### Subcritical Hopf

This is the reverse, we get an unstable spiral which turns into a stable fixed point and unstable limit cycle.

<img src="./Figs/Hopf2.jpg" style='display: block;margin-left: auto;margin-right: auto;' width="90%"/>


## Aperiodicity and Predictability in Simple Chaotic Systems

The Lorenz attractor is an example of deterministic chaos (one of many in fluids). Deterministic chaotic systems are typically 
+ **Aperiodic in the long term** - don't settle into a fixed point or periodic orbit but may still be confined into a fixed region of space
+ **Sensitive to initial conditions** - small changes in initial conditions will cause large changes in the future.
+ **Deterministic** - There is no randomness or stochasticity, the weirdness comes from the non-linear equations of motion. 

Toby sums it up by quoting Edward Lorenz himself:

> Chaos : When the present determines the future but the approximate present doesn't approximately determine the future. 


## Lyapunov Exponents

Sometimes it is useful to look at how volumes expand or contract (like we did with the strange attractor) we can do this with Lyapunov Exponents here it their derivation:

$$
\delta\dot{\underline{x}} \approx J\delta\underline{x}
$$

This means

$$
\frac{D}{Dt}||\delta x||^2 = \frac{D}{Dt}(\delta\underline{x}^T\delta\underline{x}) = \delta\underline{\dot{x}}^T\delta\underline{x} + \delta\underline{x}^T\delta\underline{\dot{x}} \approx \delta\underline{x}^T(J+J^T)\delta\underline{x}
$$

So if $\delta\underline{x}$ is aligned to the eigenfunctions of $(J+J^T)/2$ with eigenvalue $\lambda_i$ then:

$$
\frac{D}{Dt}||\delta\underline{x}||^2 = 2\lambda_i||\delta\underline{x}||^2
\implies ||\delta\underline{x}|| \approx ||\delta\underline{x}||_0e^{\lambda_i t}
$$

The result is only relevant for short times as it ignores $O(\delta\underline{x}^2)$ terms. The eigenvalues are real as $(J+J^T)/2$ is a symmetric matrix. The eigenvalues $\lambda_i$ are called the local Lyapunov Exponents, if they are large and positive then the system diverges along that eigenvector, large and negative means the system flattens along that vector and small ones mean oscillations can occur.

## The Lorenz attractor

The lorenz system was intended to be a model of Rayleigh-Benard convection (remember that from earlier!) but in a box. It has the equations...

$$
\begin{aligned}
\dot{x} &= \sigma(y - x)\\
\dot{y} &= rx - y - xz\\
\dot{z} &= xy - bz
\end{aligned}
$$

Here $r$ is the Rayleigh number, $\sigma$ is the Prandtl number, and $b$ is the aspect ratio of the box. $x$ is proportional to the strength of the convective moment, $y$ is proportional to the temperature difference between the ascending and descending currents, and $z$ is proportional to the distortion of the vertical temperature profile from linearity. Basically it is a model of Rayleigh convection but not a direct and easy to follow one! Let's analyse it anyway.

### Fixed Points and Stability

Our fixed points are given by

$$
x - y = 0\\
x(r-1-z) = 0\\
x^2 - bz = 0
$$

Which gives fixed points at...

$$
\bold{r}_1 = (0, 0, 0),\ \ \bold{r}_{2/3} = (\pm\sqrt{b(r-1)},\pm\sqrt{b(r-1)},r-1)
$$

We also have the Jacobian:
$$
J = 
\begin{pmatrix}
  -\sigma & \sigma  & 0\\
  r-z     & -1      & -x\\
  y       &  x      & -b
\end{pmatrix}
$$

For $\bold{r}_1$ the eigenvalues are 
$$
lambda = -\frac{1}{2}(1+\sigma) \pm \frac{1}{2}\sqrt{1-(2-4r)\sigma + \sigma^2},\ \ \lambda -b
$$

The $-b$ one shows trajectories converging always to $z=0$ The other set shows the point is stable for $r < 1$ and unstable for $r > 1$. Although it takes a bit more work we can show this is a supercritical pitchfork bifurcation. The whole system starts to look like this:

<img src="./Figs/Strange.jpg"/>

Notice the whole system becomes unstable at $r>r_H$ however they don't get kicked off into infinity they behave like a strange attractor!

### The Strange Attractor

The strange attractor is a very weird concept, it is a chaotic local system but is globally confined and results from the application of the continuity equation for phase space:

$$
\frac{\delta\dot{V}}{\delta V} = \frac{\partial\dot{x}}{\partial{x}} + \frac{\partial\dot{y}}{\partial{y}} + \frac{\partial\dot{z}}{\partial{z}} = -C
$$

Where C is positive (in the case of the Lorenz Attractor $C = \sigma + 1 + b$). This means volumes collapse to a confined space so even a chaotic system will be confined to a limited volume. For a lorenz attractor becomes very strange in this regime and looks a bit like this...

<img src="./Figs/Strange2.jpg"/>

### Lyapanov Exponents

Let's look at the Lyapanov exponents for this system. We have 
$$
(J + J^T) = \begin{pmatrix}
  -\sigma          & \frac{3}{2}\sigma& 0\\
  \frac{3}{2}\sigma& -1               & 0\\
  0                & 0                & -b
\end{pmatrix}
$$

If we consider this in the regime $r=28, \sigma=10, \text{and } b=8/3$ Then at point $(0,0,r-2\sigma)$ we have the eigenvalues and eigenvectors.

$$
\begin{aligned}
\lambda_1 &= -\frac{8}{3}, &\bold{u}_1 &= (0,0,1)\\
\lambda_2 &= \frac{-11+3\sqrt{109}}{2}, &\bold{u}_2 &= \bigg(\frac{-3+\sqrt{109}}{10},1,0\bigg)\\
\lambda_3 &= \frac{-11+3\sqrt{109}}{2}, &\bold{u}_3 &= \bigg(\frac{-3-\sqrt{109}}{10},1,0\bigg)
\end{aligned}
$$

Which suggests a slow decay in the $z$ axis and fast growth and decay in the $x-y$ plane.

# Ideal Fluid Examples
An ideal fluid is a fluid is inviscid ($\nu = 0$) and of uniform density ($\nabla\rho=0$ and $\nabla\cdot\underline{u}=0$) In this limit we have

$$
\frac{D\Gamma_C}{Dt} = 0
$$

And in two dimensional flow it is irrotational ($D\omega/Dt = 0$)

## Hydraulic Jumps
A hydraulic jumps are produced when a fast moving region encounters a slow moving region. The result is a rising water level sort of like a water traffic jam. I'm not sure how much we're meant to know since it's in none of the notes.


## Bath Plug Vortex

<!-- TODO: IDEAL FLUID EXAMPLE LECTURE 5 or 6 @20m-->



