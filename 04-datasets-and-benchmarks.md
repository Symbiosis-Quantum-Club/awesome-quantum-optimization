# 04 – Datasets & Benchmarks

Here we discuss **benchmark datasets, instance collections, evaluation metrics, and benchmarking methods** relevant to quantum optimization. The goal is to help practitioners select **standard instances**, choose **quality metrics**, and set up **fair comparisons** for optimization solvers.

---

## Why Benchmarks Matter

Benchmarking serves two purposes in quantum optimization:

1. **Comparative evaluation**  
   Assess how different solvers (quantum, hybrid, classical) perform on a common set of problems.

2. **Progress tracking**  
   Quantify solver improvements and hardware scaling over time.

A good benchmark consists of:

- A **collection of problem instances**
- Clearly defined **success criteria**
- Well-defined **performance metrics**

---

## 1. Benchmark Instance Libraries

These collections provide standard optimization problems in QUBO, Ising, or related formats.

### Common Benchmark Repositories

| Dataset / Library | Description | Link |
|------------------|-------------|------|
| **QOPTLib** | Combinatorial optimization instances including TSP, VRP, bin packing, and MaxCut curated for quantum benchmarking. | https://data.mendeley.com/datasets/h32z9kcz3s |
| **Fixstars Amplify Benchmark** | Benchmark framework with predefined sets including TSPLIB, QPLIB, GSET, and CVRPLIB. | https://github.com/fixstars/amplify-benchmark |
| **QOBLIB** | Ten optimization problem classes designed for systematic quantum and classical benchmarking. | https://git.zib.de/qopt/qoblib-quantum-optimization-benchmarking-library |
| **QUBO.org Benchmarks** | Repository comparing classical and quantum QUBO solvers. | https://www.qubos.org |
| **Hamiltonian Library** | Collection of Hamiltonians for optimization and simulation tasks. | https://arxiv.org/abs/2306.13126 |

---

## Instance Categories

Benchmarks often use diverse problem types to stress solvers across different structural regimes.

| Instance Type | Typical Use | Example Source |
|--------------|-------------|----------------|
| **MaxCut and spin glasses** | Connectivity and structure scaling | QOPTLib, HamLib |
| **TSP and routing** | Structured combinatorial optimization | QOPTLib, Amplify |
| **Quadratic Assignment** | Dense interaction graphs | Amplify |
| **Random dense QUBO** | Heuristic stress testing | QUBO.org |
| **Constraint satisfaction families** | Hard feasibility regions | QOBLIB |

---

## 2. Evaluation Metrics

Effective benchmarking requires well-defined performance metrics.

---

### 2.1 Approximation Ratio

The **Approximation Ratio (AR)** measures solution quality relative to known bounds.

$$
\text{AR} = \frac{C_{\text{best}} - C_{\text{solver}}}{C_{\text{best}} - C_{\text{worst}}}
$$

Where:

- **C-best** — best known optimal cost  
- **C-solver** — cost obtained by the solver  
- **C-worst** — worst possible cost for the instance  

Interpretation:

- **AR = 1.0** indicates an optimal solution  
- **AR < 1.0** indicates sub-optimal performance  
- Lower values indicate worse performance  

---

### 2.2 Time-to-Solution

**Time-to-Solution (TTS)** combines runtime and probabilistic success.


- Annealing-based solvers
- Hybrid quantum-classical methods

---

### 2.3 Success Probability

The proportion of solver runs that reach a target solution quality.

Commonly used for:

- QAOA benchmarks
- Quantum annealing experiments

---

### 2.4 Scaling Metrics

Scaling metrics track solver behavior as problem size increases.

| Metric | Description |
|------|-------------|
| **Cost scaling** | Objective quality versus problem size |
| **Time scaling** | Runtime growth with number of variables |
| **Solution distribution** | Variance across repeated runs |

These metrics are typically visualized using empirical scaling plots.

---

## 3. Benchmark Frameworks and Tools

Benchmark frameworks standardize execution, data collection, and comparison.

### Amplify Benchmark Framework

- Command-line interface for benchmark execution
- Supports multiple solvers and parallel runs
- Includes predefined benchmark suites

#### Workflow Diagram

```mermaid
flowchart TD
    A[Benchmark Instances]
    B[Job Set Definition]
    C[Solver Set]
    D[Run Benchmarks]
    E[Analyze Results]

    A --> B
    B --> C
    C --> D
    D --> E
````

---

## 4. Benchmark Setup Pipeline

```mermaid
flowchart TD
    P[Raw Problem]
    E[Instance Encoding]
    S[Solver Execution]
    Q[Solution Samples]
    M[Metric Computation]
    C[Cross Solver Comparison]

    P --> E
    E --> S
    S --> Q
    Q --> M
    M --> C
```

Explanation:

1. Encode real-world problems into QUBO or Ising form
2. Execute quantum, hybrid, or classical solvers
3. Collect multiple solution samples
4. Compute benchmark metrics
5. Compare solver performance across instances

---

## 5. Research References on Benchmarking

Key academic work defining benchmarks and evaluation methodology.

* **Quantum Optimization Benchmarking Library (QOBLIB)**
  Defines ten challenging problem classes for fair solver comparison.

* **Benchmarking the Quantum Approximate Optimization Algorithm**
  Introduces energy and success metrics for QAOA performance studies.

* **Quantum Annealing vs Classical Solvers**
  Empirical comparison of dense QUBO instances across solver paradigms.

* **Quantum-Inspired Heuristic Benchmarking**
  Evaluation of hybrid, annealing, and digital solvers on spin glass models.

* **QOPTLib Benchmark Suite**
  Benchmark collection tailored for combinatorial optimization problems.

---

## 6. Benchmark Summary Table

| Resource                | Type           | Focus                     | Notes                             |
| ----------------------- | -------------- | ------------------------- | --------------------------------- |
| **QOPTLib**             | Dataset        | Optimization instances    | General-purpose benchmark         |
| **Amplify Benchmark**   | Framework      | QUBO problems             | CLI and visualization             |
| **QOBLIB**              | Library        | Hard optimization classes | Fair quantum-classical comparison |
| **QUBO.org**            | Benchmark site | Solver comparison         | Classical vs quantum              |
| **Hamiltonian Library** | Dataset        | Hamiltonians              | Optimization and simulation       |
| **QAOA benchmarking**   | Research       | QAOA metrics              | Energy and success rates          |

---

## 7. Practical Tips for Benchmarking

* Use **standardized instances** to avoid bias
* Report **multiple metrics** for completeness
* Include **classical baselines**
* Carefully tune **penalty weights** in QUBO and Ising formulations

---
