# nvtx-test
Test routines using nvtx

This repository comprises a toy example of using the nvtx profiler to analyse Fortran code.

It largely follows the structure of an [NVIDIA tutorial](https://developer.nvidia.com/blog/customize-cuda-fortran-profiling-nvtx/).  
An updated nvtx module `nvtx.cuf` comes from [maxcuda](https://github.com/maxcuda/NVTX_example), with the original moved to `nvtx.cuf_old`.

## Building

### CSD3

With nvfortran:
```
module purge
module load rhel8/global rhel8/slurm
module use /usr/local/software/spack/spack-modules/a100-20210927/linux-centos8-zen2

nvfortran -o nvtx_test main.f90 nvtx.cuf -L/usr/local/software/cuda/12.1/lib64 -lnvToolsExt

./nvtx_test
```
