# fermpiler
Quantum Compiler for Simulating the Time-Evolution of Fermionic Hamiltonians

The interest here is to develop an end-to-end compiler for algorithms taking as input fermionic Hamiltonians. In particular, simulating the time evolution of a fermionic Hamiltonian will be our first algorithm of interest, as it requires no variational optimization. 

# High Level Compilation Flow
The high-level workflow of the compiler is as follows:
- For some fermionic Hamiltonian input, carry out Hamiltonian reduction and optimization (Preprocessing Step)
- Carry out fermion-to-qubit encoding (Qubit Encoding Step)
- Trotterize the resulting Hamiltonian after qubit encoding, producing our Hamiltonian time evolution circuit (Trotterization Step)
- Carry out any remaining optimizations on the trotterized circuit, e.g. hardware-aware optimizations (Post-processing Step)

Each of these steps have a variety of potential optimizations, which have been explored in the literature (some referenced below). The novel approach, here, is integrating these techniques within an end-to-end compiler for fermionic Hamiltonians, which, to the best of my knowledge, has not been done.

# Open Problems
As stated above, to the best of my knowledge, there does not exist any end-to-end compilers for simulating fermionic Hamiltonians. This is subsumed into a larger open problem, which is performing computationally feasible quantum chemistry simulation. In particular, empirical analysis involving the simulation of medium to large-scale fermionic Hamiltonians has not been carried out on domain-specific compilers. The bulk of literature surrounding fermionic Hamiltonian simulation uses general purposes, state-of-the-art compilers. 

# Initial References
## Fermionic Hamiltonian Optimization
- https://arxiv.org/pdf/1706.03637
- https://arxiv.org/pdf/2110.10701

## Fermion-to-Qubit Encoding
- https://arxiv.org/pdf/2403.17794 (Fermihedral: SAT Reduction)
- https://arxiv.org/pdf/2409.02010 (HATT: Ternary Tree)

## Quantum Compilers for Hamiltonian Simulation
- https://arxiv.org/pdf/2108.02099 (2QAN: Trotter Permutation)
- https://arxiv.org/pdf/2504.07214 (Partial Trotterization)

- https://github.com/QuantumComputingLab/f3c (Repo for the following two references)
- https://arxiv.org/abs/2108.03282
- https://arxiv.org/abs/2108.03283

## Hardware-Aware Optimizations
- https://arxiv.org/pdf/2105.07127
