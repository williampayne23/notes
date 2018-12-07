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
    - [LS-Coupling](#ls-coupling)

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



## LS-Coupling

In these notes we assume LS-Coupling because it's super convenient and I like it. In LS coupling $\bold{J}= \bold{L} +\bold{S}$ which in vector model terms means that $\bold{L}$ and $\bold{S}$ couple to precess around $\bold{J}$ which makes $L,S,J,$ and $M_J$ good quantum numbers but $M_L$ and $M_S$ obviously not.

<img src="./Figs/LSCoupling.jpg" alt="Figure Missing"/>