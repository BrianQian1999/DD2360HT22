# DD2360HT22 Team Project

## Summary

Group member: 

* Qiran Qian <qiranq@kth.se> 
* Yuze Cui <yuzec@kth.se> 
* Ruoya Ye <ruoya@kth.se>

Project selection:

* Application: SputniPIC
* Topic: Unified memory

All codes related to the project can be accessed in the directory `project` in the repository. 

## Code organization

The code organization of the `project` directory is: 

* `README.md`: instructions on compiling and running the code;
* `sputniPIC-baseline`: CPU baseline benchmark;
* `sputniPIC-MALLOC`: GPU accelerated benchmark with paged memory allocation scheme;
* `sputniPIC-PINNED`: GPU accelerated benchmark with pinned memory allocation scheme;
* `sputniPIC-UM`: GPU accelerated benchmark with unified memory allocation scheme;

Inside each benchmark, there are:

* `Makefile`: build the corresponding benchmark;
* `inputfiles`: input files that defines the input problem, containing `GEM_2D.inp` and `GEM_3D.inp`;
* `include`: header files;
* `src`: C++/CUDA source files;

## Compilation and execution

For each benchmark, the source codes can be compiled in the Google Colab environment (or, modify the `Makefile` so as to compile and run in other environments) by:

```bash
!make
```

To run the benchmark, use the command:

```bash
!./sputniPIC.out ./<inputfile>
```

Where the `inputfile` can be `GEM_2D.inp` or `GEM_3D.inp`.

## Profiling

To profile the benchmarks, except for the CPU timer that measures the total simulation time, mover time and interpolation time, we can explicitly call `nvprof` to get detailed results:

```bash
!nvprof ./sputniPIC.out ./<inputfile>
```

