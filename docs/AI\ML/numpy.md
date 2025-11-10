A python library that using C/Fortran back-end. 
The reason why we use numpy to perform matrix operations
1. Python arrays allow any data type within a single array, meaning each element stores the memory address of that object. Consequently, these elements are often stored in disparate memory locations. In contrast, C arrays only permit homogeneous data types, and their elements are stored in continuous memory addresses.
2. Modern CPUs have SIMD instruction sets that allow a single instruction to operate on miltiple data point simultaneously. For example, instead of adding two numbers at a time, a CPU with SIMD can add four or eight numbers at once. Because Numpy arays store data contiguously and homogeneously, they are perfectly suited for these SIMD optimizations. The underlying C/Fortran code in NumPy can be compiled to take advantage of these SIMD instructions.

## Functions
- np.array() - create an array
- np.dot() - implement dot product operation
