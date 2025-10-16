---
title: "Fast Mass-Spring Systems"
description: "A high-performance physics simulation implementing the fast mass-spring system algorithm from Liu et al. 2013, built in C++ with sparse matrix optimization."
date: 2021-03-01
image: '/flag.gif'
---

A fast and efficient physics simulation of mass-spring systems, implementing the optimization-based time integration algorithm from "Fast Simulation of Mass-Spring Systems" (Liu et al. 2013).

![Flag simulation showing cloth dynamics with mass-spring system](/flag.gif)

## About

This project is from the Computer Graphics course at the University of Toronto (taught by Alec Jacobson). Rather than using traditional explicit time integration, this implementation uses a fast implicit method that treats physics simulation as an energy optimization problem.

The key innovation from the Liu et al. paper is a local-global iterative solver that alternates between:
1. **Local step** - Computing optimal spring directions (embarrassingly parallel)
2. **Global step** - Solving a sparse linear system for vertex positions

This approach combines the stability of implicit methods with the speed of explicit methods, enabling real-time simulation of complex cloth and soft body dynamics.

## Features

- **Fast Implicit Integration** - Stable simulation with large time steps
- **Sparse Matrix Optimization** - Efficient $O(n^{1.5})$ performance using Cholesky factorization
- **Constraint Handling** - Penalty method for pinned vertices
- **Complex Cloth Simulation** - Handles flags, skirts, nets, and chains
- **Real-Time Performance** - Interactive frame rates even for large meshes

## Technical Highlights

### Optimization-Based Physics
Instead of directly solving $\mathbf{f} = m\mathbf{a}$, the simulation minimizes a quadratic energy that combines:
- **Elastic potential energy** - Springs want to return to rest length
- **Kinetic energy** - Masses want to maintain momentum
- **External forces** - Gravity and user interaction

### Sparse Linear Algebra
The system matrix $\mathbf{Q}$ is sparse (mostly zeros), allowing efficient factorization:
- Dense approach: $O(n^3)$ precomputation, $O(n^2)$ per frame
- Sparse approach: $O(n^{1.5})$ precomputation, nearly $O(n)$ per frame

The sparse implementation uses Eigen's `SimplicialLDLT` to precompute the Cholesky factorization once, then performs fast forward/backward substitution each frame.

## Technologies Used

- **C++** - High-performance systems programming
- **Eigen** - Linear algebra library with excellent sparse matrix support
- **Sparse Matrices** - Memory-efficient representation using triplet lists
- **Numerical Optimization** - Local-global iterative solver
