# Glycosyltransferase-OPES-MD

**Description:** OPES-MD inputs for studying glycosyltransferase substrate selectivity and intramolecular hydrogen-bond effects.

**Author:** 0xBytefuzz  
**Email:** 0xbytefuzz@gmail.com

## Overview

This repository provides PLUMED input files for running OPES-MD simulations of glycosyltransferase substrate systems.

The main focus is on substrate selectivity and the influence of intramolecular hydrogen bonding on substrate preorganization.

These files are intended for simulation execution only. Trajectory analysis and post-processing workflows are not included.

## Files

| File | Description |
|---|---|
| `S1_plumed.dat` | PLUMED input for the S1 system, focusing on 5-OH preorganization and intramolecular H-bond effects. |
| `S3_plumed.dat` | PLUMED input for the S3 system, focusing on 5-OH preorganization when the alternative site is unavailable or modified. |
| `S2a_O5_channel.dat` | PLUMED input for the Sub2-O5 channel. |
| `S2b_O7_channel.dat` | PLUMED input for the Sub2-O7 channel. |

## Key Collective Variables

The OPES-MD setups mainly use geometry-based collective variables related to:

- nucleophilic approach distance to UDP-Glc C1
- hydroxyl-proton orientation
- nucleophilic attack angle
- proton-transfer angle
- intramolecular hydrogen-bond tendency

For S1 and S3, `diff_H` is used as a geometric tendency descriptor:

```text
diff_H = d(HO5 ... O_intra) - d(N_epsilon(His) ... HO5)
```

In this definition:

- `diff_H < 0` suggests that the hydroxyl proton tends to stay closer to the intramolecular acceptor.
- `diff_H > 0` suggests that the hydroxyl proton tends to orient closer to the catalytic His base.

This descriptor should be interpreted as a trend in hydrogen-orientation preference, not as direct evidence of proton transfer or reaction occurrence.

## Usage

Use the corresponding PLUMED input file with an MD engine that supports PLUMED, such as OpenMM + PLUMED, GROMACS + PLUMED, or other compatible workflows.

Example:

```bash
plumed driver --plumed S1_plumed.dat
```

For production simulations, use the PLUMED file together with the corresponding topology, coordinates, and MD engine settings.

## Note

These input files are designed for enhanced-sampling simulations. Interpretation of substrate selectivity or catalytic relevance requires additional trajectory analysis and free-energy reconstruction.

## Contact

0xBytefuzz  
0xbytefuzz@gmail.com
