import numpy as np
from qiskit import QuantumCircuit
from qiskit.quantum_info import SparsePauliOp
from qiskit.primitives import StatevectorEstimator


# -----------------------------
# Problem: Simple VQE Hamiltonian
# -----------------------------


#Transverse Field Ising Model
def build_hamiltonian(n):
    terms = []
    
    # ZZ interactions
    for i in range(n-1):
        pauli = ["I"] * n
        pauli[i] = "Z"
        pauli[i+1] = "Z"
        terms.append(("".join(pauli), 1.0))
    
    # X field
    for i in range(n):
        pauli = ["I"] * n
        pauli[i] = "X"
        terms.append(("".join(pauli), 1.0))
    
    return SparsePauliOp.from_list(terms)

H=build_hamiltonian(n)
