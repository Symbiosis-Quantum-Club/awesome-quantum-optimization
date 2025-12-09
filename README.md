

# ⭐ **awesome-quantum-optimization**

*A curated collection of algorithms, libraries, datasets, benchmarks, papers, and resources related to Quantum Optimization.*

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Quantum optimization is one of the fastest-growing areas in quantum computing—spanning QAOA, AQC, quantum annealing, tensor networks, quantum-inspired solvers, hybrid variational methods, and industrial applications.

This repository organizes the ecosystem into clean categories so users can easily explore the landscape.

---

# 📚 **Table of Contents**

### 🔹 [Algorithms](#algorithms)

### 🔹 [Libraries & SDKs](#libraries--sdks)

### 🔹 [Optimization Problems](#problems)

### 🔹 [Datasets for Quantum Optimization](#datasets)

### 🔹 [Benchmarks & Metrics](#benchmarks)

### 🔹 [Research Papers](#papers)

### 🔹 [Learning Resources](#resources)

---

# 🚀 Algorithms

Quantum optimization algorithm families.

| Category                                                      | Description                                                    |
| ------------------------------------------------------------- | -------------------------------------------------------------- |
| **[Variational](algorithms/variational/README.md)**           | QAOA, VQE-optimization, layerwise training, warm-start methods |
| **[Annealing](algorithms/annealing/README.md)**               | Quantum annealing, reverse annealing, D-Wave heuristic solvers |
| **[Quantum Walk](algorithms/quantum-walk/README.md)**         | Hitting-time optimization, walk-based search                   |
| **[Pauli-Based](algorithms/pauli-based/README.md)**           | Operator pooling, Pauli decompositions, generalized ansätze    |
| **[Adiabatic](algorithms/adiabatic/README.md)**               | Adiabatic quantum computation (AQC), beyond standard annealing |
| **[Quantum-Inspired](algorithms/quantum-inspired/README.md)** | Tensor networks, digital annealers, simulated QAOA             |

---

# 🧰 Libraries & SDKs

Tools, frameworks, and simulation toolkits.

| Library                                                            | Description                                   |
| ------------------------------------------------------------------ | --------------------------------------------- |
| **[Qiskit Optimization](libraries/qiskit-optimization/README.md)** | QUBO modeling, QAOA, classical solvers        |
| **[Cirq Optimizers](libraries/cirq-optimizers/README.md)**         | Cirq ecosystem tooling for optimization       |
| **[D-Wave Ocean SDK](libraries/dwave-ocean-sdk/README.md)**        | Ocean tools (dimod, neal), QUBO/Ising solvers |
| **[TensorFlow Quantum](libraries/tensorflow-quantum/README.md)**   | Hybrid ML + quantum optimization workflows    |
| **[Qulacs Optimizers](libraries/qulacs-optim/README.md)**          | Fast simulators + QAOA-based tools            |

---

# 🧩 Problems

Common optimization problem templates with QUBO/Ising formulations.

| Problem                                                                 | Description                                  |
| ----------------------------------------------------------------------- | -------------------------------------------- |
| **[MaxCut](problems/maxcut/README.md)**                                 | Standard benchmark for QAOA and annealing    |
| **[Traveling Salesman Problem (TSP)](problems/tsp/README.md)**          | QUBO formulations for routing                |
| **[Portfolio Optimization](problems/portfolio/README.md)**              | Risk-return models, quantum finance          |
| **[Scheduling](problems/scheduling/README.md)**                         | TFISP, job-shop scheduling, graph scheduling |
| **[Constraint Programming](problems/constraint-programming/README.md)** | General encoding strategies                  |

---

# 📊 Datasets

Public datasets for benchmarking and research.

| Dataset                                                             | Description                                |
| ------------------------------------------------------------------- | ------------------------------------------ |
| **[Ising Instances](datasets/ising-instances/README.md)**           | Spin glasses, frustrated systems           |
| **[QUBO Benchmarks](datasets/QUBO-benchmarks/README.md)**           | ORLIB, QPLIB, GSET, synthetic QUBOs        |
| **[Network Optimization](datasets/network-optimization/README.md)** | Graph routing, network flow                |
| **[Finance](datasets/finance/README.md)**                           | Covariance matrices, financial time series |

---

# ⚖ Benchmarks

Comparative studies, analysis tools, and performance metrics.

| Benchmark                                                              | Focus                                |
| ---------------------------------------------------------------------- | ------------------------------------ |
| **[QAOA Performance](benchmarks/qaoa-performance/README.md)**          | Depth scaling, landscapes            |
| **[Annealing vs Gate Models](benchmarks/annealing-vs-gate/README.md)** | QA vs QAOA vs Rydberg analog         |
| **[Quantum vs Classical](benchmarks/quantum-vs-classical/README.md)**  | Fair comparisons, scaling behavior   |
| **[Metrics](benchmarks/metrics/README.md)**                            | Approximation ratio, TTS, energy gap |

---

# 📄 Papers

Categorized quantum optimization literature.

| Category                                          | Description                                                               |
| ------------------------------------------------- | ------------------------------------------------------------------------- |
| **[Foundational](papers/foundational/README.md)** | QAOA (2014), Lucas’ QUBO mappings, core theory                            |
| **[2020s](papers/2020s/README.md)**               | Warm-start QAOA, counterdiabatic, expressive ansätze                      |
| **[Surveys](papers/surveys/README.md)**           | Comprehensive review papers                                               |
| **[Applications](papers/applications/README.md)** | Industrial optimization (logistics, energy, finance, telecom, healthcare) |

---

# 🎓 Resources

Learning and educational materials.

| Resource                                       | Description                                  |
| ---------------------------------------------- | -------------------------------------------- |
| **[Tutorials](resources/tutorials/README.md)** | Hands-on guides & notebooks                  |
| **[Courses](resources/courses/README.md)**     | University courses & lecture series          |
| **[Videos](resources/videos/README.md)**       | Talks, workshops, YouTube/Conference content |
| **[Blogs](resources/blogs/README.md)**         | Articles, newsletters, explainers            |

---

# 🤝 Contributing

Contributions are welcome!
Feel free to open an issue or submit a pull request.

---

# 📜 License

MIT License — free to use and share.

---
