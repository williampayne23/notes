# B6 Condensed Matter Physics <!-- omit in toc -->

- [Structure and Types of Bonding](#structure-and-types-of-bonding)
  - [Bonding Types](#bonding-types)
    - [Ionic Bonding](#ionic-bonding)
    - [Covalent Bonding](#covalent-bonding)
    - [Molecular Bonding](#molecular-bonding)
    - [Hydrogen Bonding](#hydrogen-bonding)
- [Crystals](#crystals)
  - [Crystal Structure](#crystal-structure)
    - [Lattices](#lattices)
    - [The Unit Cell](#the-unit-cell)
    - [Lattices in 3D](#lattices-in-3d)
      - [The Body Centred Cubic (BCC) Lattice](#the-body-centred-cubic-bcc-lattice)
      - [The Face Centred Cubic (FCC) Lattice](#the-face-centred-cubic-fcc-lattice)
      - [Bravais Lattice Types](#bravais-lattice-types)
  - [The Reciprocal Lattice](#the-reciprocal-lattice)
    - [The Reciprocal Lattice as a Fourier Transform.](#the-reciprocal-lattice-as-a-fourier-transform)
    - [The Reciprocal Lattice as Families of Lattice Planes](#the-reciprocal-lattice-as-families-of-lattice-planes)
      - [Miller Indices](#miller-indices)
    - [Brillouin Zones](#brillouin-zones)

# Structure and Types of Bonding

## Bonding Types

There are 5 kinds of bonding covered in this course. Here is a table of them...


|      Type of Bonding      | Description                                                                                                                      | Typical Atoms                                                                                     | Typical Properties                                                                                                                                                         |
| :-----------------------: | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|           Ionic           | An electron is transferred from one atom to another and the resulting ions attract each other                                    | Binary compounds made of constituents with very different electronegativity. I.e Group I and VII. | <ul><li>Hard, very brittle</li> <li>High melting temp</li> <li>Electrical Insulators</li> <li>Water soluble</li> </ul>                                                     |
|         Covalent          | An electron is shared equally between two atoms forming a bond. The electron energy is lowered by delocalising the wavefunction. | Solids of only one element or compounds of similar electronegativities.                           | <ul> <li>Very Hard</li> <li>High melting point</li> <li>Electrical insulators or semiconductors</li> </ul>                                                                 |
|          Metalic          | Electrons are delocalised throughout the solid, acting as a bonding agent between the ions.                                      | Metals found on the left and middle of the Periodic table                                         | <ul> <li>Ductile and malleable due to the non-directional nature of the bond</li> <li>Lower melting temperature</li> <li>Good electrical and thermal conductors</li> </ul> |
| Molecular (Van-der-Waals) | There is no electron transfer. Instead the dipole moments of constituents align causing an attraction between the molecules.     | Noble gas solids, or solids made of slightly polar molecules.                                     | <ul> <li>Soft and weak (like Megan)</li> <li>Low melting temperature</li> <li>Electrical Insulators</li> </ul>                                                             |
|         Hydrogen          | Involves a $H^+$ ion bound to one atom but still attracted to the other.                                                         | Organic and biological materials.                                                                 | <ul> <li>Weak bond (but stronger than molecular)</li> <li>Important for maintaining the shape of DNA and proteins</li> </ul>                                               |

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

# Crystals

> Be warned this section is heavy on it's definitions.

## Crystal Structure

### Lattices


A **lattice** is an infinite set of points defined by integer sums of linearly independent primitive lattice vectors. In three dimensions we have the lattice...

$$
\bold{R}_{[n_1, n_2, n_3]} = n_1\bold{a_1} + n_2\bold{a_2} + n_3\bold{a_3}
$$

<div style="text-align:center">
<img src="./Figs/Lattice.jpg" height=200>
</div>


Another useful definition is that a lattice is a set of points for which the environment of any one point is identical to the environment of all the others.

This means that something like a honeycomb is definitely not a lattice...

<div style="text-align:center">
<img src="./Figs/Honeycomb.jpg" height=200><br/>
<span>Here R and P do not have identical environments.</span>
</div>

To describe the honeycomb and other similar structures we need to define the unit cell.

### The Unit Cell

A **Unit Cell** is a region of space such that when many identical unit cells are stacked together in tiles it completely fills and reconstructs the full structure. Ideally we want the smallest possible cell.

A **Primitive Unit Cell** is a unit cell containing only one point.

Sometimes we have a **conventional cell** which is not primitive but easier to work with for whatever reason (usually orthogonal axes).

Finally we have the Wigner-Seitz cell which is a cell constructed by the rule "Given a lattice point all space closer to that cell than any other lattice points constitutes the Wigner-Seitz cell". A good way to do this is to draw bisectors of lines to all neighbouring cells and those lines will border the Weigner-Seitz cell.

<div style="text-align:center">
<img src="./Figs/UnitCells.jpg" height=200>
<br/>
A diagram of unit cells
</div>

The description of objects within a unit cell is known as a basis.

<div style="text-align:center">
<img src="./Figs/CellBasis.jpg" height=200>
<br/>
An example of a basis
</div>

### Lattices in 3D

When we describe a 3D lattice we can represent a given vector out of the lattice vectors as

$$
[uvw] = u\bold{a}_1 + v\bold{a_2} + w\bold{a_3}
$$

For orthogonal bases we assume $\bold{a}_{1,2,3}$ corresponds to $\bold{\hat{x}}, \bold{\hat{y}}, \bold{\hat{z}}$ in this course we'll only deal with orthogonal bases according to the lecture notes.

The simplest 3D lattice is the cubic lattice which has the primitive unit cell of a cube. This is not really that common as arranging atoms along that basis is energetically unfavourable because it leaves a lot of space in the middle.

The next most complicated are the tetragonal and orthorhombic lattices which have unit cells which are basically just cuboids.

<div style="text-align:center">
<img src="./Figs/TetragonalOrthombic.jpg" height=200>
<br/>
Unit Cells for orthorhombic and tetragonal lattices left and right.
</div>

#### The Body Centred Cubic (BCC) Lattice

This is a cubic lattice with an additional point at the very center of the cube.

One way to think of the BCC lattice is as a cubic lattice with a unit cell containing two points.

<div style="text-align:center">
<img src="./Figs/BCCLattice.jpg" height=200>
<br/>
BCC lattice and a unit cell for a cubic lattice which would describe it.
</div>

This would have the basis...
$$
\begin{aligned}
\bold{R}_\text{corner} &= [u,v,w]\\
\bold{R}_\text{middle} &= [u,v,w] + [a/2,a/2,a/2]
\end{aligned}
$$

but if the atoms are all the same it can be fully described by the primitive lattice vectors...

$$
\begin{aligned}
\bold{a_1} &= [a,0,0]\\
\bold{a_2} &= [0,a,0]\\
\bold{a_3} &= [\frac{a}{2},\frac{a}{2},\frac{a}{2}]
\end{aligned}
$$

The BCC lattice has the Wigner-Seitz cell...

<div style="text-align:center">
<img src="./Figs/BCCWigner.jpg" height=200>
<br/>
The Wigner-Seitz cell for BCC
</div>

#### The Face Centred Cubic (FCC) Lattice

The FCC lattice has a point at the center of each face. It can similarly be described as a cubic lattice with a conventional unit cell containing four points...

<div style="text-align:center">
<img src="./Figs/FCCLattice.jpg" height=200>
<br/>
The FCC Latice
</div>

The basis for that cell would be...

$$
\begin{aligned}
&\bold{R}_\text{corner} &= &[u,v,w]\\
&\bold{R}_\text{face-xy} &= &[u,v,w] + [a/2,a/2,0]\\
&\bold{R}_\text{face-xz} &= &[u,v,w] + [a/2,0,a/2]\\
&\bold{R}_\text{face-yz} &= &[u,v,w] + [0,a/2,a/2]\\
\end{aligned}
$$

And if we wanted to define this fully with orthogonal primitive lattice vectors we would have

$$
\begin{aligned}
  \bold{a}_1 &= [a/2,a/2,0]\\
  \bold{a}_2 &= [a/2,0,a/2]\\
  \bold{a}_3 &= [0,a/2,a/2]\\
\end{aligned}
$$

#### Bravais Lattice Types

There are more types but we don't need to know much about them...

<div style="text-align:center">
<img src="./Figs/bravais.jpg">
<br/>
Bravais Lattice Types
</div>

## The Reciprocal Lattice

The Reciprocal lattice is sort of like it sounds (an inverse to the lattice) but has the more intense definition of...

Given a direct lattice of points $\bold{R}$ a point $\bold{G}$ is in the reciprocal lattice if
$$
e^{i\bold{G}\cdot\bold{R}}=1
$$
for all points $\bold{R}$ in the lattice.

If we say...
$$
R = u\bold{a}_1 + v\bold{a}_2 + w\bold{a}_3\\
G = h\bold{b}_1 + k\bold{b}_2 + l\bold{b}_3\\
\implies \bold{a}_i\cdot\bold{b}_j = 2\pi\delta_{ij}\\
\&\ h,k,l \subset \Z
$$

For this to work we get...

$$
\bold{b}_1 = \frac{2\pi\bold{a}_2\times\bold{a}_3}{\bold{a_1}\cdot(\bold{a}_2\times\bold{a}_3)}\\
\bold{b}_2 = \frac{2\pi\bold{a}_3\times\bold{a}_1}{\bold{a_1}\cdot(\bold{a}_2\times\bold{a}_3)}\\
\bold{b}_3 = \frac{2\pi\bold{a}_1\times\bold{a}_2}{\bold{a_1}\cdot(\bold{a}_2\times\bold{a}_3)}\\
$$

### The Reciprocal Lattice as a Fourier Transform.

Let the density of atoms be $\rho(\bold{r})$. This is clearly periodic in the lattice vector $\rho(\bold{r}) = \rho(\bold{r} + \bold{R})$. We can get the fourier transform...

$$
\tilde{\rho}(\bold{k}) = \int d^3\bold{r}e^{i\bold{k}\cdot\bold{r}\rho(\bold{r})}
$$

Since this is periodic we can write this integral as...

$$
\begin{aligned}
\tilde{\rho}(\bold{k}) &= \sum_{\bold{R}}\int_\text{unit cell} d^3\bold{x}e^{i\bold{k}\cdot(\bold{x+R})}\rho(\bold{x+R})\\
&= \sum_\bold{R} e^{i\bold{k}\cdot\bold{R}}\int_\text{unit cell}d^3\bold{x}e^{i\bold{k}\cdot(\bold{x})}\rho(\bold{x})
\end{aligned}
$$

Where $\bold{x}$ is a vector describing position within the unit cell. We know that $e^{i\bold{k}\cdot\bold{R}}$ will only have a value if $\bold{k}$ is on the reciprocal lattice so we get...

$$
\tilde{\rho}(\bold{k}) = (2\pi)^3\sum_\bold{G} \delta^3(\bold{k}-\bold{G})S(\bold{k})\\
S(\bold{k}) = \int_\text{unit cell}d^3\bold{x}e^{i\bold{k}\cdot(\bold{x})}\rho(\bold{x})
$$

Where $S(\bold{k})$ is the *Structure Factor*

### The Reciprocal Lattice as Families of Lattice Planes

A **Lattice Plane** is a place containing three or more noncolinear points in the lattice (this condition actually means it has to contain an infinite number)

A **Family of Lattice Planes** is a infinite set of equally spaced lattice planes which together contain all points in the lattice.

<div style="text-align:center">
<img src="./Figs/LatticePlanes.jpg" height=200>
<br/>
Two examples of families of lattice planes
</div>

If we define a lattic plane by the points $\bold{r}$ such that...

$$
\bold{G}\cdot\bold{r} = 2\pi m
$$

Where m is an integer we have an infinite set of planes normal to $\bold{G}$. Since $e^{i\bold{G}\cdot\bold{r}} = 1$ by this definition we know that every point is on this family of planes! The distance between planes can be found using $\bold{r}_1$ and $\bold{r}_2$ defined as being on adjacent planes.
$$
\bold{G}\cdot\bold{r}_1 = 2\pi m\\
\bold{G}\cdot\bold{r}_2 = 2\pi n\\
\bold{G}\cdot(\bold{r}_1-\bold{r}_2)= 2\pi(m-n)= 2\pi\\

d = |\bold{r}_1-\bold{r}_2|= \frac{2\pi}{|\bold{G}|}\\
$$

To find the maximum possible separation for a given direction in the reciprocal lattice we only need to use the smallest possible $\bold{G}$ as all possible reciprocal lattice vectors will give a valid family of lattice planes but the longer the vector the more dense the planes.
$$
d_\text{max} = \frac{2\pi}{|\bold{G}_\text{min}|}\\
$$

#### Miller Indices

If a reciprocal lattice vector for a lattice plane is defined as 
$$
\bold{G}_{hkl} = h\bold{b}_1 + k\bold{b}_2 + l\bold{b}_3
$$
Then the lattice plane can be defined with the *Miller Indices*

$$
[hkl]
$$

> NOTE: For fcc and bcc latices the miller indices are defined by the primitive lattice vectors of the cubic lattice.

You can write the spacing between planes in terms of miller indices... 

$$
d_{(hkl)} = \frac{2\pi}{|\bold{G}|} = \frac{2\pi}{\sqrt{h^2|\bold{b}_1|^2 + k^2|\bold{b}_2|^2 + l^2|\bold{b}_3|^2}}
$$

For orthogonal axes we have $|\bold{b}_i| = \frac{2\pi}{|\bold{a}_i|}$ so...

$$
\frac{1}{|d_(hkl)|^2} = \frac{h^2}{a_1^2} + \frac{k^2}{a_2^2} + \frac{l^2}{a_3^2}
$$

Finally for a cubic lattice $a_1=a_2=a_3=a$ so...
$$
d_{(hkl)}^\text{cubic} = \frac{a}{\sqrt{h^2 + k^2 + l^2}}
$$

### Brillouin Zones

For now we can define the brillouin zone as the unit cell of the reciprocal lattice.

Centred on lattice point $\bold{0}$ we can say the first brillouin zone is defined as being the area of all points closer to $\bold{0}$ than any other lattice point. The second brillouin zone is the area of all points where $\bold{0}$ is the second closest lattice points, and so on.

We construct brillouin zones with the Wigner-Seitz construction. The first is bounded by bisectors of the nearest neighbouring points. The second is bounded by bisectors of the next nearest and so on. 

<div style="text-align:center">
<img src="./Figs/BrillouinZones.jpg" height=200>
<br/>
An example of constructing Brillouin Zones
</div>
