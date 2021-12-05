# Periodic NBO software

__DEPRECATED__: please head to [official repo](https://github.com/jrschmidt2/periodic-NBO).

---

*This project is originally written by Schmidt Research Group @ University of Wisconsin–Madison.
Forked from [🔗LINK](https://schmidt.chem.wisc.edu/nbosoftware).*

*The source code has been updated by replacing several deprecated routine-calling scheme, and a modified Makefile for it to work with newest intel compiler and MKL version 2019.3.199*

We have generalized the Natural Bond Orbital algorithm to handle systems characterized by periodic symmetry.  While the code only requires information that can be obtained from the output of any periodic electronic structure calculation, it requires specifically formatted input files.  We have created interfaces for the VASP and CRYSTAL software packages, which process those codes' output into the requisite format.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

This package comes in two part:
1. DFT interface and projection executable.
2. NBO calculation executable.

### Prerequisites

The code is written in `Fortran 90`, and requires the `MKL BLAS95` and `MKL LAPACK95` libraries, as well as libraries used in the OpenMP parallelization.  

### Installing DFT interfaces
1. VASP
  * Insert `projection_output.F` in `./projection_VASP/VASP_patch` into directory containing VASP source code `./scr`.
  * apply `proj_VASP.patch` by
  ```
  patch -p0 < proj_VASP.patch
  ```
  * Compile VASP。
  * To compile `projection.exe`, modify `Makefile` under `./projection_VASP` and then type `Make`.

2. CRYSTAL
  * No modification needed.

### Installing NBO software
1. modify `Makefile` under `./NBO`.

2. type `make` to get `nbo.exe`

## Useage
Please see `READ_ME.txt` under each folder to see exactly how it works.


## How to cite

We request that anyone who downloads and utilizes the code cite:

  Dunnington, B. D.; Schmidt, J. R.,
  *Generalization of Natural Bond Orbital Analysis to Periodic Systems: Applications to Solids and Surfaces via Plane-Wave Density Functional Theory*, [J. Chem. Theory Comput., 2012, 8 (6), pp 1902–1911](http://dx.doi.org/ 10.1021/ct300002t)

## License

  This project is licensed under the GNU License - see the `LICENSE.md` for details
