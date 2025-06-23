# ⚙️ Multi-Controlled Unitary Construction with Basic Gates in Qiskit

This code constructs a multi-controlled unitary gate \( C^n U \), using only 1-qubit unitaries and `cx` gates.

## Overview

Before constructing the multi-controlled gate (`MCU`), we first define:
- A **controlled-unitary gate** (`cv_gate`) using the **ZYZ decomposition**, 
- A **Toffoli gate** with flexible control/target assignment.

These constructions follow **Nielsen and Chuang**:
- `cv_gate`: *Figure 4.6*
- `Toffoli`: *Figure 4.9*
- `MCU`: *Figure 4.10*

Lastly, we benchmark the implementation for small values of \( n \), showing gate counts, circuit depth, and ancilla usage.

---

## Benchmark Results

| n | Gate Count | Circuit Depth | Ancillas |
|--:|------------|----------------|----------|
| 2 | {'cx': 14, 't': 8, 'tdg': 6, 'h': 4, 'rz': 2, 'ry': 1} | 25 | 1 |
| 3 | {'cx': 26, 't': 16, 'tdg': 12, 'h': 8, 'rz': 2, 'ry': 1} | 46 | 2 |
| 4 | {'cx': 38, 't': 24, 'tdg': 18, 'h': 12, 'rz': 2, 'ry': 1} | 67 | 3 |
| 5 | {'cx': 50, 't': 32, 'tdg': 24, 'h': 16, 'rz': 2, 'ry': 1} | 88 | 4 |

- **Gate count growth:** \( O(n^2) \)
- **Circuit depth growth:** \( O(n) \)
- **Ancilla usage:** \( O(n) \)

---

## Usage Instructions

1. **Run the cell of packages**
   
2. **If they're not already compiled, run the markup cell explaining the MCU gate and ZYZ decomposition**
   
3. **Run the `cv_gate` cell**  
   - (Optional) Uncomment the example usage line to view the circuit for a random unitary.

4. **Run the `toffoli` cell**  
   - (Optional) Uncomment the example usage line to view the Toffoli circuit.

5. **Run the `MCU` cell**  
   - (Optional) Uncomment the example usage line to view the multi-control circuit for \( n = 3 \) and a random unitary.

6. **Run the benchmarking cell**  
   - Displays gate counts, circuit depths, and ancilla counts for  n = 2:6.

---

## References

- Nielsen, M. A., & Chuang, I. L. (2010). *Quantum Computation and Quantum Information* (10th Anniversary Edition).  
  - Figure 4.6: Controlled-unitary decomposition  
  - Figure 4.9: Toffoli gate  
  - Figure 4.10: Multi-controlled unitaries

