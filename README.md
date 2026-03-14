# Machine Learning Potential for Cs--FA Mixed-Cation Halide Perovskites

This repository provides the **machine learning potential (MLP)** and
**LAMMPS input files** for molecular dynamics simulations of **halide
perovskites with mixed A-site cations (Cs and FA)**.

------------------------------------------------------------------------

## Software Environment

To avoid potential issues caused by different software versions, it is
recommended to use the **Singularity image of DeepMD-kit**.

The simulations can be performed using the **integrated LAMMPS**
included in:

deepmd-kit_3.0.0a0_cuda118

------------------------------------------------------------------------

## Running the Simulation

Use the following command to run LAMMPS with the DeepMD-kit Singularity
image:

``` bash
singularity exec --nv ${path_to_image}/deepmd-kit_3.0.0a0_cuda118.sif lmp -in input.lammps
```

Replace `${path_to_image}` with the directory containing the Singularity
image file.

------------------------------------------------------------------------

## Recovering the Potential File

The potential file `PbI.pb` is split into multiple parts.

Before running the simulation, reconstruct it using:

``` bash
cat PbI.pb.part_* > PbI.pb
```

------------------------------------------------------------------------

## File Description

  File              Description
  ----------------- ----------------------------------------------
  input.lammps      Example LAMMPS input file for MD simulations
  
  PbI.pb.part\_\*   Split machine learning potential files
  
  PbI.pb            Reconstructed DeepMD potential file
