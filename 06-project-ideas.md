
# 📚 06 — Project Ideas (Deployable & Research-Grade)

This section presents **end-to-end quantum optimization project templates** you can build today (or extend for research). Each project balances **practical relevance**, **model clarity**, and **implementation feasibility** using current tools (Qiskit, D-Wave Ocean, hybrid solvers).

---

## 🌐 1. Hybrid Portfolio Optimization

**Focus:** Financial optimization using QUBO formulations

**Description:**
Implement a portfolio optimizer that balances risk and return under budget or cardinality constraints using quantum optimization methods. A recent real-world study shows practical portfolio QUBO modeling solved via hybrid D-Wave samplers and classical solvers on real asset datasets. ([Springer][1])

**Problem Formulation:**
Quadratic Unconstrained Binary Optimization (QUBO) reflecting:

* expected returns (linear term)
* covariance (quadratic term)
* budget and cardinality constraints

**Algorithms & Tools:**

* Qiskit Optimization / VQE or QAOA variants ([IBM Quantum Documentation][2])
* D-Wave Ocean hybrid solvers
* Classical baselines (simulated annealing, convex optimisation)

**Data / Benchmarks:**

* Public financial data (e.g., Yahoo Finance)
* MQLib or QUBO benchmark sets for risk tests

**Deliverables:**

* Jupyter notebook generating QUBO from historical prices
* Comparison of solvers by **approximation ratio**, **expected return**
* Back-testing on out-of–sample data

**Difficulty:** Intermediate to Advanced

---

## 🚦 2. Scheduling for Resource-Constrained Projects

**Focus:** Industrial scheduling with precedence constraints

**Description:**
Solve the **Resource-Constrained Project Scheduling Problem (RCPSP)** via QUBO and quantum annealing. A Scientific Reports paper successfully mapped RCPSP to QUBO solved on a D-Wave annealer with custom metrics like time-to-target and Q-score. ([Nature][3])

**Problem Formulation:**
Binary assignment of tasks to time slots with precedence and resource constraints.

**Algorithms & Tools:**

* D-Wave Ocean hybrid workflows
* Custom penalty tuning for constraint satisfaction
* Classical baselines (MILP solvers, greedy heuristics)

**Data / Benchmarks:**

* Standard RCPSP instances (PSPLIB)
* Synthetic projects with varied resource profiles

**Deliverables:**

* QUBO model conversion pipeline
* Solver comparison (annealing vs classical)
* Pareto front of schedule quality

**Difficulty:** Advanced

---

## 🧠 3. Large-Scale MaxCut with Divide-and-Conquer QAOA

**Focus:** Scalability of QAOA through algorithm design

**Description:**
Implement the **Divide-and-Conquer QAOA** strategy for large MaxCut problems by breaking graphs into subgraphs, solving with small quantum resources, and recombining results. Demonstrated to maintain competitive approximation ratios. ([arXiv][4])

**Problem Formulation:**
Maximize edge cuts in graphs (e.g., road networks, social graphs) via QUBO/Ising models.

**Algorithms & Tools:**

* QAOA (OpenQAOA, Qiskit)
* Subgraph partitioning and solution merging
* Simulation tools (Qulacs, Cirq)

**Data / Benchmarks:**

* GSET, ORLIB graph instances
* Real graphs (SNAP datasets)

**Deliverables:**

* Workflow for recursive partitioning
* QAOA subproblem solvers
* Graph recombination and quality metrics

**Difficulty:** Advanced / Research

---

## 🔌 4. Hybrid Workflow Scheduler for CI/CD Pipelines

**Focus:** Optimization of dependency workflow execution timelines

**Description:**
Build a scheduler that minimizes CI/CD pipeline duration by assigning tasks with dependencies to available compute slots. A prototype project on GitHub explores QAOA-like approaches for such DAG scheduling. ([Reddit][5])

**Problem Formulation:**
Binary variables for task-schedule pairs; constraints enforce dependencies and slot availability.

**Algorithms & Tools:**

* Qiskit Optimization + custom cost Hamiltonian
* Hybrid heuristic tuning
* Cloud execution via Amazon Braket or Azure Quantum

**Data / Benchmarks:**

* Synthetic DAGs of task workflows
* Real job logs (from GitHub/GitLab CI)

**Deliverables:**

* DAG → QUBO converter
* Scheduler implementation
* Case study on real pipeline logs

**Difficulty:** Intermediate

---

## ⚡ 5. Energy Grid Microgrid Optimization (Q-GRID)

**Focus:** Optimization in decentralized energy systems

**Description:**
Apply quantum optimization to energy grid problems like microgrid formation, energy exchange, or peer-to-peer trading. Recent work shows hybrid solvers can offer favorable runtime scaling for such energy dispatch problems. ([Springer][6])

**Problem Formulation:**
Multi-objective optimization balancing energy supply, cost, and stability via QUBO.

**Algorithms & Tools:**

* Hybrid quantum/classical solvers (D-Wave Leap)
* Multi-objective decomposition
* Constraint aggregation into weighted QUBO

**Data / Benchmarks:**

* Simplified grid models
* IEEE test systems (modified for QUBO)

**Deliverables:**

* Multi-objective QUBO model
* Solver workflow with Pareto front visualization
* Evaluation vs classical grid solvers

**Difficulty:** Advanced

---

## 📊 6. Multi-Objective Portfolio Optimization

**Focus:** Balancing return, risk, and ESG (environmental, social, governance)

**Description:**
Extend portfolio optimization to multi-objective settings (return vs risk vs ESG) and explore QUBO formulations and solver effectiveness. Recent studies use both quantum and simulated annealing to explore Pareto frontiers. ([MDPI][7])

**Problem Formulation:**
QUBO with multiple weighted objectives; extra binary indicator variables for decision patterns.

**Algorithms & Tools:**

* D-Wave or hybrid annealers
* Pareto frontier analysis
* Simulated annealing baselines

**Data / Benchmarks:**

* Public equity datasets
* ESG score data (Refinitiv, MSCI)

**Deliverables:**

* Multi-objective simulator
* Solver comparison on Pareto front quality
* Sensitivity analysis of weights

**Difficulty:** Advanced

---

## 🧩 7. Resource Allocation in Manufacturing

**Focus:** Production planning under capacity constraints

**Description:**
Encode classic manufacturing optimization problems (e.g., knapsack, resource allocation) into QUBO form and solve using hybrid optimization. These problems are directly relevant to operations management and have clear business impact. ([MDPI][8])

**Problem Formulation:**
Binary assignment of resources to tasks with capacity limits.

**Algorithms & Tools:**

* D-Wave Ocean dimod
* Qiskit hybrid solvers
* Local search for refinement

**Data / Benchmarks:**

* Standard scheduling and planning benchmarks
* ORLIB / QPLIB

**Deliverables:**

* QUBO builder for manufacturing cases
* Solver integration
* Real-data pilot results

**Difficulty:** Intermediate

---

## Deliverables Across Projects

For each project, aim to deliver:

* **Code repository** with Jupyter notebooks/scripts
* **QUBO/Ising modeling pipeline**
* **Solver integration (quantum + classical baselines)**
* **Evaluation metrics** (approximation ratio, time-to-solution, Pareto fronts)
* **Documentation + results dashboards**

---

## Recommended Implementation Tools

* **D-Wave Ocean SDK** for hybrid annealing workflows
* **Qiskit Optimization** & OpenQAOA for variational workflows
* **QUBO benchmark collections** (GSET, QPLIB, QOBLIB) for comparative evaluation

---
