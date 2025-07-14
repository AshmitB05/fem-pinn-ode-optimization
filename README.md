# fem-pinn-ode-optimization
A research project exploring the Finite Element Method (FEM) and Physics-Informed Neural Networks (PINNs) for general one-dimensional second-order differential equations and convection-dominated ODEs. The project also involved formulating an obstacle problem for an elastic string as an ODE-constrained optimization problem and solving it using the Primal-Dual Active Set (PDAS) algorithm. This work was carried out during a summer internship at IISc Bangalore under the guidance of Prof. Thirupathi Gudi.

## Overview

This project explores the following topics:

- Classical **Finite Element Methods (FEM)** for solving general second-order one-dimensional differential equations with Dirichlet boundary conditions, using both linear and quadratic elements.
- Stabilization techniques like **Streamline Upwind Petrov–Galerkin (SUPG)** to handle convection-dominated problems where classical FEM struggles.
- **ODE-constrained optimization**, where problems are formulated as complementarity systems and solved efficiently using the **Primal-Dual Active Set (PDAS)** algorithm — a semi-smooth Newton method known for its superlinear convergence.
- Application of **deep learning** via **Physics-Informed Neural Networks (PINNs)** to solve differential equations, along with experiments using **variational PINNs** and **least-squares-inspired PINNs** with SUPG-style stabilization.

The goal is to build a foundational understanding of both classical numerical methods and modern machine learning-based solvers in the 1D (ODE) setting, while laying the groundwork for extending these techniques to PDE-based problems and higher dimensions.

## Repository Structure
```
├── FEM Codes/ 
| └── Classical FEM implementations, including SUPG stabilization for convection-dominated problems
│
├── PINNS Codes/
| └── Implementations of PINNs, Variational PINNs, and Least-Squares Nonconforming FEM-inspired PINNs using PyTorch
│
├── PDAS/ 
| └── Primal-Dual Active Set (PDAS) algorithm for ODE-constrained optimization problems — applied to minimizing the potential energy of an elastic string
│
├── PINNs and Neural Networks for Practice/ 
| └── Practice implementations of PINNs and basic neural networks from scratch, also in PyTorch
│
├── README.md 
| └──Project documentation (this file)
```
## Technologies Used

- Python 3.9  
- NumPy, SymPy (symbolic derivation for FEM)
- sckit-fem, SciPy
- PyTorch (neural network & optimization modules)  
- Matplotlib (visualization)

---
## Key Results & Insights

- **FEM vs. PINNs:**  
  The Finite Element Method (FEM) significantly outperforms Physics-Informed Neural Networks (PINNs) in terms of computational efficiency for 1D second-order differential equations. Quadratic FEM offers improved accuracy over linear FEM at a marginal cost in runtime.

- **Convection-Dominated ODEs:**  
  Both FEM and PINNs struggle with convection-dominated problems, leading to spurious oscillations. The **Streamline Upwind Petrov–Galerkin (SUPG)** stabilization method mitigates this, though careful tuning of the stabilization parameter is essential to avoid over-smoothing.

- **PINNs & VPINNs:**  
  PINNs demand extensive hyperparameter tuning (layers, neurons, learning rate). Variational PINNs (VPINNs), although grounded in weak formulations, suffer from longer training times as the mesh size increases.

- **PDAS Algorithm for ODE-Constrained Optimization:**  
  The **Primal-Dual Active Set (PDAS)** algorithm effectively solves constrained elastic string problems when posed as ODE-constrained optimization. Various obstacle functions were tested, and solution behaviors were visualized through plots.

- **Hybrid Perspective:**  
  This work bridges **traditional numerical methods** like FEM with **modern ML approaches** like PINNs, highlighting opportunities to develop hybrid frameworks for solving differential equations.

## Future Work

- Extension to **2D Finite Element Methods (FEM)** with mesh discretization  
- Implementation of **operator learning** approaches instead of directly solving the equations  
- Formulation and solution of more **real-world constrained problems** using the PDAS algorithm  
- Incorporation of **error estimators** and **adaptive mesh refinement**  
- Integration of techniques from **convex optimization** to enhance solver performance  
- Potential submission of this work as a **research note on arXiv**

## About Me

**Ashmit Banerjee**  
3rd-Year Integrated MTech (Mathematics & Computing)  
Indian Institute of Technology (ISM) Dhanbad  
📧 Email: _[ashmit.banerjee.05@gmail.com]_  
🔗 GitHub: _[https://github.com/AshmitB05]_  
🔗 LinkedIn: _[https://www.linkedin.com/in/ashmit-banerjee-13986228a]_  



<p>
This project was carried out at the ODE and one-dimensional level to build a strong foundation in weak formulations, explore the use of PINNs, and understand how to formulate problems as ODE-constrained optimization tasks. It provided valuable insights into the limitations of PINNs and FEM in convection-dominated ODEs, along with strategies to overcome these challenges.
</p>

<p>
Moving forward, I am expanding into operator learning and extending the framework to 2D FEM for modeling and solving constrained problems biological systems in higher dimensions. To support this, I am currently pursuing formal coursework in 
<strong>Ordinary Differential Equations (ODE)</strong>, <strong>Numerical PDEs</strong>, and <strong>Partial Differential Equations (PDEs)</strong>.
</p>

---

> _If you find this useful or have suggestions for further development, feel free to connect!_

