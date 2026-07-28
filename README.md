# PLUMED-Enhanced-Sampling

## Overview

This directory contains PLUMED input files and configuration examples for enhanced-sampling molecular dynamics simulations.

The purpose of this collection is to record and organize enhanced-sampling setups, collective variable (CV) definitions, and biasing strategies used in molecular dynamics simulations.

The provided files serve as references for:

- PLUMED input construction
- collective variable design
- enhanced-sampling setup
- biasing strategy selection
- simulation workflow organization

These examples can be adapted and modified for different molecular dynamics systems.

---

## Methods

The input files are mainly based on enhanced-sampling methods implemented in PLUMED, including:

- OPES (On-the-fly Probability Enhanced Sampling)
- Metadynamics-based approaches
- Other PLUMED-supported biasing methods

The selection of enhanced-sampling methods and collective variables depends on the molecular process being investigated.

---

## Collective Variables

The collective variables (CVs) used in these examples are mainly based on structural and geometric descriptors, including:

- interatomic distances
- hydrogen-bond related coordinates
- coordination numbers
- dihedral angles
- molecular orientation descriptors
- conformational state descriptors
- reaction-related geometric parameters

Common CV examples:

```text
Distance:

d(atom1, atom2)


Angle:

θ(atom1, atom2, atom3)


Dihedral:

φ(atom1, atom2, atom3, atom4)
```

Composite CVs can also be constructed to describe competing interactions or conformational preferences.

Example:

```text
CV = d1 - d2
```

Such descriptors represent molecular structural tendencies and conformational preferences. Additional analysis is required for mechanistic interpretation.

---

## Directory Structure

Example:

```
PLUMED-Enhanced-Sampling/

├── OPES/
│   ├── system_1/
│   │   └── plumed.dat
│   │
│   └── system_2/
│       └── plumed.dat
│
├── Metadynamics/
│
└── README.md
```

---

## Usage

The PLUMED input files can be used with molecular dynamics engines supporting PLUMED, including:

- OpenMM + PLUMED
- GROMACS + PLUMED
- other compatible MD engines

Example:

```bash
plumed driver --plumed plumed.dat
```

For production simulations, the PLUMED input file should be combined with the corresponding:

- topology files
- coordinate files
- molecular dynamics parameters
- simulation environment

---

## Notes

Enhanced-sampling simulations require careful evaluation of:

- sampling convergence
- free-energy reconstruction
- collective variable suitability
- biasing behavior

The interpretation of simulation results should be supported by appropriate trajectory analysis and structural characterization.

This directory mainly records simulation inputs, CV definitions, and methodological references. Analysis scripts and post-processing workflows are maintained separately.

---

## References

### PLUMED

PLUMED documentation:

https://www.plumed.org/


### OPES

Invernizzi, M.  
On-the-fly probability enhanced sampling (OPES).  
*Journal of Chemical Theory and Computation.*


### Metadynamics

Laio, A.; Parrinello, M.  
Escaping free-energy minima.  
*Proceedings of the National Academy of Sciences.*

---

## Contact

0xBytefuzz

Email: 0xbytefuzz@gmail.com
