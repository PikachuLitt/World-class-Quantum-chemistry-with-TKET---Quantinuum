# World-class-Quantum-chemistry-with-TKET---Quantinuum
You will first get a feel for how TKET optimizes and compiles sample circuits for a given backend. You can create a sample circuit of your choice, or you can use some circuits, given as QASM code, [here](https://github.com/spendierk/ethz-hackathon22/tree/main/benchmarking/circuits). Then optimize and run this sample circuit on different backends. Here is a list of questions to get you started:

1. Which gate-based quantum computers are accessible to you to implement your circuit?
1. Which circuit parameters should be minimized for the most efficient circuit implementation for a given backend?
1. What are the main features of TKET, and how can you apply them here?
1. Which backend is the best for a given sample circuit and why?

## Step 1: Beginner Practice

1. Hardware backends available to our team include: IBMQ, IonQ and Quantinuum.
2. The goal of compiling is to reduce the effective circuit depth $D$, number of CNOT gates $N_{\text{CNOT}}$, and number of single-qubit parametrized gates $N_{\theta}$. In this case, we will compare the performance of qiskit and pytket compiler under these 3 metrics.
3. Main features of TKET include:
    1. Building up quantum circuits. Here, we choose to load a circuit for preparing H2 ground state from a QASM file.
    2. Complication to a given backend with different optimizaion levels. Here, we try to compile and optmize the circuit in a variety of backends for comparison.
    3. Simulation or execution on real devices. Here, we use this feature to obtain fidelities for compiled circuits.
4. `Quantinuum H1-1 Emulator` with `TKET compiler` gives the best result. It contains a realtive low cost on CNOT gates $N_{\text{CNOT}}=22$ and highest Fidelity $F = 92.2\%$.

<details>
<summary>
Details for Quantinuum H1-1 Emulator.
</summary>

| Backends    | Compiler    |Test file   | Qubits      |Optimization level      | $D$     | $N_{\text{CNOT}}$   |$N_{\theta}$   | Fidelity $F$ |
| ----------- | :----------: |:-----------:| :-----------: |:-----------: |:-----------: | :-----------: | :-----------: | :-----------: |
| quantinuum.hqs-lt-s1-sim  | TKET  | H2-JW   | 12          | 2          | 56      | 22       | 60        | 92.2% (emulator)     |

</details>

Also, we compared the performance of Qiskit and PyTket compiler under these 3 metrics. We found PyTket compiler outperforms Qiskit in most of our cases.

---

# Team Members:
Team Name：QBubbles

| Name            | Discord         | Github       |  Email
| --------------- | --------------: |--------------:|--------------:|
| Zhixin Song | Jack_Song#7300  | Zhixin Song  |   songzx0524@gmail.com |
| Tingting Li | PikachuLitt#2392 | PikachuLitt  | pikachulitt007@gmail.com |
| Yuxuan Yan  | Yuxuan Yan#0166 |  Rabqubit  |  yyan.tsinghua@gmail.com    |


# Dependencies
Required Packages:\
Python >= 3.6

qiskit.__qiskit_version__=={'qiskit-terra': '0.21.1', 'qiskit-aer': '0.10.4', 'qiskit-ignis': '0.6.0', 'qiskit-ibmq-provider': '0.19.2', 'qiskit': '0.37.1', 'qiskit-nature': None, 'qiskit-finance': None, 'qiskit-optimization': None, 'qiskit-machine-learning': None}

pytket==1.5.0


# Files
TODO: 文件描述
