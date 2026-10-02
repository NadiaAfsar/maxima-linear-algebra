# Matrix Operations in Maxima

A collection of nine comprehensive linear algebra implementations in **Maxima** (Computer Algebra System), covering matrix decompositions, Gaussian elimination, determinant computation, adjugate matrices, and PLU/LPL/LPU factorizations. Developed as part of the Linear Algebra course at Sharif University of Technology.

## 👥 Team "MadMax"

This project was developed collaboratively by a four-member team:

| Member | Primary Contributions |
|--------|----------------------|
| **Nadia Afsar** | **Q1 (Matrix Processing), Q3 (Block Matrices), Q7 (Inverse via Gaussian Elimination & Adjugate)** |
| Roya Zeraati | Q5, Q6, Q9 |
| Sara Mohammadi Mohammadi | Q2, Q8 |
| Mahdieh Yazdan Panah | Q5, Q6 |

> **Note:** While each member led specific questions, all team members contributed to debugging, code review, and algorithm design throughout the project.

## 📖 Project Overview

This project implements a comprehensive toolbox for linear algebra operations in Maxima, including:

- **Matrix type validation** (row echelon, reduced row echelon, permutation, elementary)
- **Random matrix generation** with specified properties
- **Block matrix construction** (horizontal, vertical, diagonal)
- **Triangular matrix operations** (inverse, determinant)
- **Gaussian elimination** (step-by-step row echelon and Gauss-Jordan)
- **Determinant computation** via two methods (Gaussian elimination vs. Laplace expansion)
- **Matrix inversion** via two methods (Gaussian elimination vs. adjugate matrix)
- **LPL, LPU, and PLU decompositions**

## ✨ Implemented Functions

### Question 1: Matrix Processing ⭐ (Implemented by Nadia Afsar)
- `to_matrix(L)` — Converts lists to Maxima matrices (accepts both formats).

### Question 2: Matrix Types & Random Generation
- `check_row_echelon(A)` — Checks if A is in row echelon form.
- `check_reduced_row_echelon(A)` — Checks if A is in reduced row echelon form.
- `check_permutation(A)` — Checks if A is a permutation matrix.
- `check_elementary(A)` — Returns 1, 2, or 3 for elementary matrix type, 0 otherwise.
- `random_lowertriangular(n, x)` — Generates random lower triangular matrix.
- `random_invertible(n, x)` — Generates random invertible matrix.
- `random_permutation(n)` — Generates random permutation matrix.
- `random_reduced_row_echelon(m, n, x)` — Generates random RREF matrix.

### Question 3: Block Matrices ⭐ (Implemented by Nadia Afsar)
- `block_matrix(L)` — Constructs a block matrix from a list of sub-matrices.
- `block_diagonal_matrix(L)` — Constructs a block diagonal matrix from a list of matrices.
- Supporting: `horizontal_join(M1, M2)`, `vertical_join(M1, M2)`, `join_matrices(L1, L2)`.

### Question 4: Triangular Matrix Operations
- `triangular_inverse(M)` — Computes the inverse of a triangular matrix.
- `triangular_det(M)` — Computes the determinant of a triangular matrix.

### Question 5: Step-by-Step Gaussian Elimination
- `gauss_row_echelon(P)` — Returns list of step matrices and elementary matrices.
- `gauss_jordan(Q)` — Returns list of step matrices and elementary matrices (RREF).

### Question 6: Determinant via Two Methods
- `det1(A)` — Determinant via Gaussian elimination.
- `det2(A)` — Determinant via Laplace expansion (recursive).
- `CompareTime(A)` — Benchmarks both methods.

### Question 7: Inverse via Two Methods ⭐ (Implemented by Nadia Afsar)
- `inverse1(A)` — Inverse via Gaussian elimination.
- `adjugate(A)` — Computes the adjugate (adjoint) matrix.
- `inverse2(A)` — Inverse via adjugate matrix.
- `CompareFunctions(A)` — Benchmarks both inverse methods.
- Supporting: `minor(A, i, j)`, `diagonal_inverse(D)`, `is_zero(L)`.

### Question 8: LPL and LPU Decompositions
- `lpl(M)` — LPL decomposition with elementary row/column operations.
- `lpu(M)` — LPU decomposition.
- `inverse3(A)` — Inverse via LPL decomposition.

### Question 9: PLU Decomposition
- `plu(A)` — PLU decomposition with elementary row operations.

## 🔬 Key Highlights

### 1. Operations Relevant to Cryptography

This project (HW1) implements mathematical tools that are foundational for cryptographic constructions:

- **Matrix decompositions (PLU, LPL, LPU)** — These factorizations are used to compute modular inverses of matrices over finite fields, which is exactly the operation required for **decryption in the Hill Cipher**. More generally, PLU decomposition appears in **secure outsourcing protocols**, where a server performs matrix operations without learning the underlying data.

- **Adjugate and inverse matrices** — Computing the inverse of a matrix over a finite field (via the adjugate matrix and determinant) is essential for **linear-algebra-based cryptosystems** such as the Hill Cipher, and for the modular arithmetic that appears throughout cryptographic protocols.

- **Gaussian elimination and determinant computation** — These are the core algorithms for solving linear systems over finite fields, which is a fundamental operation in **cryptanalysis**, **secret sharing schemes**, and **linear cryptanalysis** of block ciphers.

- **Triangular matrix operations** — Inverses and determinants of triangular matrices appear in the **LU decomposition**, which itself is used in **AES** (for efficient implementation) and in **lattice-based cryptography** (for basis reduction).

> **Note:** This is a linear algebra course assignment, not a cryptography project. The connection to cryptography is that the *mathematical tools* implemented here — matrix inversion, decomposition, Gaussian elimination, and determinant computation — are the same tools used to build and analyze cryptographic primitives. This project demonstrates mastery of those tools.
### 2. Multiple Algorithm Comparison
For both **determinant** and **inverse**, two different algorithms are implemented and benchmarked:
- **Determinant:** Gaussian elimination (O(n³)) vs. Laplace expansion (O(n!))
- **Inverse:** Gaussian elimination vs. adjugate matrix

This comparison demonstrates an understanding of algorithmic complexity.

### 3. Custom Implementation
All functions are implemented **from scratch** in Maxima, without using built-in `echelon`, `triangularize`, or LU decomposition functions.

