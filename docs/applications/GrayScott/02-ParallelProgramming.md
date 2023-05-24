---
layout: default
title: Julia parallel programming on CPU/GPU
nav_order: 2.2
parent: GrayScott reaction-diffusion 3D solver
---

The Julia code can be found in 

# Workflow

The overall workflows is very typical in HPC simulations

```mermaid
graph TD;
    MPI Init --> read JSON config;
    Read JSON config ---> MPI CartComm;
    MPI CartComm ---> Init fields <type,CPU/GPU,values>;
    Init fields <type,CPU/GPU,values> ---> Init parallel Outputs;
    Init parallel outputs ---> Solve U,V
    Solve U,V <--> Exchange 
```



# JSON input configuration



# Domain decomposition using MPI.jl

We use regular domain decomposition 





# Parallel Programming on CPU/GPU

# 

# 

# 

