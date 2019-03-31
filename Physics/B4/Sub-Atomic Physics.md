# B4 Subatomic Physics <!-- omit in toc -->

- [Scattering](#scattering)
  - [Classical Scattering](#classical-scattering)
    - [Hard ball scattering.](#hard-ball-scattering)
    - [Classical Rutherford Scattering](#classical-rutherford-scattering)
  - [Quantum Mechanical Scattering](#quantum-mechanical-scattering)
    - [The Born Approximation](#the-born-approximation)

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

For quantum mechanical scattering we need to solve the Schrödinger equation...
$$
(H_0 - E)|\psi\big> = -V|\psi\big>
$$

Where $H_0$ is the Hamiltonian for when the scattering potential $V=0$ and $E$ is the corresponding energy.

Let's call $|\phi\big>$ the eigenstate of the hamiltonian $H_0$ which gives the solution...

$$
|\psi\big> = |\phi\big> + \frac{V}{E-H_0\pm i\varepsilon}|\psi\big>
$$

> I'm not really sure how this works but toby seems confident and it gives the right answer so I won't mess with it until I'm sure it's wrong.

The $i\varepsilon$ term is to stop us dividing by zero. We want $\varepsilon \rightarrow 0$ in our final solution.

We can bra through by $\big<\bold{x}|$ and multiply by the identity to get...

$$
\big<\bold{x}|\psi\big> = \big<\bold{x}|\phi\big>+ \int d^3\bold{x}\big<\bold{x}|\frac{1}{E-H_0\pm i\varepsilon}|\bold{x}^\prime\big>V(\bold{x}^\prime)\big<\bold{x}^\prime|\psi\big>
$$

We now just need to find the Greens function...

$$
G_\pm(\bold{x},\bold{x}^\prime) = \big<\bold{x}|\frac{1}{E-H_0\pm i\varepsilon}|\bold{x}^\prime\big>
$$

Using the expression $\big<\bold{x}|\bold{p}\big> = \frac{1}{(2\pi\hbar)^{3/2}}e^{i\bold{x}\cdot\bold{p}/\hbar}$ so we can write our Greens function as an integral in $\bold{p}$. Solving this integral becomes quite involved and uses some complex analysis that I doubt is on syllabus so I'll just write the result.

$$
\big<\bold{x}|\psi\big> = \frac{1}{(2\pi)^{3/2}}\bigg[e^{i\bold{k}\cdot\bold{x}} + \frac{e^{ikr}}{r}f(\bold{k},\bold{k}^\prime)\bigg]\\
f(\bold{k},\bold{k}^\prime) = \frac{-1}{4\pi}(2\pi)^3\frac{2m}{\hbar}\big<\bold{k}^\prime|V|\psi\big>
$$

This is a plane incoming wave and spherical outgoing wave sum so remembering our definition for the differential cross section we can see that...
$$
\frac{d\sigma}{d\Omega} = |f(\bold{k},\bold{k}^\prime)|^2
$$

### The Born Approximation

Under the born approximation we can say that $|\psi\big> \approx |\phi\big>$ This means we can rewrite the state as...

$$
|\psi\big> = |\phi\big> + \frac{V}{E-H_0\pm i\varepsilon}|\phi\big>
$$

And we can rewrite the scattering amplitude $f(\bold{k},\bold{k}^\prime)$ as...

$$
f^{(1)}(\bold{k},\bold{k}^\prime) = -\frac{1}{4\pi}\frac{2m}{\hbar^2}\int d^3\bold{x}^\prime e^{i(\bold{k}-\bold{k}^\prime)\cdot\bold{x}^\prime}V(\bold{x}^\prime)
$$

Which is just the fourier transform of the potential! We can use this approximation when $V(\bold{x})$ is sufficiently small specifically that

$$
|V_0| \llless \frac{\hbar^2 k}{ma}\text{ for }ka\gg1\\\ \\
|V_0| \llless \frac{\hbar^2}{ma^2}\text{ for }ka\lesssim1\\
$$