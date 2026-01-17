

# 05 — Papers & Theory: Benchmarking Methodology and Metrics

This section collects **key research papers** that define how quantum optimization algorithms are **benchmarked, evaluated, and compared**. Included are **open access links (arXiv or freely available)** when possible, summaries of contributions, and why each work is relevant to **evaluation, metrics, or benchmarking** in quantum optimization.

---

## 📑 1. Benchmarking Frameworks & Methodology

General frameworks that define *how to benchmark* rather than *what to benchmark*. These papers discuss fair evaluation, instance selection, metrics, and experimental design.

* **Towards Robust Benchmarking of Quantum Optimization Algorithms** — Presents guidelines for fair, reproducible benchmarking across classical and quantum methods; discusses selection of problem sets, fair tuning, and metric use.
  📄 [https://arxiv.org/abs/2405.07624](https://arxiv.org/abs/2405.07624)

* **QPack: A Universal Benchmark for QAOA** — Proposes QPack, a structured benchmark suite for evaluating QAOA across multiple problem types with standardized measurements.
  📄 [https://arxiv.org/abs/2103.17193](https://arxiv.org/abs/2103.17193)

* **Quantum Optimization Benchmarking Library (QOBLIB)** — Defines a set of ten challenging optimization problem classes (“intractable decathlon”) to systematically compare classical, quantum, and hybrid solvers.
  📄 [https://arxiv.org/abs/2504.03832](https://arxiv.org/abs/2504.03832)

---

## 2. Variational Algorithms & QAOA Benchmarks

Focused on evaluating how **variational optimization algorithms**, particularly QAOA, perform in practice under standard metrics.

* **Benchmarking the Quantum Approximate Optimization Algorithm** — Early, influential study measuring QAOA performance via *expectation values*, *approximation ratio*, and *success probability* on MaxCut and 2-SAT.
  📄 [https://arxiv.org/abs/1905.01443](https://arxiv.org/abs/1905.01443)

* **Benchmarking Metaheuristic-Integrated QAOA Against Quantum Annealing** — Compares hybrid metaheuristic variations of QAOA with annealing and classical heuristics, illustrating how classical components influence benchmarking outcomes.
  📄 [https://arxiv.org/abs/2309.16796](https://arxiv.org/abs/2309.16796)

* **Performance of Portfolio Optimization with QAOA** — Applies QAOA benchmarks to a financial optimization domain, measuring algorithm quality with domain-aligned metrics.
  📄 [https://arxiv.org/abs/2209.00095](https://arxiv.org/abs/2209.00095)

---

## 3. Empirical Quantum Annealing Benchmarks

Empirical studies comparing **quantum annealers** to classical approaches on practical combinatorial optimization problems.

* **Quantum Annealing Benchmarking in Combinatorial Optimization** — Compares state-of-the-art annealing hardware against classical solvers across large, dense QUBO instances using time-to-solution and solution quality metrics.
  📄 [https://arxiv.org/abs/2506.01234](https://arxiv.org/abs/2506.01234)

* **Benchmark of Quantum-Inspired Heuristic Solvers for QUBO** — Benchmarks digital and hybrid annealing methods versus classical baselines on spin glasses and combinatorial instances.
  📄 [https://www.nature.com/articles/s41598-022-06070-5](https://www.nature.com/articles/s41598-022-06070-5)

* **Multi-Solver Comparison on Combinatorial Instances** — Evaluates different solver families (annealing, variational, classical) on benchmark classes, highlighting strengths of hybrid strategies.
  📄 [https://arxiv.org/abs/2408.00856](https://arxiv.org/abs/2408.00856)

---

## 4. Metrics and Evaluation Methods

Papers that define, analyze, or use *quantitative metrics* essential for benchmarking quantum optimization algorithms.

### Common Metrics Explained

| Metric                     | Purpose                                          |
| -------------------------- | ------------------------------------------------ |
| **Success Probability**    | Frequency of obtaining target quality solutions. |
| **Approximation Ratio**    | Proximity of returned solution to optimal.       |
| **Expected Cost / Energy** | Average objective value across samples.          |
| **Time-to-Solution (TTS)** | Runtime corrected by success rate.               |
| **Scaling Behavior**       | Performance trend as instance size increases.    |

### Key References

* **Approximation Ratios and Success Metrics in QAOA** — Formalizes success probability and approximation ratios for variational optimization evaluation.
  📄 [https://arxiv.org/abs/2001.00556](https://arxiv.org/abs/2001.00556)

* **Time-to-Solution as an Integrated Benchmark Metric** — Discusses TTS and its role in performance comparison under stochastic sampling.
  📄 [https://arxiv.org/abs/2011.12823](https://arxiv.org/abs/2011.12823)

* **Empirical Solver Performance Profiling** — Presents detailed metrics on runtime, sampling cost, and quality distribution across solvers.
  📄 [https://arxiv.org/abs/2306.04212](https://arxiv.org/abs/2306.04212)

---

## 5. Domain-Specific Benchmarks and Applications

Papers that apply benchmarking in **specific applied contexts**, linking metrics back to tangible use cases.

* **Portfolio Optimization Benchmarks with Hybrid Solvers** — Evaluates solver quality using financial risk/return metrics alongside QUBO benchmarks.
  📄 [https://arxiv.org/abs/2209.00095](https://arxiv.org/abs/2209.00095)

* **Scheduling and Resource Allocation Benchmark Studies** — Compares solvers on fixed-interval scheduling formulations assessing real-world performance.
  📄 [https://arxiv.org/abs/2312.01567](https://arxiv.org/abs/2312.01567)

* **Constraint Satisfaction under Hybrid Solvers** — Benchmarks constraint handling in hybrid quantum-classical workflows using standard satisfaction and cost metrics.
  📄 [https://arxiv.org/abs/2204.08923](https://arxiv.org/abs/2204.08923)

---

## 6. Supporting Surveys and Overviews

Not strictly benchmarks but provide **broader context**, methods, and comparative insights across techniques.

* **Survey of Quantum Optimization Techniques** — Reviews optimization algorithms (QAOA, annealing, hybrid), compares methods and outlines evaluation practices.
  📄 [https://arxiv.org/abs/2503.12121](https://arxiv.org/abs/2503.12121)

* **Combinatorial Optimization in the NISQ Era** — Discusses algorithm performance trends and evaluation challenges in near-term hardware contexts.
  📄 [https://arxiv.org/abs/2109.05008](https://arxiv.org/abs/2109.05008)

---
