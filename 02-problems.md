---

# 02 – Optimization Problems

This document describes **optimization problem classes relevant to quantum and hybrid optimization**, with emphasis on:

* how problems arise in real systems,
* how they are translated into QUBO / Ising form,
* which quantum approaches are appropriate,
* how realistic deployment is on current hardware.

The goal is to help readers **select problems that are both meaningful and implementable**, rather than theoretically attractive but impractical.

---

## Deployment Realism Classification

Each problem is tagged according to current feasibility.

| Tag                  | Interpretation                                                                |
| -------------------- | ----------------------------------------------------------------------------- |
| ✅ **Deployable**     | End-to-end implementation possible today using hybrid solvers or simulators   |
| 🟡 **Experimental**  | Small-scale execution feasible; primarily useful for benchmarking or research |
| 🔴 **Research-only** | Encoding or scaling limits prevent meaningful deployment                      |

---

## General Optimization Workflow

Most problems in this document follow the same modeling and execution pipeline:

```
Real-world optimization problem
        ↓
Binary variable definition
        ↓
QUBO / Ising formulation
        ↓
Quantum or hybrid solver
        ↓
Classical baseline comparison
```

The feasibility of a problem is largely determined by:

* number of binary variables,
* constraint density,
* penalty magnitude required for feasibility,
* solver connectivity limits.

---

## 1. Graph Optimization Problems

Graph problems are common benchmarks because they map naturally to pairwise binary interactions.

---

### 1.1 MaxCut

**Deployment Tag:** 🟡 Experimental

#### Problem Description

Given a graph ( G(V, E) ), partition the vertices into two sets such that the number (or weight) of edges crossing the partition is maximized.

#### Real-World Context

* Network segmentation
* Circuit layout
* Social network analysis (simplified)

#### QUBO / Ising Structure

| Component   | Description                         |
| ----------- | ----------------------------------- |
| Variables   | One binary variable per vertex      |
| Objective   | Reward edges cut between partitions |
| Constraints | None (naturally unconstrained)      |

This simplicity makes MaxCut a canonical benchmark.

#### Suitable Algorithms

* QAOA (low depth)
* Quantum annealing
* Tensor-network classical simulators

#### Practical Notes

* Scales poorly beyond tens of nodes on quantum hardware
* Strong classical heuristics exist
* Best used for **algorithmic benchmarking**, not deployment

---

### 1.2 Community Detection

**Deployment Tag:** 🟡 Experimental

#### Description

Partition a graph into multiple communities by maximizing modularity or related metrics.

#### Modeling Challenges

* Requires multi-class assignment
* Often converted to binary via one-hot encoding
* Variable count grows quickly

#### Practical Implications

* Useful for testing constraint-handling strategies
* Limited deployment relevance without heavy simplification

---

## 2. Routing and Scheduling Problems

Scheduling problems are often more relevant to industry but introduce significant constraint complexity.

---

### 2.1 Traveling Salesman Problem (TSP)

**Deployment Tag:** 🟡 Experimental

#### Problem Description

Find the shortest route that visits each city exactly once and returns to the origin.

#### QUBO Encoding Characteristics

| Aspect      | Impact                                       |
| ----------- | -------------------------------------------- |
| Variables   | ( O(n^2) ) (city × position)                 |
| Constraints | One city per position, one position per city |
| Penalties   | Dominant over objective                      |

#### Algorithm Suitability

* Quantum annealing (small (n))
* Hybrid solvers
* Simulated QAOA

#### Practical Assessment

* Useful for demonstrating QUBO modeling
* Not competitive for real routing tasks
* Appropriate for **educational and benchmarking use**

---

### 2.2 Job-Shop Scheduling

**Deployment Tag:** 🟡 Experimental

#### Description

Schedule jobs across machines to minimize makespan or tardiness.

#### Modeling Approach

* Time-indexed binary variables
* Large number of constraints
* Highly sensitive penalty tuning

#### Usefulness

* Good test case for constraint encoding
* Practical only at toy scale

---

### 2.3 Tactical Fixed Interval Scheduling Problem (TFISP)

**Deployment Tag:** ✅ Deployable

#### Description

Assign tasks to fixed time intervals under resource and precedence constraints.

#### Why TFISP Is Practical

| Property            | Advantage                |
| ------------------- | ------------------------ |
| Time discretization | Natural binary variables |
| Sparse constraints  | Lower coupling density   |
| Modular structure   | Hybrid-friendly          |

#### Typical Workflow

```
Task definitions
   ↓
Interval assignment variables
   ↓
Constraint penalties
   ↓
QUBO construction
   ↓
Hybrid solver execution
```

#### Recommended Algorithms

* Quantum annealing
* Hybrid quantum–classical solvers

TFISP is one of the **strongest candidates for near-term quantum optimization projects**.

---

### 2.4 Vehicle Routing Problem (VRP)

**Deployment Tag:** 🔴 Research-only

#### Limitations

* Extremely constraint-heavy
* Large variable counts
* Poor performance on current solvers

---

## 3. Finance and Economics

Financial problems often yield compact QUBOs with interpretable objectives.

---

### 3.1 Portfolio Optimization

**Deployment Tag:** ✅ Deployable

#### Description

Allocate capital across assets to balance expected return and risk.

#### QUBO Structure

| Term        | Meaning             |
| ----------- | ------------------- |
| Linear      | Expected return     |
| Quadratic   | Covariance (risk)   |
| Constraints | Budget, cardinality |

#### Algorithms

* QAOA
* Quantum annealing
* Hybrid solvers

#### Practical Notes

* Small portfolios (10–50 assets) feasible
* Requires strong classical baselines
* Well-suited for proof-of-concept deployments

---

### 3.2 Risk-Constrained Optimization

**Deployment Tag:** 🟡 Experimental

#### Notes

* Non-quadratic risk metrics require approximation
* Sensitive to encoding choices

---

## 4. Constraint Satisfaction Problems (CSPs)

---

### 4.1 Binary CSPs

**Deployment Tag:** 🟡 Experimental

#### Description

Satisfy Boolean constraints expressed as clauses.

#### Implementation Notes

* Converted via penalty-based QUBOs
* Often infeasible without careful scaling

#### Use Case

* Studying feasibility vs optimization trade-offs

---

### 4.2 General CSPs

**Deployment Tag:** 🔴 Research-only

---

## Summary: Problem Feasibility Matrix

| Problem Class          | Feasibility |
| ---------------------- | ----------- |
| TFISP                  | ✅           |
| Portfolio Optimization | ✅           |
| MaxCut                 | 🟡          |
| TSP                    | 🟡          |
| Job-Shop Scheduling    | 🟡          |
| Community Detection    | 🟡          |
| VRP                    | 🔴          |
| Network Flow           | 🔴          |
| General CSPs           | 🔴          |

---

## Recommended Problem Entry Points

For **deployable or near-deployable projects**, start with:

1. Tactical Fixed Interval Scheduling (TFISP)
2. Portfolio Optimization
3. Small MaxCut benchmarks
4. Simplified scheduling variants

These problems provide:

* clear modeling structure,
* reasonable solver compatibility,
* meaningful evaluation metrics.

---
