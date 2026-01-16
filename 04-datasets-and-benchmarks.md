# 04 – Datasets & Benchmarks

Here we will discuss **benchmark datasets, instance collections, evaluation metrics, and benchmarking methods** relevant to quantum optimization. It is intended to help practitioners select **standard instances**, choose **quality metrics**, and set up **fair comparisons** for optimization solvers.

---

## Why Benchmarks Matter

Benchmarking serves two purposes in quantum optimization:

1. **Comparative evaluation:** Assess how different solvers (quantum, hybrid, classical) perform on a common set of problems.
2. **Progress tracking:** Quantify solver improvements and hardware scaling over time.

A good benchmark consists of:

* a **collection of problem instances**,
* clearly defined **criteria** for success,
* and **metrics** for solver performance.

---

## 1. Benchmark Instance Libraries

These collections provide standard optimization problems in QUBO, Ising, or related formats.

### Common Benchmark Repositories

| Dataset / Library                                      | Description                                                                                                                                       | Link                                                                                           |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **QOPTLib**                                            | Combinatorial optimization instances (TSP, VRP, bin-packing, MaxCut) curated for quantum benchmarking. ([Mendeley Data][1])                       | [https://data.mendeley.com/datasets/h32z9kcz3s](https://data.mendeley.com/datasets/h32z9kcz3s) |
| **Fixstars Amplify Benchmark**                         | Framework with pre-defined benchmark sets (TSPLIB, QPLIB, GSET, CVRPLIB). ([GitHub][2])                                                           | [https://github.com/fixstars/amplify-benchmark](https://github.com/fixstars/amplify-benchmark) |
| **QOBLIB (Quantum Optimization Benchmarking Library)** | 10 optimization problem classes designed for systematic benchmarking of quantum and classical methods (intractable decathlon concept). ([IBM][3]) | [https://git.zib.de/qopt/qoblib-quantum-optimization-benchmarking-library/]                     |
| **QUBO.org Benchmarks**                                | Repository and comparisons of classical and quantum QUBO solver performance. ([QUBO Solver Benchmark][4])                                         | [https://www.qubos.org/](https://www.qubos.org/)                                               |
| **Hamiltonian Library (HamLib)**                       | Broad collection of Hamiltonians for benchmarking both optimization and simulation tasks (e.g., MaxCut, SAT variants). ([arXiv][5])               | [https://arxiv.org/abs/2306.13126]                                                     |

---

## Instance Categories

Benchmarks often use diverse problem types to stress solvers along different dimensions:

| Instance Type                        | Typical Use                       | Example Source   |
| ------------------------------------ | --------------------------------- | ---------------- |
| **MaxCut & spin glasses**            | Structure vs connectivity scaling | QOPTLib, HamLib  |
| **TSP & routing**                    | Structured combinatorial          | QOPTLib, Amplify |
| **Quadratic Assignment (QAP)**       | Dense interactions                | Amplify          |
| **Random dense QUBO**                | Stress test for heuristics        | QUBO.org         |
| **Constraint satisfaction families** | Hard feasibility regions          | QOBLIB           |

---

## 2. Evaluation Metrics

Effective benchmarking requires well-defined performance metrics. Below are the most commonly used metrics in optimization benchmarking.

---

### 2.1 Approximation Ratio

The **Approximation Ratio (AR)** measures the quality of a solver’s solution relative to known optimal bounds:

\[
\text{Approximation Ratio (AR)} =
\frac{C_{\text{solver}} - C_{\text{worst}}}
{C_{\text{best}} - C_{\text{worst}}}
\]

**Where:**

- \( C_{\text{best}} \): Best known (optimal) cost  
- \( C_{\text{solver}} \): Cost obtained by the solver  
- \( C_{\text{worst}} \): Worst possible cost for the problem instance  

*(Adapted from IBM Quantum documentation)*

**Interpretation:**

- **AR = 1.0** → Optimal solution  
- **AR = 0.0** → Worst possible solution  
- **0 < AR < 1** → Quality improves as the value approaches 1

---

### 2.2 Time-to-Solution (TTS)

**Time-to-Solution** is a composite metric combining time and probabilistic success:

```
TTS = time_per_sample × log(1−target_confidence) / log(1−success_prob)
```

Where `success_prob` is the empirical probability of obtaining a solution of required quality.

TTS is especially useful when comparing:

* stochastic heuristics,
* annealing samplers,
* hybrid methods.

---

### 2.3 Success Probability

Proportion of repeated solver runs that reach target quality (e.g., optimum or within tolerance).
Often used for:

* QAOA benchmarks,
* annealing sampling.

---

### 2.4 Scaling Metrics

These metrics track solver behavior as problem size increases:

| Metric                    | What It Measures                        |
| ------------------------- | --------------------------------------- |
| **Cost Scaling**          | How objective quality changes with size |
| **Time Scaling**          | Execution time growth with variables    |
| **Solution Distribution** | Variability of solutions over runs      |

These are often used in **empirical scaling plots**.

---

## 3. Benchmark Frameworks & Tools

Frameworks help standardize execution, comparison, and visualization of solver results.

### 🔹 Amplify Benchmark

* CLI for running benchmarks across solvers and collecting results.
* Supports parallel execution and result visualization.
* Pre-defined benchmark jobs include TSPLIB, GSET, QPLIB, CVRPLIB. ([GitHub][2])

**Typical workflow:**

```mermaid
flowchart TD
    Instances[Benchmark Instances]
    JobFile[Job Set Definition]
    Solver[Solver Set (Quantum/Classical)]
    Execute[Run Benchmarks]
    Results[Analyze Results]
    Instances --> JobFile --> Solver --> Execute --> Results
```

---

## 4. Benchmark Setup Diagram

```mermaid
flowchart TD
    P[Raw Problem] --> E[Instance Encoding (QUBO/Ising)]
    E --> S[Solver Execution]
    S --> Q[Solution Samples]
    Q --> M[Metric Computation]
    M --> C[Comparison Across Solvers]
```

**Explanation:**

1. **Instance Encoding:** Convert real-world problems into QUBO/Ising form.
2. **Solver Execution:** Run quantum, hybrid, or classical solvers.
3. **Solution Sampling:** Collect multiple runs to understand distribution.
4. **Metric Computation:** Compute AR, TTS, success probability.
5. **Comparison:** Determine relative performance across solvers and instances.

---

## 5. Research References on Benchmarking

Academic papers provide rigor, standard benchmarks, and evaluation methodology.

### Benchmark Design & Metrics

* **Quantum Optimization Benchmarking Library (QOBLIB):** Defines ten challenging problem classes for fair comparative benchmarks. ([IBM][3])

* **Benchmarking the quantum approximate optimization algorithm:** A foundational study of QAOA performance on weighted MaxCut and 2-SAT instances, introducing energy and success metrics. ([Springer Link][7])

* **Benchmarking quantum annealing vs classical solvers:** Recent empirical study contrasting solution quality and time for dense QUBOs with both quantum and classical approaches. ([Nature][8])

* **Benchmark of quantum-inspired heuristic solvers for QUBO:** Comparison of hybrid, annealing, and digital solvers including spin glass and real-world style problems. ([Nature][9])

* **QOPTLib benchmark suite:** A proposed benchmark collection for combinatorial problems like TSP, bin packing, VRP, and MaxCut, tailored to quantum and hybrid methods. ([Emergent Mind][10])

---

## 6. Benchmark Summary Table

| Resource                | Type                    | Focus                            | Notes                                                                  |
| ----------------------- | ----------------------- | -------------------------------- | ---------------------------------------------------------------------- |
| **QOPTLib**             | Dataset                 | Optimization instances           | General-purpose benchmark set for 4 problem types ([Mendeley Data][1]) |
| **Amplify Benchmark**   | Framework + sets        | QUBO problems                    | CLI + visualization + solver integration ([GitHub][2])                 |
| **QOBLIB**              | Library + benchmark set | Challenging optimization classes | Designed for fair quantum vs classical comparison ([IBM][3])           |
| **QUBO.org**            | Benchmark site          | Solver comparison                | Classical vs quantum comparisons ([QUBO Solver Benchmark][4])          |
| **HamLib**              | Hamiltonian dataset     | Broad range                      | Quantum simulation + optimization uses ([arXiv][5])                    |
| QAOA benchmarking paper | Research                | QAOA performance                 | Energy, success probability metrics ([Springer Link][7])               |

---

## 7. Practical Tips for Benchmarking

* **Use standardized instances** to avoid bias.
* **Record multiple metrics** (e.g., AR, TTS, success rate) for a holistic view.
* **Run baselines** with classical heuristics (simulated annealing, tabu search).
* **Tight penalty calibration** in QUBO/Ising can drastically affect metric outcomes.

---
