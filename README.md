Description
This C++ program implements Strassen’s algorithm for multiplying two square matrices of size n×n. It uses recursive divide‑and‑conquer to reduce the number of scalar multiplications compared to the classical algorithm.

Files
strassen.cpp – main source file containing

add_mat, sub_mat – matrix block addition/subtraction

Strassens – recursive Strassen routine

main – reads input, invokes Strassen, prints result

Requirements
C++11 (or later) compiler

Sufficient heap memory for dynamic allocations

Compilation
bash
Copy
Edit
g++ -std=c++11 -O2 -o strassen strassen.cpp
Usage
bash
Copy
Edit
./strassen
Input

First line: integer n (matrix dimension, must be a power of 2)

Next n lines: n integers each – entries of matrix A

Next n lines: n integers each – entries of matrix B

Output

n lines, each with n integers – the product matrix C = A × B

Example

Copy
Edit
4
1 2 3 4
5 6 7 8
9 8 7 6
5 4 3 2
1 0 2 1
3 4 0 2
1 1 1 1
0 2 3 4
produces

Copy
Edit
14 18 16 22
38 50 44 62
62 74 68 86
30 38 36 46
Algorithm Details
Base case: n == 1, multiply single elements.

Divide: split each matrix into four (n/2 × n/2) blocks via column offsets (col1, col2).

Compute the 10 intermediate S matrices via block additions/subtractions.

Recurse to compute seven products P1…P7 on size n/2 blocks.

Combine P1…P7 into result blocks C11…C22, then assemble the full n×n result.

Memory Management
All matrices (input, temporaries, result) are allocated with new[].

Temporary blocks (S1…S10, P1…P7, intermediate C11…C22) are deleted after use to avoid leaks.
