# B3 Atomic Physics <!-- omit in toc -->
- [Moving on from Hydrogen](#moving-on-from-hydrogen)
  - [Hydrogen, the simple Hamiltonian](#hydrogen-the-simple-hamiltonian)
    - [Energy](#energy)
    - [Angular Momentum](#angular-momentum)
    - [Radial Wavefunctions](#radial-wavefunctions)
  - [A Complicated Hamiltonian](#a-complicated-hamiltonian)
- [The Central Field Approximation](#the-central-field-approximation)
  - [Gross Structure](#gross-structure)
    - [The Central Field](#the-central-field)
    - [Form of the Central Field](#form-of-the-central-field)
    - [Electronic Configurations](#electronic-configurations)
      - [Spectroscopic Notation](#spectroscopic-notation)
      - [Constructing a Periodic table](#constructing-a-periodic-table)
        - [Rare Gases](#rare-gases)
        - [Alkalis](#alkalis)
        - [First Ionisation](#first-ionisation)
    - [Energy of Alkalis, the Quantum Defect](#energy-of-alkalis-the-quantum-defect)
  - [Residual Electrostatic Interaction](#residual-electrostatic-interaction)
    - [A Degenerate Perturbation](#a-degenerate-perturbation)
    - [Symmetry, Antisymmetry and Spin](#symmetry-antisymmetry-and-spin)
  - [Spin Orbit Interaction (Fine Structure)](#spin-orbit-interaction-fine-structure)
    - [The Physics](#the-physics)
    - [Finding the Spin Orbit Correction](#finding-the-spin-orbit-correction)
    - [The B Field due to Orbital Motion](#the-b-field-due-to-orbital-motion)
    - [Finding Our Operator](#finding-our-operator)
    - [Doing the Work](#doing-the-work)
    - [Final Result for Spin Orbit](#final-result-for-spin-orbit)
  - [LS-Coupling](#ls-coupling)
  - [Nuclear Effects](#nuclear-effects)
    - [Hyperfine Structure](#hyperfine-structure)
      - [Finding I](#finding-i)
    - [Mass Effects](#mass-effects)
    - [Field Effects](#field-effects)
  - [External Magnetic Fields](#external-magnetic-fields)
    - [Magnetic Effects in Fine Structure](#magnetic-effects-in-fine-structure)
      - [Weak Field, No Spin, Normal Zeeman Effect](#weak-field-no-spin-normal-zeeman-effect)
      - [Weak Field with Spin Orbit, Anomalous Zeeman](#weak-field-with-spin-orbit-anomalous-zeeman)
      - [Strong Fields, Spin and Orbit, Paschen-Back Effect](#strong-fields-spin-and-orbit-paschen-back-effect)
    - [Magnetic Effects In Hyperfine Structure](#magnetic-effects-in-hyperfine-structure)
      - [Weak Field](#weak-field)
      - [Strong Field, Back-Goudsmit](#strong-field-back-goudsmit)
- [Radiation and Transitions](#radiation-and-transitions)
  - [Selection Rules](#selection-rules)
    - [Parity](#parity)
    - [Configuration](#configuration)
    - [Angular Momentum Rules](#angular-momentum-rules)
  - [X-Ray transitions from inner shells](#x-ray-transitions-from-inner-shells)
    - [Fine Structure](#fine-structure)
    - [X-Ray Absorption](#x-ray-absorption)
    - [Auger Effect](#auger-effect)
- [Molecules](#molecules)
  - [Molecular Energy Estimations](#molecular-energy-estimations)
    - [Electronic Energy](#electronic-energy)
    - [Vibrational Energy](#vibrational-energy)
    - [Rotational Energy](#rotational-energy)
  - [Another Complicated Hamiltonian](#another-complicated-hamiltonian)
  - [The Born-Oppenheimer Approximation](#the-born-oppenheimer-approximation)
    - [Rotational and Vibrational Energies](#rotational-and-vibrational-energies)
    - [Whats the Effective Potential here though](#whats-the-effective-potential-here-though)
    - [Spectroscopic Notation](#spectroscopic-notation-1)
    - [Selection Rules](#selection-rules-1)
      - [With no change in electronic states](#with-no-change-in-electronic-states)
      - [Transitions with a change of electronic state](#transitions-with-a-change-of-electronic-state)
- [Transitions and Lasers](#transitions-and-lasers)
  - [The Light-Atom interaction.](#the-light-atom-interaction)
    - [Remember Time-Dependent Perturbation Theory?](#remember-time-dependent-perturbation-theory)
    - [The interaction](#the-interaction)
    - [Rabi Oscillations](#rabi-oscillations)
  - [Two Level Systems](#two-level-systems)
    - [Einsteins Rates](#einsteins-rates)
  - [Line Broadening](#line-broadening)
    - [Einstein Coefficients and Line Broadening](#einstein-coefficients-and-line-broadening)
    - [Homogenous Broadening](#homogenous-broadening)
      - [Lifetime Broadening](#lifetime-broadening)
      - [Collision or Pressure Broadening](#collision-or-pressure-broadening)
    - [Inhomogeneous Broadening](#inhomogeneous-broadening)
      - [Doppler Broadening](#doppler-broadening)

# Moving on from Hydrogen
## Hydrogen, the simple Hamiltonian

### Energy
The energy of a Hydrogenic atom doesn't depend on l.
$$
E_n= \frac{Z^2me^4}{(4\pi\epsilon_0)^22\hbar^2n^2} = R\frac{Z^2}{n^2}
$$
### Angular Momentum
<img src="./Figs/AngularMomentumFig.jpg" alt="Figure Missing"/>

Angular wavefunctions are eigenfunctions of $l$ and $m_l$.

### Radial Wavefunctions
- $l=0$ do not vanish at $r=0$
- $l\ \rlap{=}\ /\ 0$ vanishes at $r=0$ 
- Max probability is further out as $l$ increases 
- Size and position of peak probability scales with $n$
- There are $n-l$ nodes
- So $l=n-1$ has only one node at $r=0$
<img src="./Figs/RadialFig.jpg" alt="Figure Missing"/>
## A Complicated Hamiltonian
The hydrogenic hamiltonian is now pretty well known to us...

$$
\hat{H} = \frac{\hbar}{2m}\nabla^2 + \frac{Ze^2}{4\pi\epsilon_0r}
$$

For a many electron atom however the Hamiltonian gets much more complicated, the best way is to figure out some big hydrogenic term (a central field) and apply small perturbations to it which is what we'll do in the next section.

# The Central Field Approximation

The Hamiltonian built of ever smaller approximations for an atom looks like this...

$$
\begin{aligned}   
\hat{H} &= \hat{H_0} + \hat{H_1} + \hat{H_2} + \hat{H_3} + ...\\
\text{where } \hat{H_0} &= \text{Electrons in central field}\\
 \hat{H_1} &= \text{Residual electrostatic field}\\
 \hat{H_2} &= \text{Spin orbit interaction}\\
 \hat{H_3} &= \text{Hyperfine Structure}\\
 ...\ &= \text{Further approximations}\\
\end{aligned}
$$

We like to deal with cases where $\hat{H_1} > \hat{H_2}$ but this isn't always the case. We say that:

- $\hat{H_0}$ defines **energy levels** in the quantum numbers $n$ and $l$ and is called **gross structure**
- $\hat{H_1}$ splits degeneracy in levels into **terms**
- $\hat{H_2}$ will split terms into **fine structure**
- Nuclear effects lead to **hyperfine structure**

We can now get started looking into these one by one.

## Gross Structure
The hamiltonian of a multi electron atom (considering only the electrostatic interaction between electrons and the nucleus) looks a bit like this...
$$
\begin{aligned}
\hat{H} = \overbrace{\sum^N_{i=1}\bigg\{-\frac{\hbar^2}{2m}\nabla^2_i - \frac{Ze^2}{4\pi\epsilon_0r_i}\bigg\}}^\text{Contribution of each electron in the central field} + \underbrace{\sum_{i>j}\frac{e^2}{4\pi\epsilon_0r_{ij}}}_\text{Mutual electrostatic interaction between electrons}
\end{aligned}
$$

This can't be split into hamiltonians for each electron due to the second mutual interaction term. This term is also too large to be treated as a perturbation! Clearly we are in a bit of a situation. Luckily there's a solution.

### The Central Field

To make our lives easier we want solutions of a similar form as the Hydrogenic ones which we can then apply a perturbation to. This means we want a central $\frac{1}{r}$ potential which allows us to separate the angular and radial components like we did for the Hydrogenic case. Since most of the time **a major part of electron interaction acts radially** we can combine that part with the central nuclear potential to get the Central Field. We now have the Hamiltonian.

$$
\begin{aligned}
    \hat{H} &= \hat{H_0} + \hat{H_1}\\
    \text{where } \hat{H_0} &= \sum_i\bigg\{-\frac{\hbar^2}{2m}\nabla^2_i + U(r_i)\bigg\}\\
    \text{and } \hat{H_1} &= \sum_{i>j}\frac{e^2}{4\pi\epsilon_0r_{ij}} - \sum_i\bigg\{\frac{Ze^2}{4\pi\epsilon_0r_i} + U(r_i)\bigg\}
\end{aligned}
$$

Here $\hat{H_1}$ is the residual electrostatic interaction (the part that isn't radial) this means we can assume that $\hat{H_1}<<\hat{H_0}$ which is great because we can now apply some good old fashioned perturbation theory. By comparing to the Hamiltonian of a Hydrogenic atom we can see the solutions will be of the form...

$$
\psi(n,l,m_l,m_s) = R'_{n,l}(r)Y^m_l(\theta, \phi)\chi(m_s)
$$

In this approximation we still have angular and spin functions ($Y^m_l(\theta, \phi)$ and $\chi(m_s)$) as the same but $R'_{n,l}(r)$, the radial function, will be a little different.

### Form of the Central Field

It's clear that close to the atom the central field looks like the field of the nucleus, far away the potentials will sum and the $Z-1$ other electrons will cancel out the $Z$ charge of the nucleus leaving us with a $\frac{1}{r}$ potential. The result is something like this...

<img src="./Figs/CentralFieldGraph.jpg" alt="Figure Missing" height="200"/><img style="position:absolute;right:0px" src="./Figs/ZEffectiveGraph.jpg" alt="Figure Missing" height="200"/>

This gives a $Z_\text{eff}$ value which decreases with r.
### Electronic Configurations

Electronic configurations can be guessed at using two key principles

1. The Pauli Exclusion Principle, no more than one electron can be in any state.
2. Principle of least energy, electrons fill lowest states first.

So low energy states are filled one at a time, it's worth noting that under the central field levels are no longer degenerate in $l$ so that's why I do that more detail on that in a bit.

#### Spectroscopic Notation

This is a useful bit of notation for representing energy levels, 

$1s^22s^22p^6$ represents the energy levels $1s^2$ means two electrons are in the level with $n=1$ and $l=0$, $2p^6$ represents 6 electrons in the energy level $n=2$, $l=1$.

Full spectroscopic notation includes totals at the end.

$^{2S+1}L_J$ $2S+1$ is the multiplicity due to spin, L is orbital angular momentum and J total angular momentum.

The letters used to represent numbers is an annoying thing from old fashioned spectroscopy that everyone secretly loves. Just remember, $s=0, p=1, d=2, f=3, g=4$ and it continues alphabetically from there.

#### Constructing a Periodic table
I wonder if we can explain some of the periodic table now? Shockingly we can.

<img src="./Figs/Electron_Config_Table.jpg" alt="Figure Missing"/>

As we can see the lower states fill up first (again the lack of degeneracy in $l$ will be explained in a bit) we have a degeneracy of 2 in $s$ and 6 in $p$ the interesting part is that at the 4th energy level the $l$ effect becomes large enough to span energy levels and $3d$ comes after $4s$ it's actually even more messy than the picture would like us to believe as at Chromium we get,

Va: $3s^23p^6\ \ 3d^34s^2$

Cr: $3s^23p^6\ \ 3d^54s^1$

Mn: $3s^23p^6\ \ 3d^54s^2$

Here a $3d$ electron takes precedence over a $4s$ for a bit! It's off syllabus so luckily we don't have to worry about it hut still it makes me sick.

##### Rare Gases

A key feature of the periodic table is the rare gases. These are chemically inert with high ionisation potentials. This isn't because they have "closed" shells (states for each n are all filled) but because they have filled s and p subshells. This leads to a **spherically symmetric charge distribution** electrons are now indistinguishable and take on a common wavefunction which results in higher binding energies for all leading to the classic Rare gases we know and love.

##### Alkalis

Alkalis are the element next to rare gases and have one electron outside the filled (sp) these are generally very well screened from the attracting nuclear force. This means they have very low ionisation energies and are chemically reactive.

##### First Ionisation
What does this look like then?
<div style="background:white">
<img src="./Figs/FirstIonisationGraph.png" alt="Figure Missing"/>
</div>

We get a periodic situation with a rising trend of first ionisation energies from alkalis to rare gases with some weirdness inbetween. It's worth noting that after first ionisation, the second ionisation energies se atoms shift down one. Alkaline +1 ions become the most stable. 

### Energy of Alkalis, the Quantum Defect

As we established in the [Alkalis](#alkalis) section above, alkalis single outer 'valence' electron moving in a central field of the closed shells. The further out from the nucleus the valence electron is the more it is shielded from it's attraction by the bound electrons of the closed shell. This is why the shape of the wavefunction in R (and therefore $l$) affects the energy level. Looking at the [Radial Wavefunctions](#radial-wavefunctions) section we can see that **lower levels of $l$ penetrate the core more** so we would expect these to have higher energy. It's also important that **core penetration depends very little on $n$** this means that deviation from the Hydrogenic case is almost constant as we move through n states in the valence electron. Alkaline energy levels can be expressed almost like hydrogen then...
$$
E_n = \frac{R}{(n^*)^2}
$$

where n* is the *effective quantum number*

$$
n^* = n - \delta(l)
$$

Where $\delta(l)$ is called the quantum defect and is found empirically. $\delta(l)$ can be shown to be independent of $n$ and decreases as $l$ increases.

For heavier Alkalis $\delta(l)$ increases but ionisation energies stay about the same as valence electrons start at higher values of $n$

One convenient part of the quantum defect is that it helps us identify the source of emission lines in a spectrum. To do this we use the fact that lines of the same quantum defect will correspond to levels of the same angular momentum thus be in the same series.



## Residual Electrostatic Interaction
### A Degenerate Perturbation
For atoms with two electrons we need to start considering the Residual electrostatic interaction. This is represented by the Hamiltonian $\hat{H_1}$

This means that (considering the (closed shell) $3s4s$ state of magnesium,

$$
\Delta E_1 = \big<\psi_1(3s)\psi_2(4s)|\hat{H_1}|\psi_1(3s)\psi_2(4s)\big>
$$

Physically we would expect swapping $\psi_1$ and $\psi_2$ to have no effect. This means that states $|\psi_1(3s)\psi_2(4s)\big>$ and $|\psi_2(3s)\psi_1(4s)\big>$ are degenerate and now we have to use degenerate perturbation theory. This means we need to make linear combinations of our zero order states to diagonalise $\hat{H_1}$ which is actually not too bad. From our derivation of [The Central Field](#the-central-field) we remember that,

$$
\hat{H_1} = \sum_{i>j}\frac{e^2}{4\pi\epsilon_0r_{ij}} - \sum_i\bigg\{\frac{Ze^2}{4\pi\epsilon_0r_i} + U(r_i)\bigg\}
$$

The second sum (over i) completely disappears as the $\frac{1}{r_i}$ term is a single electron operator so doesn't matter and the zero order states are eigenfunctions of the second $U(r_i)$ term. This leaves us to diagonalise the first sum only. We can start by considering the two orthogonal functions 
$$
\begin{aligned}
    \phi_1 &= a\psi_1(3s)\psi_2(4s) + b\psi_1(4s)\psi_2(3s)\\
    \phi_2 &= b^*\psi_1(3s)\psi_2(4s) - a^*\psi_1(4s)\psi_2(3s)
\end{aligned}
$$

Now we just need to find values of $a$ and $b$ where $\big<\phi_1|V|\phi_2\big>=0$ with V being that first term in H the two electron electrostatic repulsion. V doesn't distinguish $\phi_1$ and $\phi_2$ so $|a|=|b|$ which means $|a|=|b|=\frac{1}{\sqrt{2}}$ if we want normalisation.

If we write a couple of definitions,
$$
\begin{aligned}
    J &= \big<\phi_1(3s)\phi_2(4s)|V|\phi_1(3s)\phi_2(4s)\big>&\text{The direct integral}\\
    K &=   \big<\phi_1(3s)\phi_2(4s)|V|\phi_1(4s)\phi_2(3s)\big>&\text{ The exchange integral}\\
\end{aligned}
$$

Then we can calculate matrix elements

$$
\begin{aligned}
    \big<\phi_1|V|\phi_1\big> &= \Delta E_1 = J + K &\text{ singlet}\\
    \big<\phi_2|V|\phi_2\big> &= \Delta E_2 = J - K &\text{ triplet}
\end{aligned}
$$

<img src="./Figs/ResidualElectrostaticSplitting.jpg" alt="Figure Missing"/>

The off diagonals are zero as that was kind of the point of all this. A big question is "**How do I know which one is the triplet?**" and it's a good question.

### Symmetry, Antisymmetry and Spin
The degeneracy comes from the resolution of symmetry with spin!
$\phi_1$ is a symmetric state and $\phi_2$ is antisymmetric but electrons are all antisymmetric so something must be done! They have to paired with the right spin states...

$$
\begin{aligned}
    
\uparrow_1\uparrow_2,\ \downarrow_1\downarrow_2, &\frac{1}{\sqrt{2}}(\uparrow_1\downarrow_2 + \downarrow_1\uparrow_2):\ \text{symmetric}\\
&\frac{1}{\sqrt{2}}(\uparrow_1\downarrow_2 - \downarrow_1\uparrow_2):\ \text{antisymmetric}

\end{aligned}
$$

The antisymmetric spin states pair with the symmetric wavefunctions and vice versa, this means the antisymmetric state $\phi_2$ has spin degeneracy of 3 making it a triplet and the symmetric state $\phi_1$ is a singlet as it combines with just the ones antisymmetric spin state.


## Spin Orbit Interaction (Fine Structure)

The spin orbit interaction is the hamiltonian term arising from considering magnetic fields, specifically those produced by electron spin and orbit.
### The Physics
> If you want to skip to the end of this bit it's just $\Delta E  = -\underline{\mu} \cdot \underline{B}$

The angular momentum of a spinning electron is $I\underline{\omega}=\underline{\lambda}\hbar$ the energy then is $E=\frac{1}{2}I\omega^2$. The magnetic moment of the rotating electron is $\underline{\mu}=-\gamma\underline{\lambda}\hbar$ where the minus sign is for negative charge and $\gamma$ is the *gyromagnetic ratio*. If a constant B field is applied on the z axis then the moment $\mu$ will precess about that axis with some frequency $\omega^\prime$ so angular motion changes like so:
$$
\omega \rightarrow \omega + \omega^\prime cos\theta\\
\text{Or (if $\underline{\lambda}\hbar$ is in the opposite direction)}\\
\omega \rightarrow \omega - \omega^\prime cos\theta
$$
So the new energy is:
$$
\begin{aligned}
    E^\prime &= \frac{1}{2}I(\omega \pm \omega^\prime cos\theta)^2\\
    &=\frac{1}{2}I\omega^2 + \frac{1}{2}I(\omega^\prime cos\theta)^2 \pm I\omega\omega^\prime cos\theta
\end{aligned}
$$
Assuming speed at which the axis precesses to be slow compared to original angular velocity we can say that $\omega^\prime \llless \omega$ which means $(\omega^\prime cos\theta)^2 \llless \omega^2$ this means the energy change $\Delta E = E^\prime - E$ is:
$$
\begin{aligned}
\Delta E &= I\omega\omega^\prime cos\theta\\
&= \lambda\hbar\omega^\prime cos\theta
\end{aligned}
$$

We know from **Lamor's Theorem** that $\omega^\prime = -\gamma B$ so...

$$
\begin{aligned}
    \Delta E &= -\gamma\lambda\hbar Bcos\theta\\
    &=-\underline{\mu} \cdot\underline{B}
\end{aligned}
$$
### Finding the Spin Orbit Correction

Now we can say that 
$$
\begin{aligned}
\hat{H}_2 &=  -\underline{\hat{\mu}} \cdot\underline{B}\\
\Delta E &= -\big<\underline{\hat{\mu}} \cdot\underline{B}\big>  
\end{aligned}
$$

So we need...

- To find the B Field
- Have an operator for $-\underline{\hat{\mu}} \cdot\underline{B}$ depending on $r$, $\underline{s}$, and $\underline{l}$
- Perform some perturbation theory

### The B Field due to Orbital Motion

The field the electrons experience is the one produced by the electronic orbital motion. This is given by...
$$
\underline{B} = -\frac{\underline{v}\times \underline{E}}{c^2}
$$

as $\underline{p} = m\underline{v}$ 
$$
\underline{B} = -\frac{1}{mc^2}\underline{p}\times\underline{E}
$$

Remembering E is purely radial in the central field we can rewrite it $\underline{B}$:

$$
\underline{B} = -\frac{1}{mc^2}\underline{p}\times\underline{r}\frac{|\underline{E}|}{|\underline{r}|}
$$
Luckily $\underline{r}\times\underline{p} = \underline{l}$ so:
$$
\underline{B} = \frac{1}{mc^2}\frac{|\underline{E}|}{|\underline{r}|}\underline{\hat{l}}
$$

$|\underline{E}| = \frac{\partial\phi}{\partial r}$ and $e\phi(r) = U(r)$ so $|\underline{E}| = -\frac{1}{r}\frac{\partial U(r)}{\partial r}$. Putting it all together we have:
$$
\underline{B} = \frac{1}{emc^2}\frac{1}{r}\frac{\partial U(r)}{\partial r}\underline{\hat{l}}
$$

U(r) is the central potential. 

### Finding Our Operator

The operator we need to find is $-\underline{\mu_s} \cdot \underline{B}$. The intrinsic magnetic moment of an electron due to spin is:

$$
\underline{\mu_s} = -g_s\frac{\mu_B}{\hbar}\underline{\hat{s}}
$$

So

$$
-\underline{\mu_s} \cdot \underline{B} = -g_s\frac{\mu_B}{\hbar}\frac{1}{emc^2}\frac{1}{r}\frac{\partial U(r)}{\partial r}\underline{\hat{s}}\cdot\underline{\hat{l}}
$$

Sadly most of the time we don't know the form of U(r). It is a great tragedy but we must soldier on. We can at least see that the energy operator is proportional to $\frac{1}{r}\frac{\partial U(r)}{\partial r}\underline{\hat{s}}\cdot\underline{\hat{l}}$ which is positive and determined by the relative orientation of $\underline{\hat{s}}$ and $\underline{\hat{l}}$ which is nice. A hydrogen atom has the potential $U(r) = -\frac{Ze^2}{4\pi\epsilon_0r}$ this gives:

$$
    -\underline{\mu_s} \cdot \underline{B} = \frac{\mu_B}{4\pi}2Zg_s\mu_B^2\frac{1}{r^3}\frac{\underline{\hat{s}}\cdot\underline{\hat{l}}}{\hbar^2}
$$

Although if you take into account the relativistic correction of **Thomas Precession** which isn't on syllabus we need to divide by 2 so:

$$
    -\underline{\mu_s} \cdot \underline{B} = \frac{\mu_B}{4\pi}Zg_s\mu_B^2\frac{1}{r^3}\frac{\underline{\hat{s}}\cdot\underline{\hat{l}}}{\hbar^2}
$$

### Doing the Work

$$
\Delta E = \frac{\mu_B}{4\pi\hbar^2}Zg_s\mu_B^2\big<\frac{1}{r^3}\big>\big<\underline{\hat{s}}\cdot\underline{\hat{l}}\big>
$$

The radial part is a standard radial integral using hydrogenic wavefunctions.

$$
\begin{aligned}
    \big<\frac{1}{r^3}\big> &= \int_0^{\infin}R^2_{n,l}(r)\frac{1}{r^3}r^2dr\\
    &=\frac{Z^3}{n^3a_0^3l(l+1/2)(l+1)} 
\end{aligned}
$$

the dot product is a bit harder but we can use the power of the vector model.

$$
\begin{aligned}
\underline{\hat{j}}\ \ &= \underline{\hat{s}} + \underline{\hat{l}}\\
\implies\underline{\hat{j}}^2&=\underline{\hat{s}}^2 + \underline{\hat{l}}^2+\underline{\hat{s}}\cdot\underline{\hat{l}}\\
\therefore\underline{\hat{s}}\cdot\underline{\hat{l}}&=\underline{\hat{j}}^2 - \underline{\hat{s}}^2 + \underline{\hat{l}}^2
\end{aligned}
$$

This means that we can write our matrix elements in a different basis as $|n,l,m_l,s,m_s\big>$ is not diagonalised.

$$
\big<n,l,s,j,m_j|\underline{\hat{s}}\cdot\underline{\hat{l}}|n',l',s',j',m_j'\big> = 0 \text{ unless } j=j'\text{ and } m_j=m_j' 
$$

The diagonal elements are then:

$$
\big<n,l,s,j,m_j|\underline{\hat{s}}\cdot\underline{\hat{l}}|n',l',s',j',m_j'\big> = \frac{1}{2}\{j(j+1) - l(l+1) - s(s+1)\}\hbar^2
$$
 
This is a nice result but what does this mean? We found that we need a new basis when we consider spin orbit. This is because without spin orbit $\underline{\hat{s}}$ and $\underline{\hat{l}}$ are fixed, making their projections in z good quantum numbers. When we consider spin orbit though $\underline{\hat{s}}$ and $\underline{\hat{l}}$ precess around their mutual sum $\underline{\hat{j}}$ which means $m_l$ ans $m_s$ are no longer constants of motion. Clearly it is important to choose a basis which suits the perturbation we're doing.

### Final Result for Spin Orbit

Using
$$
\hat{H_2} \propto\frac{1}{r}\frac{\partial U(r)}{\partial r}\underline{\hat{s}}\cdot\underline{\hat{l}}
$$

We can find perturbed energy:

$$
\Delta E_{SO} = \big<\hat{H_2}\big> = \beta_{n,l} \frac{1}{2}\{j(j+1) - l(l+1) - s(s+1)\}\hbar^2
$$

Where for hydrogen molecules:
$$
\beta_{nl} = \frac{\mu_0Z^4g_s\mu_b^2}{4\pi}\frac{1}{n^3a_0^3l(l+1/2)(l+1)}
$$
For single electron atoms (alkalis) j has twofold degeneracy $j =l\pm 1/2$ so energy levels are split in two. For the two electron a 
tom the whole picture (plus some spoilers on magnetic fields) can be seen below.

 <img src="./Figs/SOSplitting.png"/>

## LS-Coupling

In these notes we assume LS-Coupling because it's super convenient and I like it. In LS coupling $\underline{J}= \underline{L} +\underline{S}$ which in vector model terms means that $\underline{L}$ and $\underline{S}$ couple to precess around $\underline{J}$ which makes $L,S,J,$ and $M_J$ good quantum numbers but $M_L$ and $M_S$ obviously not.

<img src="./Figs/LSCoupling.jpg" alt="Figure Missing"/>

## Nuclear Effects

So far we assume the nucleus is simple, and pointlike with infinite mass, this is obviously not true! The effect of nucleic movement, distributed charge, and spinning leading to a magnetic field leads to corrections to the energy levels of an atom. 
### Hyperfine Structure

The magnetic affect mentioned is called hyperfine structure and we'll look at it below.

Electronic magnetic moments are described by the equations provided by Quantum Physics.
$$
\underline{\mu}_s = -g_s\frac{\mu_B}{\hbar}\underline{s}\\
\ \\
\underline{\mu}_l = -g_l\frac{\mu_B}{\hbar}\underline{l}\\
\ \\
\underline{\mu}_j = \underline{\mu_s} + \underline{\mu}_l
$$

$g_s = 2$ adn $g_l = 1$ (with s and l in units of $\hbar$). The coefficient $\mu_B$ is the bohr magneton, $\mu_B = \frac{e\hbar}{2m}$ for the Nuclear moment we have,

$$
\underline{\mu}_I = g_I\frac{\mu_N}{\hbar}\underline{I}\\
g_I\sim1\\
\mu_N = \mu_B \times \frac{m_e}{m_p}\\
$$

$\underline{I}$ is the vector operator for total nuclear spin. The relationship between $\mu_N$ and $\mu_B$ means that $\underline{\mu}_I \llless \underline{\mu}_s, \underline{\mu}_l$ so the magnetic interaction will be small. This leads to a much slower precession which is great because that means $\underline{I}$ and $\underline{J}$ will remain nice and well defined. We can write the perturbation as:

$$
\hat{H}_3 = -\underline{\hat{\mu}}_I \cdot \underline{\hat{B}}_{el}
$$

The magnetic field is proportional to the total angular momentum of electrons $\underline{J}$ and we've seen that $\underline{\mu}_I \propto \underline{I}$ so we get a constant of proportionality $A_J$. 

$$
\hat{H}_3 = A_J I\cdot J. 
$$

> Toby derives $A_J$ but the lecturer seems to think it isn't important.

Let's let $\underline{F} = \underline{I} + \underline{J}$ this gives:

$$
\underline{I}\cdot\underline{J} = \frac{1}{2}(\underline{F}^2 - \underline{I}^2 - \underline{J}^2)\\
\ \\
\implies \Delta E_3 = \frac{A_J}{2}\bigg(F(F+1) - I(I+1) - J(J+1)\bigg)
$$

This leads to the useful interval rule,

$$
\Delta E_F = \Delta E(F) - \Delta E(F-1) \sim A_J F
$$

The number of levels produced by hyperfine splitting depends on the values of F, these follow the rule:
$$
\text{number of levels}= \bigg\{
\begin{gathered}
    2I+1\ \text{ if }\ I<J\\
    2J+1\ \text{ if }\ J<I
\end{gathered}
$$

<img src="./Figs/HFSplitting.png" style="background:white">

#### Finding I

To find I we need to examine the hyperfine structure. This structure has the selection rules,
$$
\Delta F = 0, \pm1 \text{ but not } 0\rightarrow0
$$

From there there are three methods:

+ **Interval Rule** The interval between $F$ and $F-1$ is proportional to the higher level, ($F$) we can use this to find $I$ if we know $J$
+ **Number of Spectral Lines** using the degeneracy rules above we can find $I$ if we know $I<J$.
+ **Relative Intensities** the realtive intensities of spectral components is proportional to the statistical weight of the $2F+1$ hyperfine structure levels. So we can find $I$ if we know $J$

### Mass Effects
NOT ON SYLLABUS
### Field Effects
NOT ON SYLLABUS

## External Magnetic Fields

A final thing to consider the perturbation provided by a magnetic field and how that affects our previous energy levels. It's clear that the hamiltonian for this perturbation would be:

$$
\hat{H}_{mag} = \underline{\mu}_{atom} \cdot \underline{B}_{ext}
$$

Where does this sit on our hierarchy of perturbations? Most laboratory magnets are stronger than the hyperfine perturbation and weaker than the electrostatic (and Central Field), this means we only need to figure out where it sits with regard to the spin orbit (which is annoyingly difficult).

### Magnetic Effects in Fine Structure

#### Weak Field, No Spin, Normal Zeeman Effect

Without spin (and spin orbit) we have $\underline{\mu}_{atom} = \underline{\mu}_L$ so 
$$
\Delta E_Z = g_L\mu_B\underline{L}\cdot\underline{B}\\
\Delta E_Z = g_L\mu_BB_{ext}M_L
$$

This results from $\underline{L}$ precessing around $\underline{B}$ and is called Larmor precession it results in breaking the degeneracy of $M_L$. This splits the observed spectra up into three because of the selection rules of $\Delta M_L = 0, \pm1$ so we get $\omega \rightarrow \omega, \omega \pm \Delta\omega$ where
$$
\Delta\omega = \Delta E_Z/\hbar = \mu_B B_{ext}/\hbar
$$

This three splitting is called normal zeeman effect.


<img src="./Figs/Zeeman.png" alt="Figure Missing"/>

#### Weak Field with Spin Orbit, Anomalous Zeeman

Recall that for spin orbit we needed to use new wavefunctions with different quantum numbers $|n,L,S,J,M_J\big>$. With spin included our perturbation becomes,

$$
\begin{aligned}
\Delta E_{AZ} &= \big<-\underline{\mu}_J\cdot\underline{B}_{ext}\big>\\
&= g_J\mu_B|\underline{B}_{ext}|\big<\hat{J}_z\big>
\end{aligned}
$$

With $\underline{B}_{ext}$ oriented in the z direction. BUT WHAT IS $g_J$?

> Supposedly this is a question examiners really like.

To find $g_J$ we can write $\mu_J$ in it's other definition $\mu_J = \mu_S + \mu_L$ this gives us:

$$
\Delta \hat{H}_{AZ} = g_L\mu_B\underline{L}\cdot\underline{B}_{ext} + g_S\mu_B\underline{S}\cdot\underline{B}_{ext}
$$

But what do the dot products evaluate to? This isn't so much of a problem as we only want the time average for $\Delta E_{AZ}$ so we actually need to look at the dot products of their projections onto J which average stay constant while other components average to zero.

> This is because the precess around J in spin-orbit.

This gives us...

$$
\Delta E_{AZ} = g_L\mu_B\bigg<\frac{|\underline{L}\cdot \underline{J}|}{|\underline{J}|^2}\underline{J}\cdot\underline{B}_{ext}\bigg> + g_S\mu_B\bigg<\frac{|\underline{S}\cdot \underline{J}|}{|\underline{J}|^2}\underline{J}\cdot\underline{B}_{ext}\bigg>
$$

We know how to do the dot products $\underline{L}\cdot \underline{J}$ and $\underline{S}\cdot \underline{J}$ also we know $g_L = 1$ and $g_S = 2$ so we get:
$$
\begin{aligned}
\Delta E_{AZ} &= \mu_B\bigg<\frac{3\underline{J}^2 - \underline{L}^2 + \underline{S}^2}{2\underline{J}^2}J_zB_{ext}\bigg>\\
\ \\
&=\frac{3J(J+1) - L(L+1) + S(S+1)}{2J(J+1)}\mu_B B_{ext}M_J
\end{aligned}
$$

This is the same as $g_J\mu_BB_{ext}M_J$ which we got before so we have that,
$$
\Delta E_{AZ} = g_J\mu_BB_{ext}M_J\\
\ \\
g_J = \frac{3J(J+1) - L(L+1) + S(S+1)}{2J(J+1)}
$$

This breaks the degeneracy in M_J, lines split differently because of the half contribution of spin and the different size due to the complicated $g_J$


<img src="./Figs/Anomalous_Zeeman.jpg" alt="Figure Missing"/>

#### Strong Fields, Spin and Orbit, Paschen-Back Effect

A strong field means $\underline{S}$ and $\underline{L}$ precess much faster around $\underline{B}_{ext}$ and are independent which means $\underline{J}$ isn't such a good quantum number. Now it's good to use $|n, L, S, M_L, M_S\big>$ This gives us:
$$
\Delta E_{PB} = (M_L + 2M_S)\mu_BB_{ext}
$$

Which is much simpler tbh. We then need to apply the spin orbit correction onto this which means finding $<\underline{S}\cdot\underline{L}>$ but $\underline{S}$ and $\underline{L}$ are precessing so fast around $\bold{\hat{z}}$ that only the $z$ components matter so we get
$$
\xi<\underline{S}\cdot\underline{L}> = \xi M_LM_S
$$

We have six states for L = 1, ($M_L=1,0,-1, M_S=-1/2,+1/2$) which lead to shifts in spin orbit of ($\xi/2, 0, -\xi/2, -\xi/2, 0, \xi/2$), ignoring the relatively small spin orbit effect we get equally spaced energy levels, the selection rules are $\Delta M_L = 0, \pm1$ and $\Delta S = 0$ since the spin plays no part in the transition we should get a triplet similar to the Normal Zeeman effect and we do!


<img src="./Figs/Paschen_Back.png" alt="Figure Missing"/>

Putting this all together we get this diagram:


<img src="./Figs/AllTogetherMagnet.jpg" alt="Figure Missing"/>

### Magnetic Effects In Hyperfine Structure

If we add an external field the hyperfine perturbation becomes

$$
\hat{H}_3^\prime = A_J\underline{I}\cdot\underline{J} + g_J\mu_B\underline{J}\cdot\underline{B}_{ext} - g_I\mu_N\underline{I}\cdot\underline{B}_{ext}
$$
As $\mu_I << \mu_J$ we can neglect the third term. If $A_J\underline{I}\cdot\underline{J}>>g_J\mu_B\underline{J}\cdot\underline{B}_{ext}$ we can call B a weak field, and if $A_J\underline{I}\cdot\underline{J}<<g_J\mu_B\underline{J}\cdot\underline{B}_{ext}$ it's a strong field.

#### Weak Field
In the weak field we have hyperfine effects so F is our good quantum number. This means that
$$
\Delta E_F = -\underline{\mu}_F\cdot\underline{B}_{ext}\\
$$

We can do this the same as the anomalous zeeman effect,

$$
\underline{\mu}_F = g_F\mu_B\underline{F}\\
\underline{\mu}_F = g_J\mu_B\frac{\underline{J}\cdot\underline{F}}{|\underline{F}|^2}\underline{F}
$$
Here we ignore the $I$ component as it is tiny compared to the $J$ component. Using $F=I+J$ and our vector dot product trick we get,

$$
g_F = g_J\frac{F(F+1) + J(J+1) - I(I+1)}{2F(F+1)}
$$

This leads to a hfs term

$$
\Delta E = \frac{A_F}{2}\bigg(F(F+1)+ J(J+1) - I(I+1)\bigg) + g_F\mu_B\underline{F}\cdot\underline{B}_{ext}
$$

Which gives a simple degeneracy in $M_F$


<img src="./Figs/hyperfinesplittingweak.jpg" alt="Figure Missing"/>

#### Strong Field, Back-Goudsmit

In a strong field $J$ couples more strongly to $B_{ext}$ than to $I$ this means the $F$ isn't a good quantum number but $M_J$ is. 
>$M_J$ is the component of $J$ in z direction which is chosen as the direction of the field. 

As $\underline{J}$ is precessing around $\underline{B}_{ext}$ and $\underline{I}$ precesses slower around the constant part of $\underline{J}$ we get 
$$
\Delta E \propto \big<\underline{I}\cdot\underline{J}_z\big>
$$

So the strong shifts become:

$$
\Delta E_{BG} = A_JM_IM_J + g_J\mu_BM_JB_{ext}
$$

The resulting splitting looks like this with $M_F$ remaining a good quantum number.

<img src="./Figs/hyperfinesplitting.jpg" alt="Figure Missing"/>

# Radiation and Transitions
The Atomic Energy levels are important but what what we observe are the actual transitions, so it is important to also look at the physics of these.

## Selection Rules

These rules tell us whether an atom can transition from one state to another. If we have solutions to the time dependant schrödinger equation which look like this:
$$
\psi_i = \phi(r, \theta, \phi)e^{iE_it/\hbar}
$$

This gives us the perturbation matrix elements of

$$
P_{ij} = \big<\phi_i|-e\underline{r}|\phi_j\big>e^{i(E_i-E_j)t/\hbar}
$$

Where $\phi_i=\phi_j$ we have the stationary states but if $P_{ij} !=0$ then we have a transition between those states.

### Parity

The parity of the operator $e\underline{r}$ is odd, this means changing $r$ to $-r$ changes the sign of the element. This means that two even or two odd parity states in the matrix element would combine with the odd operator to give an odd integrand, which over all space integrates to $0$. So for a trnnsition we need two states of opposite parity which gives the selection rule
$$
\Delta l = \pm1
$$

This makes physical sense as conservation  of angular momentum requires one unit of $\hbar$ for an electron to jump.

### Configuration

Could more than one electron jump? The matrix element below represents this,
$$
\begin{aligned}
&\phantom{=}\big<\phi_1(1s)\phi_2(2p)|\underline{r}_1+\underline{r}_2|\phi_1(3p)\phi_2(3d)\big>\\
&=\big<\phi_1(1s)|\underline{r}_1|\phi_1(3p)\big>\times\big<\phi_2(2p)|\phi_2(3d)\big> + \big<\phi_2(2p))|\underline{r}_2|\phi_2(3d)\big>\times\big<\phi_1(1s)|\phi_1(3p)\big>\\
&=0\\
\text{as } &\phantom{=}\big<\phi_i(nl)|\phi_i(n^\prime l^\prime)\big> = 0
\end{aligned}
$$

So configurations can only change by one electron jump at a time.

### Angular Momentum Rules

Again if we consider a single unit of $\hbar$ angular momentum we have

$$
\Delta J = 0, \pm1 \text{ but not } 0\rightarrow0\\
\Delta L = 0, \pm1 \text{ but not } 0\rightarrow0\\
\Delta S = 0 \text{ as operator doesn't effect spin}
$$

Finally we have

$$
\Delta M_J = 0, \pm1
$$
Which isn't too obvious but can be seen in a magnetic field.

## X-Ray transitions from inner shells

Transitions of outer "valence" electrons are mostly what we've been thinking about, these give spectra of $\sim 10^{-7}m$ to $1m$ (ultra violet to radio waves). We can disturb the tightly bound inner shell with high energy photons in the $keV$ range, this gives us X-Ray wavelengths. Usually the inner levels are occupied so transitions can only occur if an electron is knocked loose by an energetic photon or free electron.

X-Rays are generated by high energy electrons striking a target, there are two contributions to the spectrum:
+ A continuous distribution produced by the deceleration of charged particles (Bremsstrahlung or braking radiation)
+ Discrete lines produced by inner shell transitions which only appear above a threshold energy

<img src="./Figs/Bremsstrahlung.jpg" alt="Figure Missing"/>

We can say a few things about these discrete lines:

+ The wavelengths fit a simple series formula
+ Lines of the same series appear together once a threshold energy is crossed
+ The threshold energy of a series just exceeds the shortest energy of the shortest wavelength in that series
+ Above a certain energy no new series appear

These observations can be explained by a transition in the inner shell. If the energy is sufficient an electron will be moved to a vacant higher level. The binding energy of the atom will be of the order $10eV$ so if the incident energy is $10^3eV$ or more the atom will be ionised. The lines observed then are the transitions from higher levels down into the now vacant spot. In the context of X-rays the $n = 1,2,3$ are known as $K$, $L$, and $M$ respectively.

This means the K series is the series produced by higher levels falling into the $n=1$ shell and the L series if produced by falling into the $n=2$ shell and so on. The energy of each shell can be expressed by the hydrogenic model:

$$
E_N = \frac{R(Z-\sigma_n)^2}{n^2}
$$

Where $\sigma_n$ is a screening factor. We can use differences to get a series of wavenumbers $\bar{\nu} = 1/\lambda$

$$
\bar{\nu} = R\bigg\{\frac{(Z-\sigma_K)^2}{1^2} - \frac{(Z-\sigma_i)^2}{n_i^2}\bigg\}
$$

Where $n_i = 2, 3, 4, ...$ which is how we get a series. The longest wavelength is typically called $\alpha$ and the next $\beta$ and so on.

<img src="./Figs/XRayLines.jpg" alt="Figure Missing"/>


### Fine Structure

The X-Ray spectrum is split just like the normal one due to spin orbit. The energy splitting due to fine structure can be written as:

$$
\Delta E_{fs} =  \frac{5.8Z^4}{n^3l(l+1)}
$$

The x-ray lines are then split by their selection rules,

$$
\Delta l = \pm1, \Delta j = 0, \pm1
$$

So $K_\alpha$ splits into a doublet $K_{\alpha_1}$ and $K_{\alpha_2}$

### X-Ray Absorption

Two things can happen when X-Rays are absorbed, either an electron is moved to a vacant valence shell or (if energy is high enough) they are ejected from the atom in photoionisation. This latter is far easier as the former makes it much harder to conserve energy and momentum. The result is sharp edges called "*absorption edge*" where ionisation potential is reached for that series and the chance of absorption becomes much higher.

<img src="./Figs/XRayAbsorption.jpg" alt="Figure Missing"/>

### Auger Effect

The creation of a vacancy can have the simple effect of an electron filling empty level but it cal also result in the ejection of another electron as it gains energy from an electron filling the empty level like so:

<img src="./Figs/XRayAuger.jpg" 
alt="Figure Missing"/>

The kinetic energy provided is equal to the energy produced by the transition minus the ionation potential of the auger electron, in the above case this gives:

$$
KE = (E_K-E_L) - E_L
$$

There are now two vacancies in the $L$ shell which could be simply filled or produce more auger effects.

# Molecules

Time to take a dip into the domain of chemistry, diatomic molecules. A diatomic molecule is a useful first step because the is always rotational symmetry around the axis that joins the two.

## Molecular Energy Estimations

It's useful to get an idea about the scale of various contributions to energy with some order of magnitude estimates.

### Electronic Energy

If our valence electron is confined to the region of size $a$ then we can use the uncertainty principle:

$$
\Delta x\Delta p = \frac{\hbar}{2} \rightarrow p \sim \frac{\hbar}{a}
$$

We can then estimate electronic energy $E_e$ as it'll be of the same order as the kinetic energy

$$
E_e \sim \frac{p^2}{2m_e} = \frac{\hbar^2}{2m_ea^2}
$$

If we have that $a\sim a_0$ then $E_e$ is around $eV$ we can also get a timescale with $\tau_e = \hbar/E_e$.

### Vibrational Energy

We can find vibrational energy by assuming the molecule can be treated as a classical harmonic oscillator. This means
$$ 
V_{vib}(x) = \frac{1}{2}\mu\omega_{vib}^2x^2\\
\text{where}\\
\mu = \text{reduced mass} = \frac{m_1m_2}{m_1 + m_2}
$$

At $x\sim a$ all the electronic energy should be vibrational energy so we get

$$
\frac{1}{2}\mu\omega_{vib}^2x^2 \sim \frac{\hbar^2}{2m_ea^2} \rightarrow \omega_{vib} \sim \bigg(\frac{\hbar^2}{\mu m_ea^4}\bigg)\\
\implies E_{vib} \sim \sqrt{\frac{m_e}{\mu}}E_e
$$

So vibrational energy is smaller than electronic energy by around an order of 100.

### Rotational Energy

We can treat the molecule as a rigid rotator and ignore the rotation about the axis of symmetry (the axis joining the atoms) as this is a very small moment of inertia. The moment of inertia of the perpendicular axis is $I=\mu a^2$ since angular momentum ($L$) is around $\hbar$ we can say that
$$
L \sim I\omega_{rot} \sim \hbar \rightarrow \omega_{rot} \sim \frac{\hbar}{I} \sim \frac{\hbar}{\mu a^2} 
$$

This gives a rotational energy of:

$$
E_{rot} = \frac{1}{2}I\omega_{rot}^2 = \frac{m_e}{\mu}E_e
$$

So order $10000$ smaller than $E_e$ and $100$ smaller than $E_{vib}$. So

$$
E_e \gg E_{vib} \gg E_{rot}\\
\tau_e \ll \tau_{vib} \ll \tau_{rot} 
$$

## Another Complicated Hamiltonian

Now we can try actually guessing the Hamiltonian,

$$
H_\text{molecular} = \underbrace{T_n}_\text{KE of nuclei} + \underbrace{T_e}_\text{KE of electrons} + \underbrace{V(\underline{r}_i, \underline{R})}_\text{Potential Energy}
$$

These terms are

$$
T_n = -\frac{\hbar^2}{2\mu}\nabla^2_R\\
T_e = -\sum^N_i\frac{\hbar^2}{2m_e}\nabla^2_{r_i}\\
\begin{aligned}
V(\underline{r}_i,\underline{R}) &= \underbrace{\sum_j^2\sum_i^N\bigg(-\frac{Z_je^2}{4\pi\epsilon_0|\underline{r}_i - \underline{R}_j|}\bigg)}_\text{electron-nuclear interaction} \dots\\
&+ \underbrace{\sum_{i<j>}^N\frac{e^2}{4\pi\epsilon_0|\underline{r}_i - \underline{r}_j|}}_\text{electron-electron repulsion}\dots \\
&+ \underbrace{\frac{Z_1Z_2e^2}{4\pi\epsilon_0|\underline{R}|}}_\text{internuclear repulsion}
\end{aligned}
$$

Where $\underline{R}_{1,2}$ are the positions of the nuclei relative to center of mass. The origin is on the center of mass. This means that we can write the wavefunction:

$$
|\psi\big> = |\psi_n\big>|\psi_e\big>
$$

We can split the electronic energy with $H_e = T_e + V(\underline{r}_i,\underline{R})$ which gives us our TISE:

$$
[T_n + H_e]|\psi_n\big>|\psi_e\big> = E|\psi_n\big>|\psi_e\big>
$$

Multiplying by $\big<\psi_e|$ we get:

$$
\big<\psi_e|T_n + H_e | |\psi_n\big>|\psi_e\big> = E|\psi_n\big>\\
\implies \bigg\{\big<\psi_e|T_n|\psi_e\big> + E_e(R)\bigg\}|\psi_n\big> = E|\psi_n\big>
$$

## The Born-Oppenheimer Approximation

We can make the Born-Oppenheimer Approximation

> Born-Oppenheimer Approximation $\implies$ Electronic wavefunction has weak dependence on the magnitude $R$ of internuclear separation so only the angular part of $T_n$ acts on $|\psi_e\big>$

This gives the mathematical mess that is:

$$
H_e|\psi_e\big> = E_e|\psi_e\big>\\
\ \\
\bigg[-\frac{\hbar^2}{2\mu R^2}\frac{\partial}{\partial R}\bigg(R^2\frac{\partial}{\partial R}\bigg) + \frac{\big<\psi_e|\underline{N}^2|\psi_e\big>}{2\mu R^2} + E_e(R)\bigg]|\psi_n\big> = E|\psi_n\big>
$$

Where $\underline{N}$ is orbital angular momentum operator of the nuclei.

### Rotational and Vibrational Energies

The total angular momentum of electrons and nuclei

$$
\underline{K} = \underline{N} + \underline{L}
$$

In closed systems

$$
K^2|\psi\big> = K(K+1)\hbar^2|\psi\big>\\
K_z|\psi\big> = M_K\hbar|\psi\big>
$$

Because of the axis of symmetry about the axis $L_z$ is constant. $\underline{N}\perp\underline{R}$ by definition so we have $K_z = L_z = \Lambda\hbar$ ($M_L = \Lambda$ by convention)

Remember we need to evaluate $\big<\psi_e|\underline{N}^2|\psi_e\big>$ but we have that $\underline{N}^2 = \underline{K}^2 - \underline{L}^2 - 2\underline{N}\cdot\underline{L}$

As L precesses rapidly we can say that only $L_z$ matters in a time average. 
$$
\big<\psi_e|\underline{N}\cdot\underline{L}|\psi_e\big> = 0\ \text{ and }\ \big<\psi_e|\underline{L}^2|\psi_e\big> = \big<\psi_e|L_z^2|\psi_e\big> = \Lambda^2\hbar^2
$$

This and the fact we can split $\psi_n(\underline{R})$ into $\phi_{vib}(R)\psi_{rot}(\theta\phi)$ gives

$$
\hat{H}_vib = -\frac{\hbar^2}{2\mu}\frac{\partial^2}{\partial R^2} + V_{eff}(R)\\
V_{eff}(R) = E_e(R) + \frac{[K(K+1) - \Lambda^2]\hbar^2}{2\mu R^2}
$$

### Whats the Effective Potential here though

I'll be honest, all I have here is toby and I'm not sure how useful what he's saying is so I'll just write the result:

$$
E = E_e(R_0) + \bigg(\nu + \frac{1}{2}\bigg)\hbar\omega_{vib} + B_rK(K+1)\\
\ \\
\text{where}\\
\ \\
\omega_{vib} = \bigg(\frac{K_s}{\mu}\bigg)^{1/2}\\
\ \\
K_s = \frac{d^2E_e}{dR^2}\bigg|_{R_0}\\
\ \\
B_r = \frac{\hbar^2}{2\mu R_0^2} = \frac{\hbar^2}{2I_M}
$$

### Spectroscopic Notation

Toby writes a bit about spectroscopic notation for molecules but I'm not sure it's needed.

### Selection Rules

#### With no change in electronic states

$$
\Delta K = 0, \pm1 \text{ except for } \Delta K = \pm1 \text{ for } \Lambda = \Delta\Lambda = 0\\
\Delta\nu = \pm1  
$$

#### Transitions with a change of electronic state
$$
\Delta S = 0\\
\Delta \Lambda = 0, \pm1\\
\Sigma^\pm \rightarrow \Sigma^\pm\\
g \rightarrow u 
$$

Where $\Sigma^\pm$ is the symmetry of $\Sigma$ states ($\Lambda$ can be $\Sigma, \Pi, \Delta$) and $g$ and $u$ represent symmetric and antisymmetric states in homonuclear (diatomic molecules with two of the same element) case.

# Transitions and Lasers

## The Light-Atom interaction.

### Remember Time-Dependent Perturbation Theory?

No? Well I'm not going to type the whole thing out. Basically if you have a two level system with hamiltonian $\hat{H}_0$ and unperturbed eigenstates $\psi_1(\bold{r})$ and $\psi_2(\bold{r})$ then the system with hamiltonian $\hat{H} = \hat{H}_0 + \hat{V}(t)$ has the wavefunction...
$$
\psi(\bold{r},t) = c_1(t)e^{-i\omega_1t}\psi_1(\bold{r}) + c_2(t)e^{-i\omega_2t}\psi_2(\bold{r})
$$

and after a bit of maths you find that

$$
\begin{aligned}
  \dot{c}_1 &= -\frac{i}{\hbar}(c_1V_{11} + c_2V_{12}e^{-i\omega_0t})\\
  \dot{c}_2 &= -\frac{i}{\hbar}(c_1V_{21}e^{-i\omega_0t} + c_2V_{22})
\end{aligned}
$$

Where $\omega_0 = (\omega_2 - \omega_1)$ and $V_{nm} = \big<\psi_n|\hat{V}|\psi_m\big>$.

### The interaction

The electric field of an incoming EM wave can be written as

$$
\mathcal{E} = \mathcal{E}_0\cos\omega t
$$

So the perturbation of this is

$$
\hat{V}(t) = e\bold{\hat{x}}\mathcal{E}_0\cos\omega t
$$

This gives us the matrix elements for a two level system...

$$
\begin{aligned}
  V_{11} &= \big<\psi_1|e\bold{\hat{x}}|\psi_1\big>\mathcal{E}_0\cos\omega t\\
  V_{11} &= \big<\psi_1|e\bold{\hat{x}}|\psi_1\big>\mathcal{E}_0\cos\omega t\\
  V_{21} = V_{12}^* = V_{12} &= \big<\psi_1|e\bold{\hat{x}}|\psi_2\big>\mathcal{E}_0\cos\omega t
\end{aligned}
$$

We can define the *Rabi frequency* as...

$$
\Omega = \frac{\mathcal{E}_0}{\hbar}\big<\psi_1|e\bold{\hat{x}}|\psi_2\big>
$$

This gives us the coeficient rate of changes from perturbation theory as...

$$
\begin{aligned}
\dot{c}_1 &= -i\Omega\cos\omega te^{-i\omega_0t}c_2\\
\dot{c}_2 &= -i\Omega\cos\omega te^{i\omega_0t}c_1
\end{aligned}
$$

> The notes now do this in the weak field limit but the syllabus mentions Rabi Oscillations so I'm going to skip to that.

### Rabi Oscillations

We can rewrite these equations using $cos\omega t = \frac{1}{2}(e^{i\omega t} + e^{-i\omega t}$ to get...

$$
\dot{c}_1 = -\frac{1}{2}i\Omega\big(e^{(\omega-\omega_0)t} + e^{i(\omega+\omega_0)t}\big)c_2
$$

And something similar for $\dot{c}_2$ When we end up integrating these we can use the rotating wave approximation ($|\omega-\omega_0| << \omega + \omega_0$) which means we can neglect the rapidly oscillating term in $e^{i(\omega+\omega_0)t}$ this gives...

$$
\dot{c}_1 = -\frac{1}{2}i\Omega e^{+it\delta}c_2\\
\ \\
\dot{c}_2 = -\frac{1}{2}i\Omega e^{-it\delta}c_1
$$
Where $\delta = \omega-\omega_0$ which cam ne considered the "detuning" of the radiation from the atomic transition.

We can differentiate again to solve the coupled equations...

$$
\ddot{c}_2 - i\delta\dot{c}_2 + \bigg|\frac{\Omega}{2}\bigg|^2c_2 = 0
$$

If we start with $\psi(\bold{r}, t) = \psi_1$ then we have...

$$
|c_2(t)|^2 = \frac{\Omega^2}{\Omega^2 + \delta^2}\sin^2\bigg(\frac{1}{2}t\sqrt{\Omega^2+\delta^2}\bigg)
$$

Which produces weird Rabi Oscillations which don't fit with the idea of rates (which we look at in the next section) at all! If we imagine these Rabi Oscillations are damped however we can fudge it into something approaching the rate equation solution.

<img src="./Figs/RabiDamped.jpg"/>

## Two Level Systems

We used a two level system above because it is useful to approximate an atom as a two level system because atomic transitions are very narrow in frequency so we can consider two levels in isolation from the rest. For this system let's think of a lower level of energy $E_1$ and an upper of energy $E_2$. The frequency of light emitted if there is a transition from $E_2$ to $E_1$ is $\omega_{21} = (E_2 - E_1)/\hbar$. 

### Einsteins Rates

We can think of three distinct processes through which light can interact with an atom (or two level system)...

+ **Spontaneous Emission**: We move from the upper level to the lower level through a decay adn releases a photon of energy $\hbar\omega_{21}$. The rate of this is defined as $n_2A_{21}$ where $n_2$ is the population of the upper level and $A_{21}$ is the characteristic rate of the transition, for a simple closed system of two levels that would give $A_{21} = \tau_2^{-1}$
+ **Absorption**: An atom in the lower level is excited to the upper by a photon of energy $\hbar\omega_{21}$. The rate of this is defined as $n_1B_{12}\rho(\omega_{21})$ where $\rho(\omega_{21})$ is the density of radiation with that frequency. $B_{12}$ is a characteristic rate or the transition.
+ **Stimulated Emission**: When an incident photon of energy $\hbar\omega_{21}$ stimulates an atom in the upper level to decay to the lower by re-emitting a photon of that energy. The rate of this would be $n_2B_{21}\rho(\omega_{21})$ where (you guessed it) $B_{21}$ is a constant characteristic rate of the transition.

The constant characteristic coefficients $A_{21}$, $B_{12}$, and $B_{21}$ are known as *Einstein A and B coefficients* and can descrive transition rates for a two-level system.

<img src="./Figs/EinsteinCoefficents.jpg"/>

As rates are conserved we get...

$$
n_1B_{12}\rho(\omega_{21}) = n_2A_{21} + n_2B_{21}\rho(\omega_{21})
$$

We can rearrange this in terms of spectral energy density and make use of the plank distribution for the spectral energy density to get a couple of useful equations. 

$$
\begin{aligned}
\rho(\omega_{21}) &= \frac{A_{21}}{B_{21}}\frac{1}{\frac{g_1B_{12}}{g_2B_{21}}e^{\beta\hbar\omega_{21}} - 1}\\
\text{and}\\
\rho(\omega_{21}) &= \frac{\hbar}{\pi^2c^3}\frac{\omega_{21}^3}{e^{\beta\hbar\omega_{21} - 1}}\\
\implies g_1B_{12} &= g_2B_{21}\\
\&\ \ A_{21} &= \frac{\hbar\omega_{21}^3}{\pi^2c^3}B_{21}
\end{aligned}
$$


Even though we used a specific form of the spectral energy density these relationships are general! This is because Einstein Coefficients are about the atom not the field. It turns out we can calculate $B_12$

## Line Broadening

So far we've treated our two level system as if it produces monochromatic frequencies, that doesn't really hold up. It actually has some *lineshape* function $g(\omega - \omega_0)$, it's normalised
$$
\int_0^\infty g(\omega-\omega_0)d\omega = 1 
$$
and centred around $\omega_0$

### Einstein Coefficients and Line Broadening

The rates we used to work out our Einstein coefficients are wrong outside of the monocromatic world. The new ones are...

+ Spontaneous Emission - $n_2A_{21}g_A(\omega-\omega_0)d\omega$
+ Absorption - $n_1B_{12}g_B(\omega-\omega_0)\rho(\omega_{21})d\omega$
+ Stimulated Emission - $n_2B_{21}g_{B^\prime}(\omega-\omega_0)\rho(\omega_{21})d\omega$

Note that the lineshapes are all specific to the phenomenon. If we follow the same reasoning we did before we can get a similar relationship.
$$
g_1B_{12}g_B(\omega-\omega_0) = g_2B_{21}g_{B^\prime}(\omega-\omega_0)\\
A_{21}g_A(\omega-\omega_0) = \frac{\hbar\omega_0^3}{\pi^2c^3}B_{21}g_{B^\prime}(\omega-\omega_0)
$$
In thermal equilibrium these must hold over all possible functions so we find that $g_A(\omega-\omega_0) = g_B(\omega-\omega_0) = g_{B^\prime}(\omega-\omega_0) = g_H(\omega-\omega_0)$ where $g_H(\omega-\omega_0)$ is the homogenous lineshape...

### Homogenous Broadening

This is a mechanism which effects all atoms in a sample equally. Generally this produces a *Lorentzian lineshape*.

<div style="text-align:center">
<img src="./Figs/LorentzLineshape.png">
</div>

#### Lifetime Broadening

This can be seen as a product of the uncertainty principle...
$$
\Delta E\Delta t \sim \hbar
$$

Since $E=\hbar\omega$ and $\Delta t \sim \tau$ (the lifetime of the state) we get...
$$
\Delta\omega\tau\sim1\text{ or }\Delta\omega\sim\frac{1}{\tau}
$$
If $\tau$ is more accurately the time taken for a population of that state to decay to $1/\mathcal{e}$ of it's initial value we get a lorenzian lineshape for the intensity of a given $\omega$ and the FWHM $\Delta\omega \sim \frac{2}{\tau}$.

<div style="text-align:center">
<img src="./Figs/LifetimeBroadening.jpg">
</div>


#### Collision or Pressure Broadening

A collision with another atom while the atom is oscillating disrupts the phase of the wave. The number of uninterrupted waves decays exponentially with $\tau_c$ the mean time between collisions so we get another lorentzian lineshape...

<div style="text-align:center">
<img src="./Figs/PressureBroadening.jpg">
</div>

### Inhomogeneous Broadening

Inhomogeneous broadening depends on specific properties of the atoms ($\bold{r}, \bold{v}, m\ \dots$). These typically have a *Gaussian Lineshape*.

#### Doppler Broadening

Atoms in a gas have speeds in a Maxwell-Boltsman distribution (as you'll remember from statistical mechanics). The Doppler shift from this is given by

$$
\omega = \omega_0\bigg(1\pm\frac{v}{c}\bigg)
$$

So the spread is...
$$
\Delta\omega_D \sim\omega_0\frac{v}{c}
$$

<div style="text-align:center">
<img src="./Figs/DopplerBroadening.jpg">
</div>