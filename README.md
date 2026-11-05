# Quantum Computing Basics

A beginner-friendly Python project for learning **quantum computing** through hands-on experiments using [Qiskit](https://www.ibm.com/quantum/qiskit).

This repository explores fundamental quantum computing concepts, including qubits, superposition, entanglement, quantum gates, and measurement.

## Overview

Quantum computing uses principles of quantum mechanics to process information differently from classical computers.

While classical computers use bits (`0` or `1`), quantum computers use **qubits**, which can exist in a superposition of states.

This project provides simple, executable examples to help understand how quantum circuits work.

## Tech Stack

- **Python 3.13** — Programming language
- **Qiskit** — Quantum circuit development
- **Qiskit Aer** — Quantum circuit simulation
- **NumPy** — Numerical computing
- **Matplotlib** — Data visualization
- **Jupyter Notebook** — Interactive experiments
- **uv** — Python dependency and environment management
- **Pytest** — Automated testing
- **Ruff** — Python linting and formatting

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Byusa/quantum-computing-basics.git
cd quantum-computing-basics
```

### 2. Install dependencies

Install [uv](https://docs.astral.sh/uv/) if you haven't already.

```bash
brew install uv
```

Then synchronize the project dependencies:

```bash
uv sync
```

This creates a local `.venv` environment and installs the dependencies specified in `pyproject.toml` and `uv.lock`.

### 3. Run your first quantum experiment

```bash
uv run main.py
```

## Experiment 1: Quantum Superposition

Our first experiment demonstrates quantum superposition using a single qubit.

### Python Code

```python
from qiskit import QuantumCircuit
from qiskit_aer import AerSimulator

# Create a circuit with one qubit and one classical bit
qc = QuantumCircuit(1, 1)

# Apply a Hadamard gate to create superposition
qc.h(0)

# Measure the qubit
qc.measure(0, 0)

# Display the circuit
print(qc)

# Execute the circuit 1,000 times
simulator = AerSimulator()
result = simulator.run(qc, shots=1000).result()

# Display measurement results
print(result.get_counts())
```

### Quantum Circuit

```text
     ┌───┐┌─┐
  q: ┤ H ├┤M├
     └───┘└╥┘
c: 1/══════╩═
           0
```

**Explanation:**

1. Initialize one qubit in state `|0⟩`.
2. Apply the Hadamard (`H`) gate to create superposition.
3. Measure the qubit, obtaining either `0` or `1`.
4. Repeat the experiment 1,000 times to observe the measurement distribution.

### Example Output

```python
{'0': 465, '1': 535}
```

| Measurement | Count | Percentage |
|---|---:|---:|
| 0 | 465 | 46.5% |
| 1 | 535 | 53.5% |

Each measurement has a theoretical probability of **50%** for either outcome.

Actual results vary because quantum measurement is probabilistic.

## Core Concepts

| Concept | Description |
|---|---|
| Qubit | Basic unit of quantum information |
| Superposition | A quantum state combining multiple basis states |
| Entanglement | Quantum correlations between multiple qubits |
| Quantum Gates | Operations that manipulate quantum states |
| Measurement | Extracting classical outcomes from quantum states |
| Quantum Circuit | A sequence of quantum operations |

## Learning Roadmap

- [x] Experiment 1 — Quantum Superposition
- [ ] Experiment 2 — Quantum Entanglement
- [ ] Experiment 3 — Quantum Gates
- [ ] Experiment 4 — Bell States
- [ ] Experiment 5 — Quantum Teleportation
- [ ] Experiment 6 — Grover's Search Algorithm
- [ ] Experiment 7 — Quantum Fourier Transform
- [ ] Experiment 8 — Shor's Algorithm

## Future Improvements

- Visualize quantum measurement distributions.
- Add interactive Jupyter notebooks.
- Introduce automated tests for quantum circuits.
- Explore quantum algorithms and their complexity.
- Experiment with real quantum hardware through IBM Quantum.
- Build a FastAPI backend for executing quantum simulations.
- Create an interactive quantum computing playground.

## Useful Resources

- [IBM Quantum Learning](https://quantum.cloud.ibm.com/learning)
- [Qiskit Documentation](https://quantum.cloud.ibm.com/docs)
- [Qiskit Aer Documentation](https://qiskit.github.io/qiskit-aer/)
- [Python Documentation](https://docs.python.org/3/)
- [uv Documentation](https://docs.astral.sh/uv/)

## Contributing

Contributions, suggestions, and improvements are welcome.

Feel free to open an issue or submit a pull request.

## Author

**Jabo Serge Byusa**

GitHub: [@Byusa](https://github.com/Byusa)

---

**Learning quantum computing, one qubit at a time.**