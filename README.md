# Linear Algebra Projects in Maxima

A collection of three comprehensive linear algebra homework assignments implemented in **Maxima** (Computer Algebra System). These projects cover matrix decompositions, subspaces, Gaussian elimination, determinant and inverse computation, Jordan form, Gram-Schmidt, QR, SVD, and least-squares linear models — with a focus on **operations over finite fields** relevant to cryptography.

## 📚 Homework Assignments

| # | Topic | Key Concepts | Folder |
|---|-------|--------------|--------|
| 1 | **Matrix Operations & Decompositions** | Row echelon, triangular inverse, Gaussian elimination, determinant (2 methods), inverse (2 methods), adjugate, LPL / LPU / PLU | [hw1-matrix-operations/](matrix-operations/) |
| 2 | **Subspaces, Basis & Change of Basis** | Four fundamental subspaces, subspace sum / intersection, particular solution of `Ax = b`, change of basis, matrix linear equation solver | [hw2-subspaces-basis/](subspaces-basis/) |
| 3 | **F₂ Systems, Jordan Form & SVD** | Lights Out over **F₂**, characteristic polynomial, adjugate, Jordan normal form, Jordan–Chevalley decomposition, Gram-Schmidt, QR, SVD, linear models (least squares) | [f2-jordan-svd/](hw3-f2-jordan-svd/) |

## 👥 Team "MadMax"

This series of projects was developed collaboratively by a four-member team. Each member led specific questions, while all contributed to debugging, algorithm design, and code review.

| Member | Primary Contributions |
|--------|----------------------|
| **Nadia Afsar** | **HW1: Q1 (Matrix processing), Q3 (Block Matrices), Q7 (Inverse via Gaussian & Adjugate)** <br> **HW2: Q2 (Subspaces), Part of Q5 (Homogeneous Basis)** <br> **HW3: Q4 (Gram-Schmidt, QR, SVD)** |
| Roya Zeraati | HW1: Q2, Q8 <br> HW2: Q1, Q5 <br> HW3: Q3 |
| Sara Mohammadi Mohammadi | HW1: Q4, Q9 <br> HW2: Q3, Q5 <br> HW3: Q2 |
| Mahdieh Yazdan Panah | HW1: Q5, Q6 <br> HW2: Q4, Q5 <br> HW3: Q1, Q5 |

## 🔍 Summary of My Contributions

### HW1 — Matrix Operations & Decompositions
- **Q3: Block Matrices** — `block_matrix`, `block_diagonal_matrix`, with supporting `horizontal_join`, `vertical_join`, and `join_matrices`.
- **Q7: Inverse via Two Methods** — `inverse1` (Gaussian elimination), `adjugate` (Faddeev–LeVerrier), `inverse2` (adjugate-based), plus `minor` and `CompareFunctions` for benchmarking.

### HW2 — Subspaces, Basis & Change of Basis
- **Q2: Subspaces** — `subspaces`, `find_base`, `base_for_intersection`, `get_complement` for computing sum, intersection, and complements of subspaces.
- **Part of Q5: Homogeneous Basis** — `list_varl`, `coefmatrix`, and `one_ans` for computing the homogeneous solution space of a matrix linear system.

### HW3 — F₂ Systems, Jordan Form & SVD
- **Q4: Gram-Schmidt, QR, SVD** — Full implementation of `gram_schmidt`, `orthogonal_diag`, and `svd`, including supporting helpers for normalization, eigenspace computation, and complement basis construction.

For the remaining questions, I contributed to **algorithm design** and **debugging** — especially the F₂ linear system formulation in HW3 Q1 and the Jordan form construction in HW3 Q3.

## ✨ Cross-Project Highlights

### 1. Operations over Finite Field F₂ (HW3, Q1) ⭐
The **Lights Out** puzzle is modeled as a linear system `Ax = b` over **F₂** (mod 2 arithmetic):
- Each cell of the `n × n` grid is mapped to a coordinate `k = n·(i-1) + j`.
- The **Effect matrix** `A` encodes which cells toggle when a cell is selected (itself + orthogonal neighbors).
- Solved with a **mod-2 Gauss-Jordan** implementation.

This same algebraic structure underlies **AES** (S-box = field inversion in GF(2⁸)), **Zero-Knowledge Proofs** for boolean circuits, and **post-quantum signature schemes** such as FAEST and Preon.

### 2. Matrix Decompositions (HW1)
- **PLU / LPL / LPU** factorizations — used to compute modular inverses of matrices over finite fields, exactly the operation required for **decryption in the Hill Cipher**. Also appear in **secure outsourcing protocols**.
- **Adjugate and inverse matrices** — essential for linear-algebra-based cryptosystems (Hill Cipher) and for modular arithmetic in cryptographic protocols.
- **Gaussian elimination and determinant computation** — core algorithms for solving linear systems, used in **cryptanalysis**, **secret sharing**, and **linear cryptanalysis** of block ciphers.

### 3. Subspaces & Basis Change (HW2)
- **Four fundamental subspaces**, **subspace intersection / sum**, and **change of basis** — foundational in **LWE**, **NTRU**, **rank-metric codes**, and **linear cryptanalysis**.
- **Solving `Ax = b`** — used in **secret sharing** and **linear cryptanalysis**.

### 4. Jordan Form (HW3, Q3)
- Random Jordan matrix generation, generalized eigenspace decomposition, and **Jordan–Chevalley decomposition** (`A = D + N`).
- Relevant to **algebraic cryptanalysis** and the structure of linear transformations in cryptographic primitives.

### 5. Gram-Schmidt, QR, and SVD (HW3, Q4) ⭐
- **SVD** is used in **lattice reduction** and **cryptanalysis** (e.g., side-channel analysis).
- **QR decomposition** appears in numerical linear algebra and cryptographic protocols.
- **Least squares** (HW3, Q5) is foundational for **linear regression** and **statistical cryptanalysis**.

## 🛠️ Technologies

- **Tool:** Maxima (Computer Algebra System)
- **Language:** Maxima script (`.mac` files)
- **Concepts:** Finite fields, linear algebra, matrix decompositions, numerical methods, algebraic structures

