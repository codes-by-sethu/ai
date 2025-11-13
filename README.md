# Artificial Intelligence Algorithm Project: Optimization of Biscuit Production

This project applies **AI algorithms** to optimize biscuit production from a fixed-size dough roll, maximizing profit while adhering to manufacturing constraints. Two approaches are implemented: **Constraint Satisfaction with Dynamic Programming (CSP + DP)** and a **Genetic Algorithm (GA)**.

---

## 🎯 Problem Statement

A biscuit factory needs to arrange various biscuit types on a **500-position dough roll** to maximize production and profit, while ensuring:

* No overlapping biscuits
* Defect thresholds are not violated
* Biscuits are placed at integer positions
* Total biscuit length does not exceed the dough roll
* Penalty of **-1** per unused dough position

---

## ⚙️ Algorithms Implemented

### 1. CSP with Dynamic Programming

* Uses a DP table to compute maximum score from each position
* Biscuits are prioritized by **value-to-length ratio**
* Feasibility checks handle defect thresholds efficiently
* Transition: skip a position (penalty) or place the highest-value valid biscuit

### 2. Genetic Algorithm (GA)

* **Chromosome:** 500-position array with biscuit IDs or -1 for unused positions
* **Fitness Function:** sum of biscuit values minus penalties for unused positions
* **Evolutionary Operators:**

  * Selection: Tournament
  * Crossover: Single-point
  * Mutation: Random replacement of biscuit placement

---

## 🍪 Biscuit Types

| ID | Length | Value | Max Defects (a, b, c) |
| -- | ------ | ----- | --------------------- |
| 0  | 4      | 3     | 1, 2, 3               |
| 1  | 5      | 4     | 4, 2, 2               |
| 2  | 1      | 2     | 1, 2, 1               |
| 3  | 2      | 3     | 2, 1, 2               |

---

## 📈 Results

| Algorithm              | Best Score |
| ---------------------- | ---------- |
| CSP + DP               | 715        |
| Genetic Algorithm (GA) | 771        |

> The GA outperformed CSP + DP, showing stronger exploration and better handling of complex constraints.

---

## ✅ Conclusion

The **Genetic Algorithm** is recommended for solving the biscuit production problem due to its ability to find higher-profit arrangements under multiple constraints.

---

## 🛠️ Technologies Used

* Python
* AI/Optimization Libraries (NumPy, random, etc.)
* Dynamic Programming
* Genetic Algorithm techniques
