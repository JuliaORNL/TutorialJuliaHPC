---
layout: default
title: Introduction
nav_order: 1
---

# Welcome to the Julia for High-performance Computing Tutorial

## Goal

The goal of the tutorial is to introduce an audience familiar with high-performance computing (HPC) concepts to the Julia programming language using a hands-on approach.

{: .info}
It's a good time to get the latest Julia installed from their [website](https://julialang.org/downloads/)

## Covered:
- Workflow aspects: simulation CPU/CPU, parallel I/O, data analysis (e.g. Notebooks)
- Multiple dispatch for array back ends (CPU, GPU: CUDA, AMDGPU)
- Multithreaded CPU using Julia @threads
- GPU programming using vendor (CUDA.jl, AMDGPU.jl) and performance portable layer (JACC.jl, KernelAbstractions.jl)
- Parallel I/O with ADIOS2.jl (outputs can be visualized in ParaView locally)
- Julia on OLCF's JupyterHub and Pluto.jl Notebooks (read and plot using Makie.jl)

## Not Covered (future topics?):
- More general aspects of the language (software engineering, AI)
- AI infrastructure: Flux.jl, SciML
- Ahead-of-time compilation: PackageCompiler.jl
- Tools ecosystem for profiling, debugging (well some vendor supported)

# Why Julia?

{: .highlight }
"Can a machine translate a sufficiently rich mathematical language into a suffienciently economical program at a sufficiently low cost to make the whole affair feasible?" 
-- John Backus on Fortran (1980)

1. Compiled via LLVM for performance. **Julia is Compiled**
2. Provides a unified **tested** ecosystem (packaging, testing, tools, interactivity, etc.). See JuliaCon [presentation](https://www.youtube.com/watch?v=9YWwiFbaRx8) on GeneralRegistry.
3. Community of HPC people from day-1 (the community is you, low entry barrier)
4. Sustained by [JuliaHub](https://juliahub.com/), MIT's JuliaLab, NumFocus and several open-source [contributors](https://julialang.org/blog/2019/02/julia-entities/)
5. Great math (Fortran) and data science (Python) simple syntax
6. Rapid prototyping: stay in one language+ecosystem for your custom kernels + data analysis
7. Interoperate with Fortran, C, C++ (via C), Python, R code in a lightweight manner
8. Renewed interest for high-performance + high-productivity languages
9. Great first language to expose newcomers to both HPC + math concepts
10. Contribute to HPC stack: MPI.jl, CUDA.jl, AMDGPU.jl, KernelAbstractions.jl, JACC.jl, ADIOS2.jl, HDF5.jl...for us, by us

![](images/Blog_2303_julia_value_proposition.png)**Julia's value proposition**

# Why not Julia?

1. Already existing infrastructure/expertise (Fortran is perfect!)
2. Too much of an investment to learn a new language
3. Performance/productivity solutions already in place
4. Having N-language/ecosystems is not a problem
5. Python + X is well supported for your needs
6. Garbage collection, Just-in-time (JIT) compilation are issues
7. Developing low-level system libraries
8. Domain outside "technical computing"
9. Overall, you do not see any value added

## Resources

1. [Julia's value proposition for Better Scientific Software](https://bssw.io/blog_posts/julia-s-value-proposition-for-better-scientific-software). High-level intro and many resources for Scientific Software.

2. [Bridging HPC Communities through the Julia Programming Language](https://arxiv.org/abs/2211.02740)
   
3. [JuliaParallel.org](https://juliaparallel.org/resources/). Checkout the monthly HPC call and previous events: SC24 BoF.
   
4. [JuliaCon](https://juliacon.org/2024/)

5. [OLCF September User's Call presentations](https://www.olcf.ornl.gov/calendar/userconcall-sep2022/) 

6. [Julia for ORNL Science Workshop](https://ornl.github.io/events/jufos2024/)

7. [Julia Basics Notebooks](https://github.com/ornl-training/julia-basics). Run on myBinder or locally.

8. [From zero to Julia!](https://techytok.com/from-zero-to-julia/). Series of introductory lessons.

9. [Julia for Sustainable HPC Software](https://docs.google.com/presentation/d/1-GEFfkmwZJM44a0BOSpijMpJ8OZ54Or36Ax8LpNbBEg/edit#slide=id.g1e2ac798e0a_0_653) by Valentin Churavy.

10. William F. Godoy, Pedro Valero-Lara, T. Elise Dettling, Christian Trefftz, Ian Jorquera, Thomas Sheehy, Ross G. Miller, Marc Gonzalez-Tallada, Jeffrey S. Vetter, and Valentin Churavy. "Evaluating performance and portability of high-level programming models: Julia, Python/Numba, and Kokkos on exascale nodes." In 2023 IEEE International Parallel and Distributed Processing Symposium Workshops (IPDPSW), pp. 373-382. IEEE, 2023. [doi:10.1109/IPDPSW59300.2023.00068](https://doi.org/10.1109/IPDPSW59300.2023.00068)

11. William F. Godoy, Pedro Valero-Lara, Caira Anderson, Katrina W. Lee, Ana Gainaru, Rafael Ferreira Da Silva, and Jeffrey S. Vetter. 2023. Julia as a unifying end-to-end workflow language on the Frontier exascale system. In Proceedings of the SC '23 Workshops of The International Conference on High Performance Computing, Network, Storage, and Analysis (SC-W '23). Association for Computing Machinery, New York, NY, USA, 1989–1999. [doi:10.1145/3624062.3624278](https://doi.org/10.1145/3624062.3624278)


# Acknowledgements

This tutorial is supported by the following ASCR projects: project Fairbanks as part of MAGNET, and S4PST and PESO of the Next Generation of Scientific Software Technologies.
The many people in the Julia community that made this possible. Thanks to Suzanne Parete-Koon from the Oak Ridge Leadership Center (OLCF).
