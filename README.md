# Quantum Teleportation Simulation using Qiskit

## Important Note

This is **only a practice / educational project** created to explore quantum computing concepts using Qiskit.
It is not intended as an optimized or research-level implementation.

---

## Overview

This project is a **practice implementation of the quantum teleportation protocol** using **Qiskit**.
It demonstrates how an arbitrary quantum state can be teleported from one qubit (Alice) to another qubit (Bob) using:

* Entanglement (Bell pair creation)
* Quantum gates
* Coherent correction (without classical conditional gates)
* Ideal and noisy simulations
* State fidelity verification

The goal of this project is **learning and experimentation**, not production or research deployment.

---

## Features

* Preparation of an arbitrary quantum state using rotation gates
* Creation of Bell entangled pair
* Implementation of teleportation circuit with **coherent correction**
* Simulation on:

  * Ideal quantum simulator
  * Noisy quantum simulator (depolarizing noise model)
* Histogram comparison of measurement results
* Fidelity calculation to verify teleportation success
* Automatic saving of output plots

---

## Project Structure

```
.
├── teleportation.ipynb / teleportation.py
├── outputs/
│   └── teleportation_histogram.png
└── README.md
```

---

## Installation

Install required libraries:

```bash
pip install qiskit qiskit-aer matplotlib numpy
```

---

## How It Works

### 1. Message State Preparation

An arbitrary qubit state is prepared using:

* `RY(theta)`
* `RZ(phi)`

This represents the quantum information to be teleported.

### 2. Entanglement Creation

A Bell pair is created between qubits 1 and 2 using:

* Hadamard gate
* CNOT gate

### 3. Teleportation Protocol

Alice performs:

* CNOT between message and Bell qubit
* Hadamard on message qubit

Bob performs **coherent corrections** using:

* CNOT
* Controlled-Z

This avoids classical measurement-based correction and works across Qiskit versions.

### 4. Simulation

Two types of simulations are performed:

#### Ideal Simulation

* Uses `AerSimulator`
* No noise model

#### Noisy Simulation

* Uses depolarizing noise:

  * 1-qubit error probability: 0.01
  * 2-qubit error probability: 0.05

### 5. Fidelity Verification

* Final 3-qubit statevector is generated
* Bob’s qubit is extracted using **partial trace**
* Fidelity is computed with the original message state

Teleportation is considered successful if fidelity is close to **1**.

---

## Example Output

* Measurement histograms comparing ideal vs noisy teleportation
* Saved plot:

```
outputs/teleportation_histogram.png
```

* Fidelity value:

```
Teleportation Fidelity ≈ 1.0
Perfect Teleportation Achieved
```

---

## Learning Objectives

This practice project helps in understanding:

* Quantum state preparation
* Entanglement and Bell states
* Quantum teleportation protocol
* Noise modelling in quantum circuits
* Density matrices and partial trace
* Fidelity as a performance metric

---
