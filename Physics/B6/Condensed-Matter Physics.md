# B6 Condensed Matter Physics <!-- omit in toc -->

- [Structure and Types of Bonding](#structure-and-types-of-bonding)
  - [Bonding Types](#bonding-types)
    - [Ionic Bonding](#ionic-bonding)
    - [Covalent Bonding](#covalent-bonding)
    - [Molecular Bonding](#molecular-bonding)
    - [Hydrogen Bonding](#hydrogen-bonding)
  - [Crystals](#crystals)

# Structure and Types of Bonding

## Bonding Types

There are 5 kinds of bonding covered in this course. Here is a table of them...


|      Type of Bonding      | Description                                                                                                                      | Typical Atoms                                                                                     | Typical Properties                                                                                                                                                         |
|:-------------------------:|----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ionic                     | An electron is transferred from one atom to another and the resulting ions attract each other                                    | Binary compounds made of constituents with very different electronegativity. I.e Group I and VII. |  <ul><li>Hard, very brittle</li> <li>High melting temp</li> <li>Electrical Insulators</li> <li>Water soluble</li> </ul>                                                    |
| Covalent                  | An electron is shared equally between two atoms forming a bond. The electron energy is lowered by delocalising the wavefunction. | Solids of only one element or compounds of similar electronegativities.                           | <ul> <li>Very Hard</li> <li>High melting point</li> <li>Electrical insulators or semiconductors</li> </ul>                                                                 |
| Metalic                   | Electrons are delocalised throughout the solid, acting as a bonding agent between the ions.                                      | Metals found on the left and middle of the Periodic table                                         | <ul> <li>Ductile and malleable due to the non-directional nature of the bond</li> <li>Lower melting temperature</li> <li>Good electrical and thermal conductors</li> </ul> |
| Molecular (Van-der-Waals) | There is no electron transfer. Instead the dipole moments of constituents align causing an attraction between the molecules.     | Noble gas solids, or solids made of slightly polar molecules.                                     | <ul> <li>Soft and weak (like Megan)</li> <li>Low melting temperature</li> <li>Electrical Insulators</li> </ul>                                                             |
| Hydrogen                  | Involves a $H^+$ ion bound to one atom but still attracted to the other.                                                         | Organic and biological materials.                                                                 | <ul> <li>Weak bond (but stronger than molecular)</li> <li>Important for maintaining the shape of DNA and proteins</li> </ul>                                               |

### Ionic Bonding

In ionic bonds an electron is transferred from one atom to another and the resulting ions are attracted to one another. To describe this we need three terms...

+ *Ionisation energy* the energy cost to ionise the atom which forms positive ion.
+ *Electron Affinity* the energy released by the formation of the negative ion.
+ *Cohesive Energy* the energy released on forming the bond.

The change in energy is then...

$$
\Delta E = \text{Electron Affinity} + \text{Cohesive Energy} - \text{Ionisation Energy}
$$

We require that this is positive for the bond to form (i.e that energy will be released) Electron Affinity and Ionisation Energy have to be experimentally calculated but we can approximate cohesive energy using the coulomb attraction...
$$
\text{Cohesive Energy} \approx \frac{e^2}{4\pi\epsilon_0R}
$$

This actually leads to an **overestimation of $\Delta E$** as it ignores the interaction of the electron clouds when the atoms get very close.

<div style="text-align:center">
<img src="./Figs/Ionic.jpg">
</div>

### Covalent Bonding

Covalent bonding is when an electron is shared between two similar atoms. We can imagine this electron having the Hamiltonian...

$$
H = T + V_1 + V_2\\\ \\
T = \frac{\bold{p}^2}{2m_e}\\\ \\
V_i = \frac{e^2}{4\pi\epsilon_0|\bold{r}-\bold{R}_i|}
$$

For a state of the form
$$
|\psi\big> = \phi_1|1\big> + \phi_2|2\big>
$$

Where $|1\big>$ and $|2\big>$ are the states an electron localised in each nucleus. This gives...

$$
H = \begin{pmatrix}
    E_0 + V_c   & -t\\
    -t^*        & E_0 + V_c
\end{pmatrix}
$$

Where
$$
\begin{aligned}
E_0 &= \big<1|T + V_1|1\big> = \big<2|T + V_2|2\big>\\
V_c &= \big<1|V_2|1\big> = \big<2|V_1|2\big>\\
t &= \big<1| H | 2\big>
\end{aligned} 
$$

$E_0$ is the hydrogenic energy of an electron in a single nucleus, $V_c$ is the *cross-term* energy associated with an electron in orbital $|1\big>$ feel the attraction of the other nucleus and vice versa, t is the *hopping term*, the energy associated with moving between orbitals. The solution of this hamiltonian is...
$$
E_\pm = E_0 + V_c \pm |t|
$$

Since we expect a cancellation of the coulomb attraction from an atom outside of it we can ignore $V_c$ so long as the atoms are sufficiently far apart. So we have...

$$
E_\pm \approx E_0 \pm |t|
$$

So for the lower energy eigenstate it's energetically favourable to form a bond. The eigendtates are...

$$
|\psi_\pm\big> = \frac{1}{\sqrt{2}}(|1\big>\pm|2\big>) 
$$

They correspond to more and less separated atoms respectively.

### Molecular Bonding

*Van-der-Waals bonding* is a result of electric dipoles of two molecules aligning to attract one another. For two atoms separated by $r = |\bold{r}|$ where the first has a dipole moment $\bold{p}_1$. Then the second feels an electric field...
$$
\bold{E} = \frac{|\bold{p}_1|^2}{4\pi\epsilon_0}\frac{\hat{\bold{r}}}{r^3}
$$

The second atom then has polarisation $\bold{p}_2 = \chi_e\bold{E}$ as a result. The PE due to this interaction then is...
$$
U(r) = -\bold{p}_2\cdot\bold{E} = -\frac{|\bold{p}_1|^2\chi_e}{(4\pi\epsilon_0)^2}\frac{1}{r^6}
$$

This means that the force due to the bond $\bold{F} = -\nabla U \propto r^{-7}$ this quickly drops off with seperation which is why this is such a weak form of bonding.

### Hydrogen Bonding

Non-Examinable

## Crystals

