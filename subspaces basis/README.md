# Subspaces, Particular Solutions & Change of Basis

This project implements the four fundamental subspaces, subspace operations, particular solutions of linear systems, change of basis matrices, and a general matrix linear equation solver — all in **Maxima** (Computer Algebra System).

## 👥 Team "MadMax"

| Member | Primary Contributions |
|--------|----------------------|
| **Nadia Afsar** | **Q2 (Subspaces & Complements), Part of Q5 (Homogeneous Basis)** |
| Roya Zeraati | Q3, Q5 |
| Sara Mohammadi Mohammadi | Q1, Q5 |
| Mahdieh Yazdan Panah | Q4, Q5 |

> **Note:** While each member led specific questions, all team members contributed to debugging, algorithm design, and code review throughout the project.

## 📋 Implemented Questions

| # | Topic | Key Functions |
|---|-------|---------------|
| 1 | Four Fundamental Subspaces | `four_basis`, `four_basis_mat`, `row_space`, `Null_Space` |
| **2** | **Subspaces (Sum, Intersection, Complements)** ⭐ | `subspaces`, `find_base`, `base_for_intersection`, `get_complement` |
| 3 | Particular Solution of Ax = b | `particular_solution` |
| 4 | Change of Basis & Matrix Representation | `mat_bb`, `change_of_basis_matrix`, `not_in_span` |
| **5** | **Matrix Linear Equation Solver** ⭐ (partial) | `mat_linsolve`, `dimension_check`, `linear_check`, `solution` |

⭐ = Implemented (fully or partially) by Nadia Afsar

## 🔍 Detailed Contributions

### Question 2 — Subspaces (Fully Implemented by Nadia Afsar)

Given two lists of row vectors `L1` and `L2`, the `subspaces(L1, L2)` function computes:

- **`P`**: A basis for `span(L1) + span(L2)` (the sum subspace)
- **`Q`**: A basis for `span(L1) ∩ span(L2)` (the intersection)
- **`C`**: A basis for the complement of `span(L1) ∩ span(L2)` in `span(L1)`
- **`C'`**: A basis for the complement of `span(L1) ∩ span(L2)` in `span(L2)`

**Implementation approach:**
- `find_base(L)`: Extracts a basis from a list of vectors using row echelon form.
- `base_for_intersection(P1, P2)`: Builds an augmented block matrix `[[P1, P1], [P2, 0]]`, reduces it, and extracts the non-zero rows in the right half.
- `get_complement(Q, V)`: Finds basis vectors of `V` that are linearly independent from `Q`.
