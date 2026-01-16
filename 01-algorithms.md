
# 01 – Optimization Algorithms

Let us discuss the **core quantum and quantum-hybrid algorithms used for optimization**, focusing on:

* how each algorithm works at a functional level,
* which problem structures it is suitable for,
* realistic execution environments (gate-based, annealing, hybrid),
* practical limitations observed in experiments and deployments.

Our goal is **algorithm selection**, not theoretical completeness.

---

## Algorithm Selection Overview

Most optimization algorithms differ along three axes:

1. **Problem encoding** (QUBO / Ising / constrained binary)
2. **Execution model** (gate-based vs annealing vs hybrid)
3. **Scalability under noise and constraints**

### High-Level Mapping

| Algorithm Family    | Best Problem Types         | Execution Model        | Current Deployment Viability |
| ------------------- | -------------------------- | ---------------------- | -------------------- |
| QAOA                | Sparse QUBO, graph cuts    | Gate-based             | 🟡 Experimental      |
| Annealing           | Dense QUBO, scheduling     | Annealer / Hybrid      | ✅ Deployable         |
| Adiabatic QC        | Structured Hamiltonians    | Annealer               | 🟡 Experimental      |
| Quantum Walk        | Search, routing            | Gate-based             | 🔴 Research          |
| Variational Hybrids | Small constrained problems | Gate-based + classical | 🟡 Experimental      |
| Quantum-Inspired    | Large-scale optimization   | Classical              | ✅ Deployable         |

---

## 1. Variational Algorithms

Variational algorithms dominate **gate-based quantum optimization** due to their tolerance to noise and hybrid structure.

---

### 1.1 Quantum Approximate Optimization Algorithm (QAOA)

#### Core Idea

QAOA alternates between:

* a **problem Hamiltonian** (encoding the objective),
* a **mixing Hamiltonian** (explores the solution space),

with parameters optimized by a classical loop.

```
QUBO → Hamiltonian → Parameterized circuit → Measurement
                        ↑
                 Classical optimizer
```

#### Best-Suited Problems

| Property                     | Suitability |
| ---------------------------- | ----------- |
| Sparse interaction graph     | High        |
| Low constraint density       | High        |
| Hard feasibility constraints | Poor        |

Typical examples:

* MaxCut
* Graph partitioning
* Simplified portfolio optimization

#### Realistic Use Cases

* Benchmarking graph optimization
* Studying noise vs circuit depth trade-offs
* Algorithmic research (parameter transferability)

#### Limitations

* Circuit depth grows with approximation quality
* Parameter optimization landscapes can be flat
* No competitive advantage over classical solvers at scale

**Deployment Status:** 🟡 Experimental

---

### 1.2 VQE-Based Optimization

Originally designed for chemistry, VQE variants are sometimes adapted for optimization by encoding cost functions into expectation values.

#### Practical Assessment

* Flexible ansatz design
* Poor scalability for discrete constraints
* Rarely preferred over QAOA for pure optimization

**Deployment Status:** 🔴 Research-only for optimization

---

## 2. Annealing and Adiabatic Methods

Annealing-based approaches are currently the **most practical path for quantum optimization deployment**.

---

### 2.1 Quantum Annealing

#### Core Idea

Start in an easy-to-prepare ground state and slowly evolve toward the problem Hamiltonian.

```
Initial Hamiltonian → Adiabatic evolution → Final Hamiltonian
```

#### Strengths

| Feature             | Impact                        |
| ------------------- | ----------------------------- |
| Native QUBO support | Minimal encoding overhead     |
| Constraint handling | Straightforward via penalties |
| Hardware maturity   | Higher than gate-based        |

#### Best-Suited Problems

* Scheduling (TFISP, job assignment)
* Portfolio optimization
* Resource allocation
* Binary constraint problems with soft constraints

#### Real-World Use Cases

* Workforce and task scheduling
* Manufacturing resource planning
* Traffic signal timing (simplified models)

Often executed using **hybrid solvers**, where:

* the quantum processor explores solution space,
* classical components refine feasibility.

**Deployment Status:** ✅ Deployable (hybrid)

---

### 2.2 Adiabatic Quantum Computing (AQC)

Closely related to annealing, but analyzed more formally under adiabatic theorems.

#### Practical Notes

* Same hardware as annealing
* Gap scaling limits theoretical guarantees
* Mostly relevant for analysis, not deployment

**Deployment Status:** 🟡 Experimental

---

## 3. Hybrid Quantum–Classical Optimization

Hybrid solvers combine **classical heuristics with quantum subroutines**.

---

### 3.1 Hybrid Decomposition Solvers

#### Approach

* Split large problems into subproblems
* Use quantum annealing for local search
* Recombine using classical heuristics

```
Large problem
   ↓
Subproblem decomposition
   ↓
Quantum sampling
   ↓
Classical recombination
```

#### Best-Suited Problems

* Scheduling with fixed time windows
* Medium-scale QUBOs (100s–1000s variables)
* Problems with modular structure

#### Realistic Use Cases

* TFISP
* Production scheduling
* Energy dispatch optimization (simplified)

**Deployment Status:** ✅ Deployable

---

## 4. Quantum Walk and Search-Based Methods

Quantum walks generalize classical random walks for search problems.

#### Practical Assessment

* Elegant theoretical results
* Poor constraint handling
* Limited tooling support

Primarily useful for:

* academic exploration,
* unstructured search models.

**Deployment Status:** 🔴 Research-only

---

## 5. Quantum-Inspired Classical Algorithms

While not quantum, these algorithms borrow ideas from quantum mechanics.

---

### 5.1 Simulated Annealing Variants

* Often outperform real quantum hardware
* Used as baselines
* Essential for fair benchmarking

---

### 5.2 Tensor Network Optimization

#### Strengths

* Efficient simulation of low-treewidth QAOA
* Strong classical competitor to NISQ devices

Used extensively to:

* test algorithm scaling,
* validate claimed quantum advantage.

**Deployment Status:** ✅ Deployable (classical)

---

## Algorithm Viability by Problem Class

| Problem Class          | Recommended Algorithms            |
| ---------------------- | --------------------------------- |
| TFISP                  | Quantum annealing, hybrid solvers |
| Portfolio optimization | Annealing, QAOA (small)           |
| MaxCut                 | QAOA, annealing                   |
| Job-shop scheduling    | Hybrid annealing                  |
| TSP                    | Hybrid annealing (small)          |
| VRP                    | Classical / quantum-inspired only |

---

## Key Practical Takeaways

1. **Annealing with hybrid methods are currently the most viable**
2. Gate-based optimization is still benchmarking-focused
3. Constraint structure matters more than problem size
4. Classical baselines are mandatory for credibility

---
