# B4 Subatomic Physics <!-- omit in toc -->

- [Scattering](#scattering)
  - [Classical Scattering](#classical-scattering)
    - [Hard ball scattering.](#hard-ball-scattering)
    - [Classical Rutherford Scattering](#classical-rutherford-scattering)
  - [Quantum Mechanical Scattering](#quantum-mechanical-scattering)
    - [Time Dependant Perturbation Theory Recap...](#time-dependant-perturbation-theory-recap)
    - [A Perturbation for Scattering Theory](#a-perturbation-for-scattering-theory)
    - [A quantum rate equation](#a-quantum-rate-equation)
    - [The Born Approximation](#the-born-approximation)
    - [Second order perturbation](#second-order-perturbation)
    - [Validity of perturbation theory here](#validity-of-perturbation-theory-here)
  - [Application of first order scattering theory](#application-of-first-order-scattering-theory)
    - [The Yukawa Potential](#the-yukawa-potential)
    - [Virtual exchange particles](#virtual-exchange-particles)
  - [Feynman Diagrams and Feynman's Rules](#feynman-diagrams-and-feynmans-rules)
    - [Yukawa Potential Example](#yukawa-potential-example)
    - [More complicated example](#more-complicated-example)
  - [Resonances](#resonances)
    - [Decays](#decays)
    - [Resonance Scattering](#resonance-scattering)

# Scattering

We can learn a lot about the structure of a material by firing a bunch of particles at it and seeing how they scatter. If the rate of particles reaching a detector at a given solid angle is $n(\theta, \phi)$ and the incoming flux is $j_A$ we define the differential cross section as the ratio between the two...

$$
\frac{d\sigma}{d\Omega} = \frac{n}{j_A} = \frac{\text{Particles per solid angle}}{\text{Incoming flux}} 
$$

The scattering cross section $\sigma$

$$
\sigma = \int\frac{d\sigma}{d\Omega}d\Omega
$$

Represents the 'effective area' of the target in the scattering process.

## Classical Scattering

This is not on the syllabus so I'm going to leave the derivation to be read in the notes. One important result is...
$$
nd\Omega = n\sin\theta d\theta d\phi = j_Abdbd\phi
$$
Here are the results.

### Hard ball scattering.

For a hard sphere of potential...

$$
V(r) = 
\begin{cases}
\begin{aligned}
    0 \text{ for } r>R\\
    \infty \text{ for }r\leq R
\end{aligned}
\end{cases}
$$

We end up with
$$
\frac{d\sigma}{d\Omega}=\frac{R^2}{4}
$$

### Classical Rutherford Scattering

For a coulomb potential given by...
$$
V(r) = \frac{Z_1Z_2e^2}{4\pi\epsilon_0r}
$$

we end up with...

$$
\frac{d\sigma}{d\Omega} = \bigg(\frac{Z_1Z_2e^2}{4\pi\epsilon_0T}\bigg)^2\frac{1}{16\sin^4(\theta/2)}
$$

Where $T$ is the KE of the particle.

## Quantum Mechanical Scattering
### Time Dependant Perturbation Theory Recap...
For first order perturbation theory the probability that we go from initial state $|i\big>$ to final state $|f\big>$ when there is a hamiltonian $H = H_0 + \Delta H(t)$ is...

$$
P^{(1)}_{i\rightarrow f} = \frac{1}{\hbar^2}\bigg|\int^t_{t_0}\big<f|\Delta H|i\big>e^{i(E_f-E_i)t^\prime/\hbar}dt^\prime\bigg|^2
$$

### A Perturbation for Scattering Theory

For scattering theory we need some perturbation depending on the position of the particle $\bold{r}$ to use time dependant perturbation theory though it needs to be time dependant but this makes sense if we think about the fact that the potential only begins to affect the particle as it comes closer so we can make a perturbation $\Delta H(t) = e^{\epsilon t}\Delta H_0$. Which has a term to take into account the fact there is a perturbation which slowly appears from time $t=-\infty$. In out integral now we simply need to integrate from $-\infty$ to some time t. We get...

$$
P^{(1)}_{i\rightarrow f} = |\big<f|\Delta H_0|i\big>|^2\frac{e^{2\epsilon t}}{(E_f-E_i)^2+(\epsilon\hbar)^2}
$$

This is still a probability density function as we only have it for one specific state f. If we define the density of final states $\rho(E_f)$. This gives a probability of transition...

$$
P^{(1)} = \int|\big<f|\Delta H_0|i\big>|^2\frac{e^{2\epsilon t}}{(E_f-E_i)^2+(\epsilon\hbar)^2}\rho(E_f)dE_f
$$

and a rate of transitioning known as **Fermis golden rule**
$$
R^{(1)} = \int|\big<f|\Delta H_0|i\big>|^2\frac{2\epsilon e^{2\epsilon t}}{(E_f-E_i)^2+(\epsilon\hbar)^2}\rho(E_f)dE_f
$$

Our calling this a time dependant perturbation was a bit sneaky though as the potential of the target is probably steady. We can still use the maths though so long as we now let $\epsilon\rightarrow0$. If we take the part with $\epsilon$ in it and find the limit...

$$
\lim_{\epsilon\rightarrow0}\frac{2\epsilon}{(E_f-E_i)^2+(\epsilon\hbar)^2} = \frac{2\pi}{\hbar}\delta(E_f-E_i)
$$

So we have...

$$
R^{(1)} = \frac{2\pi}{\hbar}|\big<f|\Delta H_0|i\big>|^2\rho(E)
$$

Where $E_i=E_f=E$ (This rate equation is Fermi's golden rule).

Finally we might want to get some specific answer for $\rho(E)$ this is simply the density of energy states states. The derivation is the same as always so here it is just to knock it into my head one more time...

$$
\rho(k) = \frac{dN}{dk} = \frac{Vk^2d\Omega}{(2\pi)^3}\\\ \\
E = \frac{\hbar^2k^2}{2m}\\\ \\
\rho(E) = \frac{dN}{dE} = \frac{dN}{dk}\frac{dk}{dE} = \frac{Vk^2d\Omega}{(2\pi)^3}\frac{m}{\hbar^2k}
$$

### A quantum rate equation

We have this rate equation but we still don't have a differential cross section! Remember differential cross section is defined as
$$
\frac{d\sigma}{d\Omega}=\frac{\text{Particles per solid angle}}{\text{Incoming flux}}
$$

We can say that
$$
\text{Partilces per solid angle} = \frac{R}{d\Omega}
$$
and
$$
\text{Incoming flux} = \frac{j}{V} = \frac{\hbar k}{Vm}
$$

Where $j$ is probability current for a plane wave.

This gives the final expression...

$$
\frac{d\sigma}{d\Omega}^{(1)} = \frac{m^2}{(2\pi\hbar^2)^2}V^2|\big<f|\Delta H_0|i\big>|^2
$$

### The Born Approximation

Finally we need to evaluate the matrix element. Let's define our initial and final states in terms of momentum. $|i\big> = V^{-1/2}|\bold{k}\big>$ and $|f\big> = V^{-1/2}|\bold{k}^\prime\big>$ where $V^{-1/2}$ is a normalization. So our differential cross section to first order perturbation theory is given by...
$$
\frac{d\sigma}{d\Omega}^{(1)}=\bigg(\frac{m}{2\pi\hbar^2}\bigg)^2\bigg|\int e^{i\bold{q}\cdot\bold{r}}\Delta H_0(\bold{r})d^3\bold{r}\bigg|^2
$$

So the differential cross section is approximately a fourier transform of the target perturbation. This result is often called the Born approximation.

### Second order perturbation

Since this is only first order perturbation theory we need to turn to higher orders if we get a small result. This is off syllabus but basically we end up with a *propogator factor* which behaves as if there is some intermediate between state which feels no need to conserve energy but which quickly decays into a state which does. This is where the idea of virtual particles comes from.

### Validity of perturbation theory here

The perturbation theory approach is only valid if $\Delta H_0$ is much smaller than the energy of the incoming particle. To get a value on this let's use a step function for $\Delta H$. Where it is given by...

$$
\Delta H  = 
\begin{cases}
\begin{aligned}
  &\Delta H_0\ &0\le t^\prime \le t\\
  &0 &\text{otherwise}
\end{aligned}
\end{cases}
$$
We end up getting...

$$
P_{i\rightarrow f} = \frac{|\big<f|\Delta H_0|i\big>|^2}{\hbar^2}t^2
$$

Which gives us the condition for a small perturbation that...

$$
\big<f|\Delta H_0|i\big>\llless\frac{\hbar}{t}
$$

$t$ is the approximate time to traverse an atom so lets say...

$$
t\approx\frac{a}{v} = \frac{am}{\hbar k}\\
\implies \big<f|\Delta H_0|i\big> = \frac{\hbar^2k}{am}
$$

## Application of first order scattering theory

Our matrix element can be simplified if we remember that basically every potential we see would be central and can be evaluated in polar coordinates...

$$
\Delta H(\bold{r}) = \Delta H(r)\\\ \\
\begin{aligned}
\implies \big<k^\prime|\Delta H|k\big> &= \iiint\Delta H(r)e^{iqr\cos\theta}r^2drdcos\theta d\phi\\\ \\
&=\frac{4\pi}{q}\int^\infty_0r\Delta H(r)\sin qr\ dr
\end{aligned}
$$

### The Yukawa Potential

The Yukawa potential is a more realistic 'screened' Coulomb potential.

$$
V(r) = V_0\frac{e^{-\mu r}}{r}
$$

Evaluating the matrix element in polar coordinates we get...

$$
\big<k^\prime|\Delta H|k\big> = \int^\infty_0 e^{-\mu r}\sin{qr}\ dr =  \frac{4\pi V_0}{q^2+\mu^2}
$$

Which gives a differential cross-section.

$$
\frac{d\sigma}{d\Omega}^{(1)} = \bigg(\frac{2mV_0}{\hbar^2}\bigg)^2\frac{1}{[2k^2(1-\cos\theta)+\mu^2]}
$$
and the cross-section

$$
\sigma^{(1)} = \bigg(\frac{2mV_0}{\hbar^2}\bigg)^2\frac{4\pi}{4k^2\mu^2+\mu^4}
$$

Note if we let $\mu\rightarrow0$ we get coulomb scattering again!

### Virtual exchange particles

Previously in Yukawa potential we had the matrix element

$$
\big<k^\prime|\Delta H|k\big> =  \frac{4\pi V_0}{q^2+\mu^2}
$$

Apparently our lecturer is tempted to call this a product of an interaction strength $\sqrt{4\pi V_0}^2$ and a propagator $1/(q^2+\mu^2)$. For propagators to work they need to have an associated Green's function. Luckily this one does!! It's the greens function the the Klein-Gordon equation...
$$
\Box\psi(\bold{r},t) + \frac{m^2c^2}{\hbar^2}\psi(\bold{r},t) = 0
$$

This was an early attempt at making a relativistic quantum physics equation. It was thrown out for allowing negative probability density (which is now accepted as being due to the possibility of an anti particle solution) but also more seriously breaking down for spin-1/2 particles which is a big deal because that makes up most matter. Luckily this course only needs spin-0 particles so it's cool. The complete Green's function is...

$$
G(P) = \frac{-1}{\frac{P\cdot P}{\hbar^2}-\mu^2}
$$

For a yukawa potential we have $m=\frac{\hbar\mu}{c}$ and clearly $P\cdot P = \frac{E^2}{c^2}-p^2=\frac{\Delta E^2}{c^2}-p^2$ which gives the propagator for the yukawa potential given $\Delta E = 0$.

<div style="text-align:center">
<img src="./Figs/Yukawa.jpg">
</div>

## Feynman Diagrams and Feynman's Rules

To get better at dealing with scattering we need to
+ Deal better with relativistic effects
+ Lift the restriction on elastic processes (like particle creation and annihilation)

To do this we need to use propagators which are the Green's fuction of the Dirac equation and the second needs describing particles in terms of fields basically it's Quantum Field Theory. This is a bit beyond syllabus so we'll use feynman diagrams as a simplification.

+ Each scattering process is represented as a series of diagrams with each diagram representing a term in the perturbation series. (I.e higher order perturbations)
+ The diagrams contain propagators and vertices.
+ The more vertices the higher the order.
+ The higher the order the lower the contribution so we can stop at some point in the series.
+ Particles are lines with an arrow forward in time, antiparticles are lines with an arrow pointing backward in time.
+ External legs (incoming and outgoing have well defined 4-Momenta)
+ 4-momentum is conserved at vertices (as well as charge e.c.t)
+ We can use perturbation theory to calculate a rate for a given process in the diagram. By calculating a matrix element and a density of states. This can be done with Feynman's rules:
  - The vertex factor g describes the strength of the interaction. It is proportional to the strength of the force and the charge of the particle. In QED these are $g_{EM}=\sqrt{4\pi\alpha_{EM}}=e/\sqrt{\epsilon_0\hbar c}$
  - We'll say the propagator is the same as for the Yukawa potential from earlier for this course $\frac{1}{P\cdot P-m^2c^2}$
  - For SI units we need to include a factor $\hbar^3c$
  - The first order perturbation matrix element is then the product of the vertex factors and the initial propagator. The rate/cross section is proportional to it's square. 

### Yukawa Potential Example

Let's try it for the Yukawa potential...

$$
\underbrace{\hbar^3c}_\text{Unit factor} \times \underbrace{g^2}_\text{Vertex Factors} \times \overbrace{\frac{1}{p^2+m^2c^2}}^\text{Propagator} \\\ \\
\begin{aligned}
&= \hbar^3c\frac{e^2}{\epsilon_0\hbar c}\frac{1}{\hbar^2q^2+\mu^2\hbar^2}\\\ \\
&= \frac{4\pi}{q^2 + \mu^2}\frac{e^2}{4\pi\epsilon_0}\\\ \\
&= \frac{4\pi V_0}{q^2+\mu^2} &\text{as before}
\end{aligned}
$$

Note there are two vertices as a more accurate diagram is...

<div style="text-align:center">
<img src="./Figs/Yukawa2.jpg" height=200>
</div>

### More complicated example

Let's take the example of $e^- + e^+ \rightarrow \mu^- + \mu^+$:

<div style="text-align:center">
<img src="./Figs/FeynmanEx.jpg">
</div>

The four momentum of the photon is given by

$$
Q = P_1+P_2
$$

Which we can evaluate in the center of momentum frame where

$$
\begin{aligned}
P_1 &= (E_e/c, \bold{p})\\
P_2 &= (E_e/c, -\bold{p})\\
\implies Q &= (2E_e/c, 0)
\end{aligned}
$$

Since the mass of the photon $m=0$ we have the propogator...

$$
\frac{1}{Q^2-m^2c^2} = \frac{c^2}{4E_e^2}
$$

Putting this together with the vertex factors we get...

$$
|M_{if}|^2 = \bigg|\frac{\hbar^3c^3g^2_{EM}}{4E_e^2}\bigg|^2
$$

The matrix element has dimensions $Jm^3$ though which is sad because it should clearly be $J$ as the matrix is a perturbation to the Hamiltonian. We can fix this with a $V^{-1}$ term. This can be thought of as a normalisation and will disappear later anyway.

$$
|M_{if}|^2 = \bigg|\frac{\hbar^3c^3g^2_{EM}}{4E_e^2}\bigg|^2\frac{1}{V^2}
$$

Using Fermi's Golden Rule...

$$
R_{i\rightarrow f}=\frac{2\pi}{\hbar}|M_{if}|^2\rho(E)
$$

To get a cross section we need to divide by the flux of incoming particles which is given by.. $j = 2v_e/V = 2c^2p_e/E_eV$ (the factor of two is for the two beams)

$$
\sigma = \frac{VE_e}{2c^2p_e}\frac{2\pi}{\hbar}|M_{if}|^2\rho(E)
$$
But the density of states can be found as..
$$
\rho(E) = \frac{dN}{dp_\mu}\frac{dp_\mu}{dE}\\\ \\
\frac{dN}{dp_\mu} = \frac{4\pi V p^2_\mu}{(2\pi\hbar)^3}\\\ \\
E_\mu^2 = p_\mu^2c^2+m_\mu^2c^4\\\ \\
E_\mu dE_\mu = c^2p_\mu dp_\mu\\\ \\
\frac{dp_\mu}{dE}=\frac{1}{2}\frac{dp_\mu}{dE_mu} = \frac{1}{2}\frac{E_\mu}{c^2p_\mu}
$$

Putting it all together we get the monster that is...

$$
\begin{aligned}
\sigma &= \underbrace{\frac{VE_e}{2c^2p_e}\frac{2\pi}{\hbar}}_\text{Coefficent in fermis rule}\times\ \ \ \underbrace{\bigg(\frac{\hbar^3c^3g^2_{EM}}{4E_e^2}\bigg)^2\frac{1}{V^2}}_\text{Matrix element} \times \underbrace{\frac{4\pi V p^2_\mu}{(2\pi\hbar)^3}\frac{1}{2}\frac{E_\mu}{c^2p_\mu}}_\text{Density of states in energy}\\\ \\
&= \pi\hbar^2\frac{\alpha_{EM}}{s}\\\ \\
\alpha_{EM} &= \frac{g^2_{EM}}{4\pi}\\\ \\
s &= \frac{4E_e^2}{c^2}
\end{aligned}
$$

Where we have used conservation of energy to say that $E_e=E_\mu$. This doesn't take into account spin but when we do we get the result that...
$$
\sigma = \frac{4\pi}{3}\hbar^2\frac{\alpha^2_{EM}}{s}
$$

Which matches experiment pretty well for both $e^- + e^+ \rightarrow \mu^- + \mu^+$ and $e^- + e^+ \rightarrow \tau^- + \tau^+$

## Resonances

Currently we've been looking at how originally unpopulated states become populated but how about how an already populated state develops?

### Decays

Imagine we have an unstable state with mean lifetime $\tau$ we can say that the probability to exist at a time $t+dt$ is
$$
P(t+dt) = P(t)\bigg(1-\frac{dt}{\tau}\bigg)
$$

which has the solution

$$
P(t) = P(0)e^{-\frac{t}{\tau}}
$$

This is easy to slot into perturbation theory we just need to say

$$
c_i(t) = e^{-\frac{t}{2\tau}}
$$

We can now look at the final state again!

$$
c^{(1)}_f=-\frac{i}{\hbar}\int^t_0\big<f|\Delta H|i\big>e^{i\big(\frac{E_f-E_i}{\hbar} + \frac{i}{2\tau}\big)t^\prime}dt^\prime
$$

This gives us a complicated transition probability

$$
P_{i\rightarrow f} = |\big<f|\Delta H|i\big>|^2\frac{\bigg|e^{i\big(\frac{E_f-E_i}{\hbar} + \frac{i}{2\tau}\big)t}-1\bigg|^2}{(E_f-E_i)^2+(\frac{\hbar}{2\tau})^2}
$$

Since we have that $t\gg\tau$ we can ignore the exponential and say
$$
P_{i\rightarrow f} = |\big<f|\Delta H|i\big>|^2\frac{1}{(E_f-E_i)^2+(\frac{\hbar}{2\tau})^2}
$$

Which is a lorentzian with width $\Gamma=\frac{\hbar}{\tau}$. If we look at decay into a range of states we get

$$
P = \int |\big<f|\Delta H|i\big>|^2\frac{1}{(E_f-E_i)^2+(\frac{\Gamma}{2})^2}\rho(E_f)dE_f
$$

The rate of decay can be found as

$$
R = \frac{dP}{d\tau} = \frac{2\pi}{\hbar}|\big<f|\Delta H|i\big>|^2\rho(E_f)\\\ \\
\implies \Gamma = \frac{\hbar}{\tau} = \hbar R = 2\pi|\big<f|\Delta H|i\big>|^2\rho(E)
$$

(Where $E_f=E_i=E$) If we have several final states then this decay width will be specific to that state and we have...

$$
\begin{aligned}
\Gamma_f &= 2\pi|\big<f|\Delta H|i\big>|^2\rho(E)\\
\Gamma &= \sum_f\Gamma_f
\end{aligned}
$$

$\Gamma$ is the total width and obeys the $\Gamma=\frac{\hbar}{\tau}$ relationship we had before.

### Resonance Scattering

Now lets consider the generating of an unstable state from a stable initial state. This sort of problem is very common in particle physics where a stable state scatters into an unstable state and the decays into a new stable state. The unstable middle state is called a resonance. To the first order we have that
$$
i\hbar\frac{dc_R^{(1)}(t)}{dt} = \underbrace{\big<R|\Delta H| i\big>e^{i(E_R-E_i)\frac{t}{\hbar}}}_\text{Transition from i to R} - \underbrace{i\bigg(\frac{\Gamma}{2}\bigg)c^{(1)}_R(t)}_\text{Decay of R}
$$

This can be rearranged and integrated to give

$$
\big|c^{(1)}_R(t)\big|^2 = \frac{|\big<R|\Delta H|i\big>|^2}{(E_R-E_i)^2 + \Gamma^2/4}
$$

Since $\Gamma_i = 2\pi|\big<i|\Delta H|R\big>|^2\rho_i(E)$ and  $|\big<R|\Delta H|i\big>|^2=|\big<i|\Delta H|R\big>|^2$ we can write that

$$
\big|c^{(1)}_R(t)\big|^2 = \frac{1}{2\pi\rho_i(E)}\frac{\Gamma_i}{(E_R-E_i)^2+\Gamma^2/4}
$$

To get a rate equation we need to divide this by lifetime so a factor of $\tau^{-1} = \Gamma/\hbar$ is included. If we're looking at a specific final state $|f\big>$ we must reduce by a factor $\Gamma_f/\Gamma$. To get a cross section we divide by the incoming flux $j=\hbar k_i/(\mu V)$ finally if we use the density of state and the dispersion relation $E_i=\hbar^2 k_i^2/(2\mu)$ we get...
$$
\sigma_{i\rightarrow R\rightarrow f} = \frac{\pi}{k_i^2}\frac{\Gamma_i\Gamma_f}{(E_R-E_i)^2 + \Gamma^2/4}
$$

This is the **Briet-Wigner** resonance formula, and it describes how a cross section forms around a resonance. If we want to be a bit more thorough we would use a relativistic version of this but that's only needed for wide resonances. Another correction though is the correction for spin degeneracies which is given below...

$$
\sigma_{i\rightarrow R\rightarrow f} = \frac{\pi}{k_i^2}\frac{2j+1}{(2s_1+1)(2s_2+1)}\frac{\Gamma_i\Gamma_f}{(E_R-E_i)^2 + \Gamma^2/4}
$$

$j$ is the angular momentum of the resonance and $s_1$ and $s_2$ are the spins of the incoming particles. In practice this allows us to find resonances by plotting cross section by energy (no easy experimental feat) and looking for bumps.

<div style="text-align:center">
<img src="./Figs/Resonance.jpg" height=300>
<br/>
An example of identifying a resonant particle
</div>
