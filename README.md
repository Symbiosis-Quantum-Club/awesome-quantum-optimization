# ⭐ Awesome-Quantum-Optimization

*A curated, implementation-focused guide to **quantum optimization**. We shall discuss problem formulations, algorithms, tools, datasets, benchmarks, and practical project directions.*


---

## Overview

Quantum optimization is currently **one of the most important and fastest-growing subfields within quantum computing**, bridging quantum algorithms, physical QC hardware models, applied mathematics, and industrial use cases. 
**Quantum optimization** studies how quantum and quantum-inspired algorithms can be applied to continuous optimization problems. Many of today’s most promising quantum algorithms; such as **QAOA (Quantum Approximate Optimization Algorithm)**, **Adiabatic Quantum Computation**, **Quantum Annealing**, and **Quantum-Inspired Optimizers** - are specifically designed to solve or approximate solutions to difficult optimization & efficiency problems.

Most practical approaches reduce problems to **QUBO (Quadratic Unconstrained Binary Optimization)** or **Ising Hamiltonians**, which can then be processed using the following techniques:

* gate-based variational algorithms (e.g., QAOA),
* analog / adiabatic methods,
* quantum annealing,
* hybrid quantum–classical solvers,
* quantum-inspired classical approximations.

This repository focuses on **what can be implemented today** using existing hardware, simulators, and hybrid workflows, rather than speculative long-term algorithms.

---

## Current Problem–Algorithm Pipeline for Quantum Optimization Projects

```
Optimization Problem
      ↓
QUBO / Ising Encoding
      ↓
Quantum / Hybrid Algorithm
      ↓
Hardware or Simulator
      ↓
Benchmarking & Evaluation
```

Each document in this repository corresponds to a specific stage of this pipeline.

---

## Repository Structure


| File                                                             | Scope                                                                          |
| ---------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `README.md`                                                      | High-level map of quantum optimization workflows                               |
| [`01-algorithms.md`](01-algorithms.md)                           | Variational, annealing, adiabatic, walk-based, and quantum-inspired algorithms |
| [`02-problems.md`](02-problems.md)                               | Optimization problems with known QUBO / Ising formulations                     |
| [`03-tools-and-libraries.md`](03-tools-and-libraries.md)         | SDKs, modeling tools, solvers, and simulators                                  |
| [`04-datasets-and-benchmarks.md`](04-datasets-and-benchmarks.md) | Benchmark instances, metrics, and evaluation methods                           |
| [`05-papers-and-theory.md`](05-papers-and-theory.md)             | Key papers, theoretical foundations, proofs, and complexity analyses           |
| [`06-project-ideas.md`](06-project-ideas.md)                     | Deployable and research-grade project templates                                |

---

## Target Use Cases

This repository emphasizes optimization tasks that:

* have easily implementable QUBO / Ising encodings,
* can be executed on current quantum hardware or simulators,
* support hybrid or classical baselines for comparison.

Representative domains include:

* **Graph optimization**: MaxCut, community detection, network flow
* **Routing & scheduling**: TSP, job-shop scheduling, TFISP, vehicle routing
* **Finance**: portfolio optimization, risk-constrained allocation
* **Constraint satisfaction**: binary constraints, penalty-based formulations
* **Energy & infrastructure**: unit commitment, grid dispatch (small-scale)

---

## Algorithms Covered

The repository focuses on algorithmic families that are actively used or evaluated today:

* **Variational algorithms**
  QAOA, warm-start QAOA, adaptive ansätze, VQE-based optimization

* **Annealing and adiabatic methods**
  Quantum annealing, reverse annealing, adiabatic quantum computation

* **Quantum walk–based methods**
  Walk-based search, hitting-time–driven optimization

* **Pauli-based and adaptive constructions**
  Operator pooling, problem-informed ansätze

* **Quantum-inspired classical algorithms**
  Tensor networks, simulated annealing variants, digital annealers

Details and implementation guidance are in [`01-algorithms.md`](01-algorithms.md).

---

## Tooling and Execution

Practical implementations rely on:

* **Modeling layers** for QUBO / Ising construction
* **Quantum SDKs** for circuit execution or annealing
* **Hybrid solvers** combining classical heuristics with quantum sampling
* **Simulators** for scaling and debugging

Commonly used toolchains are summarized in [`03-tools-and-libraries.md`](03-tools-and-libraries.md).

---

## Benchmarking and Evaluation

This repository treats benchmarking as a **first-class requirement**.

Evaluation topics include:

* approximation ratio and solution quality,
* time-to-solution and sampling cost,
* scaling behavior with problem size,
* comparison against classical heuristics.

Benchmark datasets and metrics are documented in
[`04-datasets-and-benchmarks.md`](04-datasets-and-benchmarks.md).

---
## Papers and Academic Resources

This section collects the theoretical foundations, canonical papers, surveys, and recommended reading that underpin the practical material in this repository. It is structured so readers can pick the right level: short introductions, focused algorithm papers, mapping/formulation references, and deeper theoretical or complexity results.

- Foundational algorithm papers (implementer-first)
  - "A Quantum Approximate Optimization Algorithm" — E. Farhi, J. Goldstone, S. Gutmann (introduces QAOA and basic performance discussion).
  - Key adiabatic / annealing works — the foundational adiabatic quantum computing and quantum annealing papers that introduce the adiabatic paradigm and early algorithmic experiments.

- QUBO / Ising formulations and encodings
  - Survey-style references describing how to map combinatorial problems to QUBO / Ising, explicit encodings for MaxCut, TSP, partitioning, scheduling, and portfolio optimization. These are essential when preparing instances for hardware or simulators.

- Theory, complexity, and approximation
  - Results on approximation guarantees, hardness of approximation, and limitations for quantum heuristics.
  - Papers analyzing depth/parameter scaling (e.g., low-depth QAOA performance on specific problems) and provable gaps/upper bounds.

- Hardware and empirical studies
  - Empirical benchmarking papers that compare quantum annealers, short-depth variational circuits, and classical baselines. These studies are helpful to understand noise impacts and practical performance.
  - Papers describing device models and readout/postprocessing techniques for quantum annealers and gate-based devices.

- Surveys and reviews
  - Review articles and survey papers covering the landscape of quantum optimization, hybrid workflows, and quantum-inspired algorithms. These are useful starting points for newcomers and for locating further references.

- Textbooks & background
  - Standard quantum computing textbooks for necessary background material (e.g., quantum circuits, Hamiltonian dynamics).
  - Classical optimization texts for methods and baselines used as comparisons.

How this maps to the repository
- Use [`05-papers-and-theory.md`](05-papers-and-theory.md) for the full annotated bibliography, grouped references, and suggested reading order.
- For each project in [`06-project-ideas.md`](06-project-ideas.md), consult the linked sub-section in `05-papers-and-theory.md` to find the most relevant theory and papers.

Contributing pointers
- If you add or find a paper that clearly belongs in a subsection (e.g., QAOA performance bounds, Ising encodings, device benchmarks), please add it to `05-papers-and-theory.md` with a one-line annotation and, if possible, a stable link.
- Mark especially useful reproducible-experiment papers with the tag "reproducible" so readers can easily find experiments to repeat.

---

## Project-Oriented Focus

Rather than isolated examples, this repository discusses **end-to-end optimization pipelines**:

* problem definition → QUBO formulation,
* algorithm selection,
* solver execution,
* classical baseline comparison,
* performance analysis.

Concrete, implementable project templates are collected in
[`06-project-ideas.md`](06-project-ideas.md).

These are suitable for:

* academic projects,
* applied Quantum Optimization research,
* Quantum hackathons,
* proof-of-concept deployments.

---

## Scope and Limitations

* No claim of general quantum advantage
* Emphasis on small- to medium-scale problem instances
* Explicit comparison to classical and hybrid baselines
* Clear distinction between experimental and deployable methods

---


## License

MIT License — see [`LICENSE`](LICENSE).

---

