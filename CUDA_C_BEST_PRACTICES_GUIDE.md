# CUDA C BEST PRACTICES GUIDE (notes)
## High Priority
- To maximize developer productivity, profile the application to determine hotspots and bottlenecks.
- To get the maximum benefit from CUDA, focus first on finding ways to parallelize sequential code.
- Use the effective bandwidth of your computation as a metric when measuring performance and optimization benefits.
- Minimize data transfer between the host and the device, even if it means running some kernels on the device that do not show performance gains when compared with running them on the host CPU.
- Ensure global memory accesses are coalesced whenever possible.
- Minimize the use of global memory. Prefer shared memory access where possible.
-  Avoid different execution paths within the same warp.
- Avoid the use of __syncthreads() inside divergent code.

## Medium Priority
- Use shared memory to avoid redundant transfers from global memory.
- To hide latency arising from register dependencies, maintain sufficient numbers of active threads per multiprocessor (i.e., sufficient occupancy).
- The number of threads per block should be a multiple of 32 threads, because this provides optimal computing efficiency and facilitates coalescing.
- Use the fast math library whenever speed trumps precision.
-  Prefer faster, more specialized math functions over slower, more general ones when possible.
-  Use signed integers rather than unsigned integers as loop counters.

## Low Priority
- Use shift operations to avoid expensive division and modulo calculations.
- Avoid automatic conversion of doubles to floats.
- Make it easy for the compiler to use branch predication in lieu of loops or control statements

## A few rules of thumb to choose block sizes
- Threads per block should be a multiple of warp size to avoid wasting computation on under-populated warps and to facilitate coalescing.
- A minimum of 64 threads per block should be used, and only if there are multiple concurrent blocks per multiprocessor.
 Between 128 and 256 threads per block is a better choice and a good initial range for experimentation with different block sizes.
- Use several (3 to 4) smaller thread blocks rather than one large thread block per multiprocessor if latency affects performance. This is particularly beneficial to kernels that frequently call __syncthreads().

## Others
- The **core computational unit**, which includes *control*, *arithmetic*, *registers* and typically some *cache*, is replicated some number of times and connected to *memory* via a network.
- **CPU cores** are designed to minimize latency for one or two threads at a time each, whereas *GPUs* are designed to handle a large number of concurrent, lightweight threads in order to maximize throughput.
- **gprof** is an open-source profiler for Linux platforms from the GNU Binutils collection.
- **Bandwidth** is the rate at which data can be transferred.
- A comparison of the **effective or requested bandwidth** to the **actual bandwidth** presents a good estimate of how much bandwidth is wasted by suboptimal coalescing of memory accesses.
- Operations in different streams can be **interleaved** and in some cases overlapped - a property that can be used to hide data transfers between the host and the device.
-  **Global, local, and texture memory** have the greatest access latency, followed by **constant memory, shared memory, and the register file**.
- Global memory loads and stores by threads of a warp are **coalesced** by the device into as few as one transaction when certain access requirements are met.
- If some words of the line had not been requested by any thread (such as if several threads had accessed the same word or if some threads did not participate in the access), all data in the cache line is fetched anyway. Furthermore, if accesses by the threads of the warp had been permuted within this segment, still only one 128-byte L1 transaction would have been performed by a device with compute capability 2.x.
- Memory allocated through the CUDA Runtime API, such as via cudaMalloc(), is guaranteed to be aligned to at least 256 bytes.
- **Non-unit-stride** global memory accesses should be avoided whenever possible. 
- Shared memory is divided into equally sized memory modules (**banks**) that can be accessed simultaneously.
- **Bank conflicts**: If multiple addresses of a memory request map to the same memory bank, the accesses are serialized.  The one exception here is when multiple threads in a warp address the same shared memory location, resulting in a broadcast.
- Aside from memory bank conflicts, there is no penalty for non-sequential or unaligned accesses by a warp in shared memory.
- Access to **local memory** is as expensive as access to global memory. It is used when insufficient register space to hold the variable.
- The read-only **texture memory** space is cached. Therefore, a texture fetch costs one device memory read only on a cache miss; otherwise, it just costs one read from the texture cache.
- There is a total of 64 KB **constant memory** on a device. The constant memory space is cached. As a result, a read from constant memory costs one memory read from device memory only on a cache miss; otherwise, it just costs one read from the constant cache.
- Accessing a **register** consumes zero extra clock cycles per instruction, but delays may occur due to register read-after-write dependencies and register memory bank conflicts.
- **Occupancy** is the ratio of the number of active warps per multiprocessor to the maximum number of possible active warps.
- The multidimensional aspect of grids and blocks allows easier mapping of multidimensional problems to CUDA and does not play a role in performance.
- The **compute capability** describes the features of the hardware and reflects the set of instructions supported by the device as well as other specifications, such as the maximum number of threads per block and the number of registers per multiprocessor.
