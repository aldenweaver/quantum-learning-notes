# Quantum Computing Basics Notes

## Procedure for Computations Using Quantum Circuits
1. Encode input
2. Do operations on bits
3. Extract output

+ First part is changed with new input, rest remains the same
+ 4 qubits: use first two for computation & last two for encoding computation
+ Logic gates: basic operations of computing
+ NOT gate
+ More powerful gates too
+ Half adder: add bigger numbers by breaking everything down into just adding two bits
+ XOR gate: "controlled NOT gate" aka CNOT; figures out if two bits are different or not
+ Pair of qubits: 
  + Input A: control qubit (dot)
  + Input B: target qubit (big circle with cross like target mark)
+ Qiskit: CNOT circuit method is `.cx()`; takes the indices of the two qubits it acts on as arguments