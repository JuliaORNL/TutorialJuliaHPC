---
layout: default
title: Julia Notebooks
nav_order: 2.4
parent: GrayScott reaction-diffusion 3D solver
---


# Julia on OLCF JupyterHub Open enclave

This is a step-by-step guide

1. `ssh <username>@opendtn.ccs.ornl.gov`

2. Launch Julia:

    ```
    $ /ccsopen/proj/trn017/opt/julia-1.9.0/bin/julia 
                _
    _       _ _(_)_     |  Documentation: https://docs.julialang.org
    (_)     | (_) (_)    |
    _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
    | | | | | | |/ _` |  |
    | | |_| | | | (_| |  |  Version 1.9.0 (2023-05-07)
    _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
    |__/                   |
    ```

3. Create a JupyterHub kernel with IJulia
    
    ```
    julia> using IJulia

    julia> installkernel("Julia (16 threads)", env=Dict("LD_LIBRARY_PATH" => "", "JULIA_NUM_THREADS" => "16"))
    ```

4. The above would create a config file to launch the Julia kernel next time we open [Jupyter OLCF open](https://jupyter-open.olcf.ornl.gov/)

    ```
    $ cat  /ccsopen/home/wfg/.local/share/jupyter/kernels/julia-_16-threads_-1.9/kernel.json 
    {
    "display_name": "Julia (16 threads) 1.9.0",
    "argv": [
        "/autofs/nccsopen-svm1_proj/trn017/opt/julia-1.9.0/bin/julia",
        "-i",
        "--color=yes",
        "/ccsopen/home/wfg/.julia/packages/IJulia/6TIq1/src/kernel.jl",
        "{connection_file}"
    ],
    "language": "julia",
    "env": {
        "LD_LIBRARY_PATH": "",
        "JULIA_NUM_THREADS": "16"
    },
    "interrupt_mode": "signal"
    }
    ```


# Julia's own Pluto.jl

[Pluto.jl](https://github.com/fonsp/Pluto.jl) is Julia's own alternative to using Notebooks. 
It takes advantage of the fact that Julia manages its own packaging ecosystem. It's reactive by nature, so every update in the Pluto notebook would trigger the package manager and there is no need to pre-define an environment.

To trigger Pluto.jl:

```
$ julia
julia> using Pluto
julia> Pluto.run()
```


