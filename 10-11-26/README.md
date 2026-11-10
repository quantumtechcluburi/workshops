# ⚛️ Quantum Technologies Club: Qiskit from Zero
*Workshop · 10 November 2026*

A friendly, hands-on introduction to quantum computing with **IBM Qiskit**. No physics or maths background needed. You'll build quantum circuits, *see* qubits on spheres, roll quantum dice, create entanglement, and finish by running a program on a **real IBM quantum computer**, for free.

## 🏁 Start here
1. **Get set up** → [`SETUP_AND_SIGNUP.md`](SETUP_AND_SIGNUP.md) (Google Colab = zero install). Notebooks 01 to 03 run on a simulator and need **no account**; the free IBM Quantum account is only for notebook 04.
2. **Open the notebooks in order** ↓
3. Keep the [`MATERIALS.md`](MATERIALS.md) quick reference open next to you

## 📓 Notebooks
| # | Notebook | You'll learn | ⏱️ in session |
|---|---|---|---|
| 01 | [Meet the Qubit](notebooks/01_meet_the_qubit.ipynb) | What Qiskit is · qubits as arrows on the Bloch sphere · gates X, H, Z, S, T, RY · interactive sliders | 10 min |
| 02 | [Measure & Simulate](notebooks/02_measure_and_simulate.ipynb) | Measurement & randomness · shots & histograms · the "peek" experiment · interference fringes (quantum double-slit) · quantum dice | 10 min |
| 03 | [Q is for Quantum](notebooks/03_q_is_for_quantum.ipynb) | Quantum computing as balls, boxes and mist: NOT, CNOT, SWAP, C-SWAP, Hadamard, Bell & GHZ entanglement | 8 min |
| 04 | [Run on a Real Quantum Computer](notebooks/04_run_on_a_real_quantum_computer.ipynb) | Connect your IBM account · pick a chip · transpile · run · compare ideal vs. noisy results | 7 min |

Every notebook:
- starts with a **setup cell** that installs Qiskit if needed (works on Colab out of the box),
- is saved **with outputs**, so you can read it like a book even without running it,
- ends with **🏆 challenges** (solutions hidden behind a click).

## 📁 What's in this folder
```
10-11-26/
├── README.md                 ← you are here
├── SETUP_AND_SIGNUP.md       ← install options + IBM Quantum account, step by step
├── MATERIALS.md              ← one-page Qiskit quick reference
├── FACILITATOR_GUIDE.md      ← for the presenter: timings, talking points, FAQ
├── requirements.txt          ← pip install -r requirements.txt
├── notebooks/                ← the four workshop notebooks
└── slides/                   ← intro slides (+ QR codes)
```

## 🔗 Useful links
- IBM Quantum Platform (account, API key, jobs): <https://quantum.cloud.ibm.com>
- IBM Quantum Composer (drag & drop circuits): <https://quantum.cloud.ibm.com/composer>
- IBM Quantum Learning (free courses): <https://quantum.cloud.ibm.com/learning>
- Qiskit documentation: <https://quantum.cloud.ibm.com/docs>
- Google Colab: <https://colab.research.google.com>

*Tested with Python 3.14 · Qiskit 2.6.2 · Qiskit Aer 0.18.2 · qiskit-ibm-runtime 0.52.0.*
