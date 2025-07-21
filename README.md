# Strassen’s Matrix Multiplication

## Description
This C++ program implements **Strassen’s algorithm** for multiplying two square matrices of size *n×n*. It uses recursive divide‑and‑conquer to reduce the number of scalar multiplications compared to the classical algorithm.

## Files
- `strassen.cpp` – main source file containing  
  - `add_mat`, `sub_mat` – matrix block addition/subtraction  
  - `Strassens` – recursive Strassen routine  
  - `main` – reads input, invokes Strassen, prints result  

## Requirements
- C++11 (or later) compiler  
- Sufficient heap memory for dynamic allocations  

## Compilation
```bash
g++ -std=c++11 -O2 -o strassen strassen.cpp
