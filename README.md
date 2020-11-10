# lattice-percolation
Lattice percolation in C using MPI and OpenMP for parallel computing.

## Introduction
This application is written in C. It uses MPI and OpenMP that provide parallel computing functionalities.
### What is MPI?
The MPI Standard is a message passing library standard. The goal of MPI is to provide a portable, efficient and flexible standard for message passing parallel programming.

### What is OpenMP?
OpenMP (Open Multi-Processing) is an API that supports multi-platform shared-memory multiprocessing programming in C.

### Why are we using both?
MPI and OpenMP provide different functionalities. An application can be designed with a hybrid model of parallel programming in mind. This allows us to run the program on a computer cluster using both OpenMp and MPI. OpenMP is used for parallelism within a (multi-core) node, while MPI is used for parallelism between nodes. In other words, we use MPI to run multiple separate processes, and send and receive information between those processes. We then can use OpenMP to run multiple threads per process, and share information between those threads.

## Requirements
I will assume you are using Linux. If you are using Windows 10 you can also download the [Linux Subsystem for Windows](https://docs.microsoft.com/en-us/windows/wsl/install-win10) which is very useful.

### MPI
To use MPI with C, you must include mpi.h as a header. It can be included in your c program with `#include <mpi.h>`, you may need to directly reference its absolute path such as `#include "/usr/include/mpi/mpi.h"`.

### OpenMP
To use OpenMP, you must include omp.h as a header. It can be included in your c program with `#include <omp.h>`, you may need to directly reference its absolute path as well.

## How to run
To compile the C file correctly, you should compile it with mpicc.\\
You can install this on linux by `sudo apt install openmpi-bin` and `sudo apt install libopenmpi1.3`.

1. Download `percolation.c`.
2. Enter `mpicc -o percolation percolation.c -fopenmp` to compile `percolation.c.`.
3. Enter `mpirun -np 3 ./percolation` to execute the application.

