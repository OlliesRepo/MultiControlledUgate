# ⚙️ Multi-Controlled Unitary Construction with Basic Gates in Qiskit

This project implements the construction of an arbitrary, multi-controlled, single-qubit unitary gate using ancilla qubits, built exclusively from simple 1-qubit gates, (via ZYZ decomposition), and CNOT (CX) gates. All logic is constructed from the universal gate set {U, CX}. 

Each function is preceded by derivations and justifications in Markdown cells, explaining the decomposition, inspired by the approach of Nielsen & Chuang (2010).
Each function displays it's corresponding circuit when run. 

The final function, MCU(n, U), MultiControlled U gate, has 2 inputs, n = the number of qubits, U = any unitary.

> 📄 Reference:  
> Nielsen, M. A., & Chuang, I. L. (2010). *Quantum Computation and Quantum Information* (10th anniversary ed., p. 181). Cambridge University Press.

---

## 📚 Contents

- ZYZ decomposition of arbitrary 1-qubit unitary gates  
- Construction of controlled-unitary (`cv_gate`) from ZYZ parameters  
- Toffoli gate implementation from Clifford+T and CNOT gates  
- Recursive construction of multi-controlled unitary gates (`MCU`) with ancilla qubits  
- Circuit visualization and benchmarking (gate counts, depth, ancilla usage)

---

## 🧠 Theory and Justification

- Each function is annotated with mathematical derivations or explanations for correctness and optimality.  
- The `cv_gate` uses ZYZ decomposition and carefully extracts Euler angles to reconstruct any single-qubit unitary from elementary gates.  
- The Toffoli implementation is given in terms of elementary gates (H, T, T†, CX), and serves as a building block for higher controlled gates.  
- The `MCU` function recursively builds a multi-controlled \(U\) gate by controlling ancilla qubits in layers, leveraging the Toffoli construction and `cv_gate`.  
- Benchmarks illustrate the resource scaling, showing gate count grows as \(O(n^2)\), circuit depth as \(O(n)\), and ancilla count as \(O(n)\).

