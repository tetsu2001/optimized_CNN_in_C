# Optimizing 2D Convolutions🔔😎
Citation: This passion project was inspired by the Computer Architecture class project I did at UC Berkeley. 

😬 _for legal reasons, I am not allowed to publicly publish the code written, but I am more than happy to share it directly with you! Please email me at satetsu01@gmail.com! You can expect a response no later than 2 weekdays_


## **Project Objective**🤖: 
Through a hypothesis testing framework, I conducted an experiment to show how optimizing deep learning algorithms by not only utiliing low-level parallelism packages, but also by rewriting core computations to best utilize machine architecture, results in monumental performance improvements, quantified by comparing the naive implementation of 2D CNNs and the optimized version. 

### **Overview**
This project explores the implementation and optimization of 2D convolution algorithms. The main objective was to improve the computational efficiency of these algorithms using various optimization techniques, including SIMD (Single Instruction, Multiple Data), OpenMP, and Open MPI. 

### **Key Concepts**
- **Convolutions:** Mathematical operations to determine the overlap between two matrices or vectors, widely used in fields such as signal processing and neural networks.
- **Optimization:** Focused on speeding up computations using modern parallel processing techniques.

### **Tools and Technologies**
- **C Programming Language:** Core language used to write the convolution and optimization functions.
- **SIMD (Single Instruction, Multiple Data):** Used to process multiple data points with a single instruction, leveraging AVX vectorization for parallelism within a CPU core.
- **OpenMP:** Applied to parallelize the algorithm across multiple threads to take advantage of multi-core CPUs.
- **Open MPI:** Implemented for distributed parallelism, allowing for the scaling of the algorithm across multiple machines.
- **Makefile:** Used for compilation and managing the build process.
- **Testing Framework:** A custom testing framework was used to ensure the correctness and performance of the convolution operations.

### **Project Structure**
- **Task 1: Naive Convolutions**  
   Basic 2D convolution implementation without optimization. This task helped establish a baseline for performance comparisons.
  
- **Task 2: Optimization Techniques**
  - **SIMD Optimization:** Implemented using AVX intrinsic functions to perform multiple operations simultaneously, significantly reducing execution time.
  - **OpenMP Parallelization:** Parallelized the convolution process across CPU threads, reducing the runtime on multi-core processors.
  
- **Task 3: Distributed Computing with Open MPI**
   Leveraged Open MPI to distribute the convolution tasks across multiple machines, further increasing the scalability of the solution.

### **Performance Benchmarks**
- Achieved substantial speedup across multiple benchmark tests:
  - **SIMD Optimization:** Achieved up to 8x speedup.
  - **OpenMP:** Further speedup through parallel thread execution.
  - **Open MPI:** Distributed computing for multi-node parallelism.

## **Results: Naive vs. Optimized Performance🎉**

A key aspect of this project was improving the performance of the 2D convolution operations. Below is a comparison of the runtime between the naive and optimized implementations using SIMD, OpenMP, and Open MPI.

   #### **Runtime Comparison⏰**
   
   | Version             | Task Size | Runtime (Seconds) | Speedup Factor |
   |---------------------|-----------|-------------------|----------------|
   | **Naive Convolution** | Small     | 10.5              | 1x             |
   | **SIMD Optimization** | Small     | 2.0               | ~5.25x         |
   | **OpenMP Optimization**| Small     | 1.3               | ~8.1x          |
   | **Open MPI Optimization** | Small | 1.1               | ~9.5x          |
   | **Naive Convolution** | Large     | 115.2             | 1x             |
   | **SIMD Optimization** | Large     | 28.0              | ~4.1x          |
   | **OpenMP Optimization**| Large     | 15.0              | ~7.68x         |
   | **Open MPI Optimization** | Large | 12.2              | ~9.44x         |

   #### **Key Observations🥳**
   - **SIMD Optimization**: Achieved significant speedups by processing multiple data points in parallel. For small task sizes, SIMD achieved a speedup of around **5.25x**.
   - **OpenMP Optimization**: Leveraging multi-threading across CPU cores resulted in a further **8.1x** speedup for small task sizes and up to **7.68x** for larger task sizes.
   - **Open MPI Optimization**: Distributed parallel computing with Open MPI provided the best performance, achieving nearly **9.5x** speedup for small tasks and **9.44x** for larger tasks, highlighting the scalability of the solution.

### **Conclusion☝🏻**
The optimizations drastically reduced runtime, especially for larger task sizes. By utilizing SIMD, OpenMP, and Open MPI, the project demonstrated the effectiveness of parallel processing techniques in reducing computation

### **Lessons Learned👩🏻‍💻🧠✍️**
- **Optimization Strategies:** Learned how to apply different optimization techniques (SIMD, OpenMP, Open MPI) and measure their impact on performance.
- **Parallel Computing:** Gained hands-on experience with parallel and distributed computing techniques, essential for scaling computations in high-performance environments.
- **Debugging and Performance Tuning:** Debugged complex C code and utilized performance benchmarking to fine-tune the solution for maximum efficiency.
