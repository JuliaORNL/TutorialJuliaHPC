---
layout: default
title: Julia Notebooks
nav_order: 2.5
parent: GrayScott reaction-diffusion 3D solver
---


# Julia on OLCF JupyterHub Open enclave

This is a step-by-step guide

1. ssh into odo: `ssh <username>@login1.odo.olcf.ornl.gov`

2. Clone Gray-Scott repository in your home directory.

    ```
    $ git clone https://github.com/JuliaORNL/GrayScott.jl.git
    ```

3. Source the script to set up the environment, modules, and packages. This is a one-time step and might take a few minutes.
    
    ```bash
    $ source GrayScott.jl/Notebooks/Plot2D.jl/config_Odo_IJulia_kernel.sh
    ```

4. The above would create a config file to launch the Julia kernel next time we open [Jupyter OLCF open](https://jupyter-open.olcf.ornl.gov/)

    ```
    $ cat /ccsopen/home/wgodoy/.local/share/jupyter/kernels/julia-24threads_-1.10/kernel.json 
    {
      "display_name": "Julia-24threads) 1.10.4",
      "argv": [
      "/autofs/nccsopen-svm1_sw/odo/julia-1.10.4/bin/julia",
      "-i",
      "--color=yes",
      "/ccsopen/home/wgodoy/.julia/packages/IJulia/Vo51o/src/kernel.jl",
      "{connection_file}"
      ],
      "language": "julia",
      "env": {
         "LD_LIBRARY_PATH": "",
         "JULIA_NUM_THREADS": "24"
      },
      "interrupt_mode": "signal"
    }
    ```

5. Log into [Jupyter OLCF open](https://jupyter-open.olcf.ornl.gov/) and select the kernel `Julia-24threads) 1.10.4` to start a new notebook. Example provided in [GrayScott.jl/Notebooks/Plot2D.jl/src/Julia-reading.ipynb](https://github.com/JuliaORNL/GrayScott.jl/blob/GrayScott-JACC/Notebooks/Plot2D.jl/src/Julia-reading.ipynb). Package dependencies need to be precompiled on the first run, instantiate: `GrayScott-JACC/Notebooks/Plot2D.jl/Project.toml`.

6. Copy the generated bp file to `/ccs/open/home/<username>`
   
7. Modify and execute the [Plot2D.ipynb notebook](https://github.com/JuliaORNL/GrayScott.jl/blob/main/Notebooks/Plot2D.jl/src/Plot2D.ipynb) - it might take a while.

# Julia's own Pluto.jl

[Pluto.jl](https://github.com/fonsp/Pluto.jl) is Julia's own alternative to using Notebooks. 
It takes advantage of the fact that Julia manages its own packaging ecosystem. It's reactive by nature, so every update in the Pluto notebook would trigger the package manager and there is no need to pre-define an environment.

To trigger Pluto.jl:

```
$ julia
julia> using Pluto
julia> Pluto.run()
```


