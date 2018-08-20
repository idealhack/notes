# High Performance Computing

## Overview

- [[CUDA]]
- OpenCL
- OpenMP

## Accelerated libraries

- [thrust/thrust: Thrust is a parallel algorithms library which resembles the C++ Standard Template Library (STL).](https://github.com/thrust/thrust)
- [ddemidov/vexcl: VexCL is a C++ vector expression template library for OpenCL/CUDA](https://github.com/ddemidov/vexcl)
- [viennacl/viennacl-dev: Developer repository for ViennaCL. Visit http://viennacl.sourceforge.net/ for the latest releases.](https://github.com/viennacl/viennacl-dev)
- [sschaetz/aura: Accelerator Programming Library in C++](https://github.com/sschaetz/aura)
- [pocl/pocl: pocl - Portable Computing Language](https://github.com/pocl/pocl)
- [NVlabs/cub: CUB is a flexible library of cooperative threadblock primitives and other utilities for CUDA kernel programming.](https://github.com/NVlabs/cub)
- [HSA-Libraries/Bolt: Bolt is a C++ template library optimized for GPUs. Bolt provides high-performance library implementations for common algorithms such as scan, reduce, transform, and sort.](https://github.com/HSA-Libraries/Bolt)
- [CNugteren/CLBlast: Tuned OpenCL BLAS](https://github.com/CNugteren/CLBlast)
- [ARM-software/ComputeLibrary: The ARM Computer Vision and Machine Learning library is a set of functions optimised for both ARM CPUs and GPUs using SIMD technologies.](https://github.com/ARM-software/ComputeLibrary)
- [boostorg/compute: A C++ GPU Computing Library for OpenCL](https://github.com/boostorg/compute)
- [01org/tbb: Official Intel(R) Threading Building Blocks (Intel TBB) GitHub repository.](https://github.com/01org/tbb)
- [Gladdy/EasyOpenCL: The easiest way to get started with OpenCL!](https://github.com/Gladdy/EasyOpenCL)
- [Polytonic/Chlorine: Dead Simple OpenCL](https://github.com/Polytonic/Chlorine)
- [SYCL Overview - The Khronos Group Inc](https://www.khronos.org/sycl)
- [SkePU 2](https://www.ida.liu.se/labs/pelab/skepu/)
- [Overview of MTL4 | SimuNova](http://www.simunova.com/de/node/24)
- [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page)

### Arrayfile

- [arrayfire/arrayfire: ArrayFire: a general purpose GPU library.](https://github.com/arrayfire/arrayfire)
- [Overview](http://arrayfire.org/docs/index.htm)
- [arrayfire/arrayfire-project-templates: Template Projects for ArrayFire](https://github.com/arrayfire/arrayfire-project-templates)
- [arrayfire/arrayfire-docker: Dockerfile for Building and Using ArrayFire https://github.com/arrayfire/arrayfire.git](https://github.com/arrayfire/arrayfire-docker)

### Tools

- [krrishnarraj/clpeak: A tool which profiles OpenCL devices to find their peak capacities](https://github.com/krrishnarraj/clpeak)

### Compile

    g++ test.cpp -L/opt/arrayfire/lib -lafcpu -I/opt/arrayfire/include -O2

## Distributed System

[[Spark]]

## Resources

- [分布式存储与分布式计算 - 五三中 - 博客园](http://www.cnblogs.com/cxzdy/p/5338596.html)
- [GPU-Accelerated Libraries for Computing | NVIDIA Developer](https://developer.nvidia.com/gpu-accelerated-libraries)
- [Echelon Blog](http://www.soa-world.de/echelon/2014/04/c-accelerator-libraries.html)
- [Benchmarking parallel vector libraries | ArrayFire](http://arrayfire.com/benchmarking-parallel-vector-libraries/)
- [c++ - Differences between VexCL, Thrust, and Boost.Compute - Stack Overflow](http://stackoverflow.com/questions/20154179/differences-between-vexcl-thrust-and-boost-compute)
- [并行计算的高性能软件库：ArrayFire - OPEN 开发经验库](http://m.open-open.com/m/lib/view/1415890274039.html)
- [高并发和高可用的一点思考 - Kris的博客 | Kris' Blog](http://kriszhang.com/high_performance/)
- [实时计算——聊一聊我所经历的计算框架 - 简书](https://www.jianshu.com/p/16323566f3c6)
