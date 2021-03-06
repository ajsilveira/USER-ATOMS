# USER-ATOMS

USER-ATOMS is a LAMMPS user package developed at ATOMS/UFRJ

-------------------------------------------------------------------------------
# Installation

1) Download and install [LAMMPS](http://lammps.sandia.gov) from their website.

2) Go to the LAMMPS source directory (src) and run the following commands:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    git clone https://github.com/atoms-ufrj/USER-ATOMS
    make yes-USER-ATOMS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

3) Proceed with normal [LAMMPS](http://lammps.sandia.gov) compilation.

--------------------------------------------------------------------------------
# Included features

### 1) Pair style lj/sf/coul/sf

__Syntax__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    pair_style lj/sf/coul/sf cutoff (cutoff2)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* cutoff = global cutoff for Lennard-Jones interactions (distance units)
* cutoff2 = global cutoff for Coulombic interactions (optional) (distance units)

__Examples__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    pair_style lj/sf/coul/sf 10.0
    pair_style lj/sf/coul/sf  8.0 10.0
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

__Description__:

The pair style _lj/sf/coul/sf_ computes the shifted-force version of a combined
Lennard-Jones/Coulombic pair potential.

### 2) Compute style ke/com

__Syntax__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    compute ID group ke/com
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

__Example__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    compute KinEngCoM all ke/com
    thermo_style custom step temp pe ke c_KinEngCoM
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

__Description__:

The compute style _ke/com_ computes the translational part (that is, based on
the center-of-mass velocities) of the kinetic energy. The center of mass of each
molecule is computed considering only those atoms that belong to the specified
group.

### 3) Fix style msd/chunk

__Syntax__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    fix ID group msd/chunk chunkID nEvery blockSize file nUpdate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* chunkID = 
* nEvery = 
* blockSize = 
* file = 
* nUpdate = 

__Example__:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    compute mols all chunk/atom molecule
    fix     msd all msd/chunk mols 20 10 msd.dat 10000
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

__Description__:


