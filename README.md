

# ⭐ **awesome-quantum-optimization**

*A curated collection of algorithms, libraries, datasets, benchmarks, papers, tools, and learning resources in the field of **Quantum Optimization**.*


Quantum optimization is currently **one of the most important and fastest-growing subfields of quantum computing**, bridging quantum algorithms, physical hardware models, applied mathematics, operations research, and industrial use cases. Many of today’s most promising quantum algorithms—such as **QAOA (Quantum Approximate Optimization Algorithm)**, **Adiabatic Quantum Computation**, **Quantum Annealing**, and **Quantum-Inspired Optimizers**—are specifically designed to solve or approximate solutions to difficult optimization problems.

As quantum hardware evolves (superconducting qubits, trapped ions, photonics, Rydberg arrays), organizations, researchers, and practitioners increasingly need a clear, structured way to understand:

* **What quantum optimization algorithms exist?**
* **Which libraries or frameworks implement them?**
* **What problems can be encoded as QUBO/Ising models?**
* **What datasets and benchmarks should be used for comparison?**
* **Which papers are foundational or state-of-the-art?**
* **Where can one learn—courses, tutorials, videos?**

Whether you are a researcher, engineer, student, or enthusiast, this repository will help you understand the landscape, choose the right tools, compare algorithms, and explore the cutting edge of quantum optimization.

---

# 🚀 Algorithms

Quantum optimization spans multiple algorithmic paradigms. Each folder provides:

* Theoretical overview
* Links to original papers
* Implementations (Python notebooks, libraries)
* Real-world examples
* Benchmarks and comparisons

| Category                                                      | Description                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **[Variational](algorithms/variational/README.md)**           | Covers hybrid quantum-classical algorithms like **QAOA**, **VQE-optimization variants**, **layer-wise training**, and **warm-start QAOA**. These methods rely on a classical optimizer tuning quantum circuit parameters to minimize an objective function. Ideal for near-term noisy intermediate-scale quantum (NISQ) hardware. |
| **[Annealing](algorithms/annealing/README.md)**               | Includes **quantum annealing**, **reverse annealing**, **hybrid solvers**, and **D-Wave’s heuristic sampling tools**. Based on slowly evolving a Hamiltonian to encode problem minima. Widely used for industrial optimization tasks.                                                                                             |
| **[Quantum Walk](algorithms/quantum-walk/README.md)**         | Focused on quantum-walk–based optimization and search, including **hitting-time algorithms**, **walk-based local search**, and **graph traversal heuristics**. Strong connections to Grover-like speedups.                                                                                                                        |
| **[Pauli-Based](algorithms/pauli-based/README.md)**           | Algorithms built around **Pauli operator decompositions**, dynamic circuit construction, **operator pooling**, generalized ansätze, and advanced QAOA derivatives. A more expressive alternative to fixed-layer variational circuits.                                                                                             |
| **[Adiabatic](algorithms/adiabatic/README.md)**               | Covers **Adiabatic Quantum Computation (AQC)**, a generalized form of annealing. Includes theoretical guarantees, spectral gap analysis, and techniques to maintain adiabaticity under hardware constraints.                                                                                                                      |
| **[Quantum-Inspired](algorithms/quantum-inspired/README.md)** | Includes **tensor networks**, **digital annealers**, **simulated QAOA**, and classical approximations inspired by quantum principles. Often competitive with quantum hardware for near-term problem sizes.                                                                                                                        |

---

# 🧰 Libraries & SDKs

These frameworks provide ready-made tools for modeling optimization problems, building circuits, running QAOA/AQC/annealing, simulating quantum devices, and using hybrid solvers.

| Library                                                            | Description                                                                                                                                                                          |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **[Qiskit Optimization](libraries/qiskit-optimization/README.md)** | High-level modeling framework for QUBO/Ising problems integrated with QAOA, VQE, classical solvers, and IBM Quantum hardware. Offers a strong OR-friendly API.                       |
| **[Cirq Optimizers](libraries/cirq-optimizers/README.md)**         | A collection of Cirq-compatible optimization tools: circuit factories, optimizers, QAOA libraries, and parameter sweep utilities. Designed for Google's quantum hardware ecosystem.  |
| **[D-Wave Ocean SDK](libraries/dwave-ocean-sdk/README.md)**        | The standard toolkit for D-Wave's quantum annealers. Includes **dimod**, **neal**, hybrid solvers, QUBO models, and energy sampling tools. Used heavily for industrial applications. |
| **[TensorFlow Quantum](libraries/tensorflow-quantum/README.md)**   | Combines TensorFlow with quantum circuit differentiation, enabling **machine-learning-driven optimization**, quantum neural networks, and differentiable QAOA.                       |
| **[Qulacs Optimizers](libraries/qulacs-optim/README.md)**          | Provides extremely fast simulation capabilities for QAOA and VQE. Often used for state-of-the-art variational algorithm research thanks to its performance and customizability.      |

---

# 🧩 Problems

These folders explain how classical optimization problems are represented as **QUBO** or **Ising** Hamiltonians—essential for executing them on QAOA or annealers.

| Problem                                                                 | Description                                                                                                                    |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **[MaxCut](problems/maxcut/README.md)**                                 | The canonical benchmark problem for QAOA. Includes graph-based QUBOs, example circuits, and analytical approximations.         |
| **[Traveling Salesman Problem (TSP)](problems/tsp/README.md)**          | A classic NP-hard routing problem. Learn multiple QUBO encodings, penalty tuning, and strategies for quantum annealers & QAOA. |
| **[Portfolio Optimization](problems/portfolio/README.md)**              | Covers mean-variance optimization, cardinality constraints, risk penalties, and quantum finance examples.                      |
| **[Scheduling](problems/scheduling/README.md)**                         | Includes TFISP, job-shop scheduling, vehicle routing, resource allocation, and other complex workflow optimization tasks.      |
| **[Constraint Programming](problems/constraint-programming/README.md)** | General patterns for encoding binary constraints, penalties, and modular constraint systems into QUBO/Ising form.              |

---

# 📊 Datasets

Datasets are crucial for reproducibility and benchmarking. Each dataset includes links, formats, example loading scripts, and suitability for various quantum solvers.

| Dataset                                                             | Description                                                                                                |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **[Ising Instances](datasets/ising-instances/README.md)**           | Spin-glass problems, random Ising models, frustrated systems—excellent for annealing and QAOA testing.     |
| **[QUBO Benchmarks](datasets/QUBO-benchmarks/README.md)**           | Includes ORLIB, QPLIB, GSET, and synthetic QUBOs widely used in research, competitions, and meta-analyses. |
| **[Network Optimization](datasets/network-optimization/README.md)** | Routing, network flows, graph instances—ideal for walk-based and annealing-based solvers.                  |
| **[Finance](datasets/finance/README.md)**                           | Covariance matrices, return time series, and financial datasets for portfolio problems and risk modeling.  |

---

# ⚖ Benchmarks

Benchmarking enables fair and transparent comparisons between quantum and classical solvers.

| Benchmark                                                              | Focus                                                                                                                    |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **[QAOA Performance](benchmarks/qaoa-performance/README.md)**          | Studies on QAOA depth vs performance, optimization landscapes, initialization strategies, and gradient behavior.         |
| **[Annealing vs Gate Models](benchmarks/annealing-vs-gate/README.md)** | Comparisons among D-Wave annealing, analog Rydberg optimization, and digital circuit-based QAOA.                         |
| **[Quantum vs Classical](benchmarks/quantum-vs-classical/README.md)**  | Benchmarking quantum solvers against classical heuristics, simulated annealing, and tensor networks to assess advantage. |
| **[Metrics](benchmarks/metrics/README.md)**                            | Definitions of approximation ratio, time-to-solution, spectral gap, sampling quality, and performance bounds.            |

---

# 📄 Papers

A curated, structured library of foundational, modern, review, and applied research.

| Category                                          | Description                                                                                                                               |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **[Foundational](papers/foundational/README.md)** | Seminal works such as Farhi’s QAOA paper (2014), Lucas’ QUBO mappings, AQC theory, and early optimization models.                         |
| **[2020s](papers/2020s/README.md)**               | State-of-the-art techniques: warm-start QAOA, counterdiabatic driving, depth-efficient ansätze, and hardware-informed optimization.       |
| **[Surveys](papers/surveys/README.md)**           | Comprehensive reviews, meta-analyses, and comparison papers helpful for newcomers and researchers.                                        |
| **[Applications](papers/applications/README.md)** | Real-world industrial applications including logistics, power grids, finance, telecom optimization, drug discovery, scheduling, and more. |

---

# 🎓 Resources

These learning materials offer multiple entry points for beginners and advanced learners.

| Resource                                       | Description                                                                                    |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **[Tutorials](resources/tutorials/README.md)** | Hands-on introductions, Jupyter notebooks, and end-to-end examples using various quantum SDKs. |
| **[Courses](resources/courses/README.md)**     | University courses, MOOCs, lecture notes, and professional certification paths.                |
| **[Videos](resources/videos/README.md)**       | Talks, workshops, conference keynotes, summer schools, and visual explainers.                  |
| **[Blogs](resources/blogs/README.md)**         | Articles, newsletters, digestible insights, and concept breakdowns from experts.               |

---
