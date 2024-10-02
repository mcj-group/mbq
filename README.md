# mbq
This repository will provide the code that accompanies the [paper](https://www.eecg.utoronto.ca/~mcj/papers/2024.mbq.spaa.pdf) by Guozheng Zhang, Gilead Posluns, and Mark C. Jeffrey, presented at the [36th ACM Symposium on Parallelism in Algorithms and Architectures (SPAA)](https://spaa.acm.org/program/), June 2024.

This is a super repo for submodule benchmarks, the **Multi Bucket Queue (MBQ)** & the **MultiQueue (MQ)** (both in the `cps` repo).

The **MBQ** and **MQ** are implemented separately, and are embedded into the individual submodule frameworks for evaluation and comparison against the native scheduler in that framework.

## Getting started
```
# cloning the main repo
git clone https://github.com/mcj-group/mbq.git

# getting all the submodule repos recursively
cd mbq
git submodule update --init --recursive
```


## Overview of frameworks
Each framework contains benchmarks used for evaluation, some contain native schedulers which we use for comparison against our **MBQ** and **MQ**.

All benchmark repos are minimalistic (only include necessary files for experiments).

|Framework|Benchmarks| Input Type |Native Scheduler|  
|---|---|---|---|  
|**galois**| `sssp`, `ppsp`, `bfs`, `pr`| `.gr` galois binaries |**OBIM**, **PMOD** |
|**ligra**| `sc`| PBBS adjacency graphs |**Julienne** |
|**pbbs**| `mis` | **symmetric** PBBS adjacency graphs | **Synchronous Parallel Loops** |
|**rbp**| `rbp`| specified & generated at run-time ||
|**astar**| `astar`| `.bin` graph binaries with coordinates | |

**cps** repo: contains the **MBQ** & **MQ** (and others, see README from cps's `main` branch), which are necessary for comparing with above benchmarks. The schedulers in this repo require **Boost**.


## Building & running individual frameworks
See the `README.md` file in each individual frameworks/repos for more details on prerequisites and info.

All the repo have scripts for building and running experiments. 

We do not provide input files (see download sources from the paper).
