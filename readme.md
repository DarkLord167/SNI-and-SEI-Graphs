# Reliability Analysis of Stepwise Inhomogeneous Graphs (SNI & SEI)


## Project Overview
This project studies **reliability, fragility, and resilience** of a special class of complex networks known as **Stepwise Inhomogeneous Graphs**. The focus is on two graph families:

- **SNI (Stepwise Node-Inhomogeneous graphs)**
- **SEI (Stepwise Edge-Inhomogeneous graphs)**

Using **graph-theoretic modeling and Monte Carlo simulations**, the project evaluates how these networks respond to **random and targeted node failures**, and compares their robustness characteristics.

The project is fully implemented in **Python** using the **NetworkX** library.


## Objectives
- Generate SNI and SEI networks of arbitrary size
- Simulate node failures (random and intentional attacks)
- Quantify **fragility** using spectral properties
- Quantify **resilience** using giant component analysis
- Study the relationship between fragility and resilience
- Compare robustness behavior of SNI vs SEI graphs


## Background
Complex systems such as social, biological, and technological networks can be modeled as graphs where:
- Nodes represent entities
- Edges represent interactions

A network is considered **robust** if it maintains its core functionality under failures. Two key concepts are:

- **Fragility:** Sensitivity of the network to perturbations
- **Resilience:** Ability of the network to remain connected

Stepwise Inhomogeneous graphs are a special class of bipartite graphs where the degree difference between adjacent nodes (or edges) is at most one.


## Graph Definitions

### SNI Graphs
- Stepwise **node-based** inhomogeneity
- Degree difference between adjacent nodes $≤$ 1

### SEI Graphs
- Stepwise **edge-based** inhomogeneity
- Degree difference between adjacent edges $≤$ 1

Both graph families are bipartite and have zero determinant for their adjacency matrices.


## Project Tasks

### 1. Graph Generation
- Implement flexible Python functions to generate **SNI** and **SEI** graphs
- Accept network size and construction parameters as input
- Use **NetworkX** for graph representation

### 2. Fragility Analysis
Fragility is measured using the **spectral instability** of the adjacency matrix:

- Compute eigenvalues of the adjacency matrix
- Measure the maximum distance of eigenvalues from the imaginary axis
- Higher values indicate greater fragility

### 3. Resilience Analysis
Resilience is evaluated using the **Giant Component (GC)** concept:

\[ G(q) = $\frac{N_G}{N}$ \]

Where:
- \( q \) = fraction of removed nodes
- \( $N_G$ \) = size of giant component
- \( N \) = original network size

The critical threshold \( $q_c$ \) is defined where the network becomes disconnected.


## Failure & Attack Models
- **Random node removal**
- **Targeted attacks** (based on degree or centrality)

Network degradation is evaluated over multiple attack steps:

- Fragility increases: \( F(t+1) $\ge$ F(t) \)
- Resilience decreases: \( R(t+1) $<$ R(t) \)


## Monte Carlo Simulation
- Perform repeated simulations for statistical reliability
- Compute confidence intervals
- Analyze variability across runs


## Polynomial Fitting & Analysis
- Plot **resilience vs fragility** curves for SNI and SEI
- Perform **polynomial regression** on simulation data
- Treat:
  - Fragility as independent variable (x)
  - Resilience as dependent variable (y)

The fitted polynomial models describe the nonlinear relationship between robustness metrics.


## Tools & Technologies
- **Python 3**
- **NetworkX** – Graph modeling
- **NumPy / SciPy** – Linear algebra & eigenvalues
- **Matplotlib / Seaborn** – Visualization
- **Scikit-learn** (optional) – Polynomial fitting


## 📁 Project Structure
```text
├── src/                # SNI & SEI graph generators
└── readme.md
```

**Simulation parameters (network size, attack type, p-values) can be configured inside the code.**





