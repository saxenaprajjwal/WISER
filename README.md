# Project Name
Quantum Walks Monte Carlo

# Team Name
Qrozzal

# Team Members
1. Prajjwal Saxena — [gst-gaWUFxD74GvtxIk]


--------------

## 500-Word Project Summary

This project explores the simulation of **Quantum Galton Boards (QGBs)** and their role in demonstrating quantum walks and Monte Carlo methods. The work follows the WISER 2025 project description *"Quantum Walks and Monte Carlo"* and references the methodology described in Carney and Varcoe’s 2022 paper on the quantum Galton board [arXiv:2202.01735].

The QGB is a quantum analogue of the classical Galton board, where a “ball” moves through a network of pegs according to quantum superposition and interference rules rather than classical probability. The board’s vertical progression is modeled as discrete “layers,” and at each layer a quantum coin toss (implemented using a Hadamard gate) determines whether the ball moves left or right. Controlled-SWAP gates implement the conditional position shifts, and inverted CNOT gates are used to ensure the particle is always displaced rather than remaining stationary in the center.

**Main Tasks:**
1. **Conceptual Study** — Reviewed [arXiv:2202.01735] and related literature to understand the mathematical model of quantum walks in a Galton board setting. Prepared a 2-page structured summary covering physics, mathematics, and relevant circuit implementations.
2. **Circuit Generalization** — Started from working 1- and 2-layer QGB implementations in Qiskit (v1.4.2) and developed a general algorithm to generate a QGB circuit with an arbitrary number of layers. Verified that the distribution approaches a Gaussian-like profile for many layers.
3. **Target Distribution Modification** — Modified the QGB implementation to achieve different output distributions. As a demonstration, implemented a noiseless all-to-all sampler to produce an exponential distribution, and separately simulated a Hadamard quantum walk.

**Key Technical Details:**
- **Platform:** Qiskit 1.4.2 with AerSimulator backend.
- **Registers:** A single coin qubit and multiple position qubits; the number of position qubits is \(2n+1\) for \(n\) layers.
- **Gates:** Hadamard (coin flip), Controlled-SWAP (conditional movement), inverted CNOT (conditional control on \(|0\rangle\)).
- **Measurement:** Position qubits are measured to produce final probability distributions.

**Outcomes:**
- A parameterized QGB circuit generator that can be used to explore different dynamics.
- Verification of the interference patterns characteristic of quantum walks.
- Demonstration of tailoring the QGB to target non-Gaussian distributions.

**Applications:**
Quantum walks have direct applications in quantum algorithms for search, sampling, and modeling physical processes. The QGB serves as a visually intuitive platform to study interference-driven probability distributions and to compare classical vs quantum stochastic processes.

## References
- [WISER Quantum Walks Monte Carlo](https://www.thewiser.org/quantum-walks-monte-carlo)

	-W. Feller, An Introduction to Probability Theory and Its Applications, Vol. 1, Wiley, 1968.
    -J. Kempe, “Quantum random walks: An introductory overview,” Contemporary Physics, 44(4), 307–327 (2003).
    -J. J. Carney and B. Varcoe, “The quantum Galton board: a new algorithm,” arXiv:2202.01735 (2022)
    -A. Schreiber et al., “Photons walking the line: A quantum walk with adjustable coin operations,” Phys. Rev. Lett., 104(5), 050502 (2010).
    -Y. Qin et al., “Integrated photonic Galton board,” Optica, 11(3), 311–319 (2024).
