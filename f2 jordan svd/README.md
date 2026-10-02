# F₂ Systems, Jordan Form & SVD

This project implements advanced linear algebra topics in **Maxima** (Computer Algebra System), including **linear systems over the finite field F₂** (Lights Out), characteristic polynomials, adjugate matrices, **Jordan decomposition**, **Gram-Schmidt orthogonalization**, **QR decomposition**, **SVD**, and **least-squares linear models**.

## 👥 Team "MadMax"

| Member | Primary Contributions |
|--------|----------------------|
| **Nadia Afsar** | **Q4 (Gram-Schmidt, QR, SVD)** |
| Roya Zeraati | Q3 |
| Sara Mohammadi Mohammadi | Q2 |
| Mahdieh Yazdan Panah | Q1, Q5 |

> **Note:** While each member led specific questions, all team members contributed to debugging, algorithm design, and code review throughout the project.

## 📋 Implemented Questions

| # | Topic | Key Functions |
|---|-------|---------------|
| 1 | **Lights Out over F₂** | `reach_target_state`, `Effect_matrix`, `particular_solution`, `difference` |
| 2 | **Characteristic Polynomial & Adjugate** | `charpoly_adj`, `charpoly1`, `adjugate`, `charpoly_brute_force`, `adjugate_brute_force` |
| 3 | **Jordan Form** | `random_jordan1`, `random_jordan2`, `decomp_mat`, `jordan_basis`, `jordan_normal_form`, `jordan_chevalley` |
| **4** | **Gram-Schmidt, QR, SVD** ⭐ | `gram_schmidt`, `orthogonal_diag`, `svd` |
| 5 | **Linear Models (Least Squares)** | `linear_model` |

⭐ = Implemented by Nadia Afsar

## 🔍 Detailed Contributions

### Question 4 — Gram-Schmidt, QR, and SVD (Implemented by Nadia Afsar)

This question required implementing three foundational matrix factorization algorithms from scratch:

#### (a) Gram-Schmidt Orthogonalization — `gram_schmidt(A)`
- Takes a matrix `A` whose columns are `y₁, ..., yₙ`.
- Returns `[X, Q, R]` where:
  - `X` = orthogonalized (but not normalized) columns
  - `Q` = orthonormal basis (normalized via `yekke_sazi`)
  - `R` = upper triangular matrix such that `A = QR`

#### (b) Orthogonal Diagonalization — `orthogonal_diag(A, L)`
- Given a symmetric matrix `A` and its eigenvalues (as a weighted list `L`), computes an orthogonal matrix `Q` and diagonal matrix `D` such that `Qᵀ A Q = D`.
- Uses `fazaye_vizhe` to form `A - λI`, `Null_Space` to find eigenvectors, and `gram_schmidt` to orthogonalize each eigenspace.

#### (c) Singular Value Decomposition — `svd(M)`
- Computes `M = U Σ Vᵀ` where:
  - `V` = eigenvectors of `MᵀM` (orthonormalized)
  - `Σ` = square roots of the eigenvalues of `MᵀM`
  - `U` = computed from `M`, `V`, and `Σ`, then completed to an orthonormal basis using `get_complement` and `gram_schmidt`
- The implementation handles rectangular matrices by extending `U` with complement vectors.

