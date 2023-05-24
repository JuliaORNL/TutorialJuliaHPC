---
layout: default
title: Introduction
nav_order: 1
---

# Goal

The goal of the tutorial is to introduce an audience familiar with high-performance computing (HPC) concepts to the Julia programming language.

## Covered:
- Hands-on approach
- Cover workflow aspects: simulation CPU/CPU, parallel I/O, data analysis (Notebooks)
- Multithreaded CPU using Julia threads
- GPU programming using CUDA.jl and AMDGPU.jl
- Parallel I/O with ADIOS2.jl
- Julia on OLCF's JupyterHub and Pluto.jl Notebooks (read and plot)

## Not Covered:
- More general aspects of the language (software engineering, AI)
- AI infrastructure: Flux.jl, SciML
- Performance portability layers: KernelAbstractions.jl (future)
- Ahead-of-time compilation: PackageCompiler.jl

# Why Julia?

1. Compiled via LLVM for performance. **Julia is Compiled**
2. Provides a unified ecosystem (packaging, testing, notebooks, interactivity, etc.)
3. Community of HPC people from day-1 (it's you, low entry barrier)
4. Great math (Fortran) and data science (Python) syntax
5. Rapid prototyping/productivity: stay in one language+ecosystem
6. Reuse Fortran, C, C++ (via C), Python, R code in a lightweight manner
7. Renewed interest for high-performance + high-productivity languages

# Why not Julia?

1. Already existing infrastructure/expertise
2. Too much of an investment to learn a new language
3. Performance solutions in place
4. Two-language problem is not a problem
5. Happy with Python + X

![](images/Blog_2303_julia_value_proposition.png)**Julia's value proposition**


## Community Resources

1. [Julia's value proposition for Better Scientific Software](https://bssw.io/blog_posts/julia-s-value-proposition-for-better-scientific-software)

2. [Bridging HPC Communities through the Julia Programming Language](https://arxiv.org/abs/2211.02740)
   
3. [JuliaParallel.org](https://juliaparallel.org/resources/). Checkout the monthly HPC call.
   
4. [JuliaCon](https://juliacon.org/2023/)

# Acknowledgements

This research was supported by the Exascale Computing Project (17-SC-20-SC), a collaborative effort of the U.S. Department of Energy Office of Science and the National Nuclear Security Administration. 

[ECP PROTEAS-TUNE](https://www.ornl.gov/project/proteas-tune), [ASCR Bluestone](https://csmd.ornl.gov/Bluestone), [IDEAS](https://ideas-productivity.org/ideas-ecp/) projects, and the [Sustainable Research Pathways Program](https://shinstitute.org/sustainable-research-pathways-srp/) 
