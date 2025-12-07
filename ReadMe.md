# Matrix Multiplication Benchmark (C++)

This project follows Lei Mao's blog on Row-Major vs Column-Major memory layouts. It is a direct line-for-line recreation of the code from his post. The program implements a naïve CPU matrix multiplication kernel and benchmarks performance under different transpose configurations.

The benchmark measures the average latency of four cases:

- `C = A * B`
- `C = A^T * B`
- `C = A * B^T`
- `C = A^T * B^T`

All matrices use column-major layout, and transpose behavior is implemented through indexing rather than allocating new matrices.

## What the Code Does

- Implements a simple column-major matrix multiplication routine with optional transpose flags.
- Uses `measure_performance()` to execute warm-up runs, timed runs, and compute average latency in milliseconds.
- Benchmarks each transpose combination using `std::bind` to bind matrix parameters.
- Prints latency results for each configuration.
- Includes assertions to verify expected relative performance.

## Purpose

The goal is to compare how memory layout, loop order, and transpose flags influence performance in a naïve matrix multiplication kernel. This provides a small experimental framework for understanding low-level GEMM behavior before exploring optimized CPU or GPU implementations.
