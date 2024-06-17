---
layout: default
title: Running Gray-Scott on Odo/Frontier
nav_order: 2.4
parent: GrayScott reaction-diffusion 3D solver
---

# Running Gray-Scott on Odo/Frontier

This instructions are for the [Odo training system at OLCF](https://docs.olcf.ornl.gov/systems/odo_user_guide.html). Which is identical to [Frontier](https://docs.olcf.ornl.gov/systems/frontier_user_guide.html).

We assume the user has access to `trn023` training account

0. Access Odo/Frontier

    ```
    $ ssh USERNAME@login1.odo.olcf.ornl.gov
    ```

1. Obtain Gray-Scott, first access your scrath directory, clone the repository poiting at the GrayScott-JACC branch. Replace wgodoy with your username.

    ```
    cd /gpfs/wolf2/olcf/trn023/scratch/wgodoy
    mkdir tutorial
    cd tutorial
    git clone https://github.com/JuliaORNL/GrayScott.jl.git
    git checkout -b GrayScott-JACC origin/GrayScott-JACC
    ```

2. Install package dependencies in Julia REPL

  - Script prepared for this tutorial [`GrayScott.jl/scripts/config_odo.sh`](https://github.com/JuliaORNL/GrayScott.jl/blob/GrayScott-JACC/scripts/config_odo.sh). Run it with `source config_odo.sh`.

    ```bash
     #!/bin/bash

     # Change the first 3 lines appropriately
     PROJ_DIR=/gpfs/wolf2/olcf/trn023/scratch/wgodoy/tutorial
     export JULIA_DEPOT_PATH=$PROJ_DIR/.julia
     GS_DIR=$PROJ_DIR/GrayScott.jl

     # remove existing generated Manifest.toml
     rm -f $GS_DIR/Manifest.toml
     rm -f $GS_DIR/LocalPreferences.toml

     # good practice to avoid conflicts with existing default modules
     module purge

     # load required modules
     module load PrgEnv-gnu-amd/8.4.0
     module load cray-mpich
     module load adios2/2.9.2
     module load julia/1.10.4
     # point at current Julia installation until module is available on Odo
     # export PATH=/gpfs/wolf2/olcf/trn023/world-shared/opt/julia-1.10.3/bin:$PATH

     # Required to point at underlying modules above
     export JULIA_ADIOS2_PATH=$OLCF_ADIOS2_ROOT

     # MPIPreferences to use Cray's MPICH
     julia --project=$GS_DIR -e 'using Pkg; Pkg.add("MPIPreferences")'
     julia --project=$GS_DIR -e 'using MPIPreferences; MPIPreferences.use_system_binary(mpiexec="srun", vendor="cray")'

     # Set up underlying rocm
     # this will polute Project.toml with AMDGPU.jl
     julia --project=$GS_DIR -e 'using Pkg; Pkg.add("AMDGPU")'

     export ROCM_PATH=/opt/rocm-5.3.0
     # adds an entry to LocalPreferences.toml
     julia --project=$GS_DIR -e 'using AMDGPU; AMDGPU.ROCmDiscovery.use_artifacts!(false)'

     # Instantiate the project by installing packages in Project.toml
     julia --project=$GS_DIR -e 'using Pkg; Pkg.instantiate()'
     # Verify the packages are installed correctly
     julia --project=$GS_DIR -e 'using Pkg; Pkg.build()'
     # JACC.jl and GrayScott.jl won't precompile, but other packages will
     julia --project=$GS_DIR -e 'using Pkg; Pkg.precompile()'

     # Set jacc-amdgpu as the backend in LocalPreferences.toml
     julia --project=$GS_DIR -e 'using GrayScott.GrayScottPreferences; GrayScottPreferences.set_backend("jacc-amdgpu")'
    ```

    
  {: .info }
  JULIA_DEPOT is where Julia packages and artifacts (e.g. extra data) will be installed for different local environments. Project/system admins should prefer a global installation of commonly used packages: MPI.jl, CUDA.jl, Plots.jl, etc. due to their size to avoid multiple copies.


3. Verify Julia v1.10.4 
    
    ```
    julia --version
    ```

4. Run Gray-Scott submitting a job

  - Script prepared for this tutorial [`GrayScott.jl/scripts/job_odo.sh`](https://github.com/JuliaORNL/GrayScott.jl/blob/GrayScott-JACC/scripts/job_odo.sh)

  - The [GrayScott.jl/examples/settings-files.json](https://github.com/JuliaORNL/GrayScott.jl/blob/GrayScott-JACC/examples/settings-files.json) allows to run different jobs for different size problems.

  - Set up the above files and run, in a separate directory, `sbatch job_odo.sh`

