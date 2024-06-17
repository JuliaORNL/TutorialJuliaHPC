---
layout: default
title: Running Gray-Scott on Summit/Ascent
nav_order: 2.3
parent: GrayScott reaction-diffusion 3D solver
---

# Running Gray-Scott on Summit/Ascent

This instructions are for the [Ascent training system at OLCF](https://docs.olcf.ornl.gov/systems/ascent_user_guide.html). Which is identical to [Summit](https://docs.olcf.ornl.gov/systems/summit_user_guide.html).

We assume the user has access to `trn017` training account

1. Load and verify Julia v1.9 
    
    ```
    module load julia
    julia --version
    ```

2. Obtain Gray-Scott

    ```
    cd $PROJWORK/trn017
    mkdir $USER
    cd $USER
    git clone https://github.com/JuliaORNL/GrayScott.jl.git
    ```
   
3. Install package dependencies in Julia REPL

  - Scripts prepared for this tutorial `cd GrayScott.jl/scripts`

  - The first line setup a `JULIA_DEPOT_PATH`, otherwise `~/.julia` is selected by default which is not recommended due to small available space. The second assumes GrayScott.jl was cloned under `$USER`.

    ```
    export JULIA_DEPOT_PATH=$PROJWORK/trn017/$USER/julia_depot
    GS_DIR=$PROJWORK/trn017/$USER/GrayScott.jl
    ``` 
  
  {: .info }
  JULIA_DEPOT is where Julia packages and artifacts (e.g. extra data) will be installed for different local environments. Project/system admins should prefer a global installation of commonly used packages: MPI.jl, CUDA.jl, Plots.jl, etc. due to their size to avoid multiple copies.

