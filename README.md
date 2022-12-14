# Shor's Algorithm on Qiskit and Cirq simulators

Group members: 

  - Venkata Satyanarayana Chivatam

  - Rania Ouassif

  - Rakshitha Ravi

  - Shaun Soobagrah

## Problem description: 

Exploring the implementation of Shor's algorithm to solve period finding problem on Google and IBM quantum simulators

## Methodology:

As part of this project, we are going to implement the shor's algorithm to factorize a given n-bit number. We will explore two implementations of Shor's algorithm, one using IBM's Qiskit library and the other using Google's Cirq library and run them in their respective simulators.

We are trying to factor a given number N which is equal to the product of P and Q, where P and Q are prime numbers. This, when solved classically, takes exponential runtime. But when run on a quantum computer, it takes only polynomial runtime. This exponential speedup is caused by Shor's algorithm.

## Shor's Algorithm: 

We implement QPE (Quantum Phase Estimation) in which we apply unitary operators N times to get the phase of the state that repeats the period. This state will be converted from fourier basis to computational basis using inverse quantum fourier transform which will allow us to find the r (period). We can then easily find the factors using gcd(a^{r/2} ±1 , N) where a is a guess number.

Shor's algorithm involves two components. Quantum fourier transform and Quantum phase estimation.

Quantum Fourier transform: 

QFT transforms computation basis(|0⟩, |1⟩) to fourier basis (|+⟩, |-⟩). This is done so that the X-basis states are transformed into Z-basis states which allow us to determine the value stored based on the angle of the state in the Bloch sphere and change it using quantized angle rotations. 

QFT can be implemented using Hadamard gate and a CROT gate(controlled angle rotation).

Quantum Phase estimation: 

QPE applies unitary operation on the states which are in fourier basis to obtain the eigenvalue of the state (considering the state to be an eigenvector). This eigenvalue can help us obtain the phase rotation that is required in inverse quantum fourier transform. Upon that, Inverse quantum fourier transform is applied to transform the fourier basis states into computational basis. Inverse Quantum fourier transform does the exact opposite of QFT and its implementation also requires the same gates as of QFT.

QPE can be implemented using hadamard gates, unitary operator gates and inverse QFT implementation.

We intend on writing shor's algorithm in IBM's qiskit library and google's cirq library

## Testing: 

We will verify the resulting factors from the simulators with the factors resulting from a classical approach.
