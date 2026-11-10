# ⚛️ Quantum Technologies Club: Qiskit from Zero
*Workshop · 10 November 2026*

A friendly, hands-on introduction to quantum computing with **IBM Qiskit**. No physics or maths background needed. You'll build quantum circuits, *see* qubits on spheres, roll quantum dice, create entanglement, and finish by running a program on a **real IBM quantum computer**, for free.

## 🏁 Start here
1. In the table below, click **▶️ Open in Colab** for notebook 01.
2. Sign in with your Google account if Colab asks.
3. Click the first code cell and press **Shift + Enter**. Wait about a minute while it installs Qiskit.
4. Keep pressing **Shift + Enter** to run each cell in order.
5. When you finish, open the next notebook the same way.

You don't need an account for notebooks 01 to 03. Notebook 04 needs a free IBM Quantum account: see [Part 2 of the setup guide](SETUP_AND_SIGNUP.md#part-2--free-ibm-quantum-account-for-notebook-04).

Keep the [quick reference (`MATERIALS.md`)](MATERIALS.md) open while you work.

## 📥 Download the materials
All the files are in the club's GitHub repo: <https://github.com/quantumtechcluburi/workshops>

To download them:
1. Click this link: <https://github.com/quantumtechcluburi/workshops/archive/refs/heads/main.zip>
2. Unzip the file.
3. Open the `qiskit-from-zero-11-10-26` folder.

To run the notebooks on your own laptop, follow [Option B of the setup guide](SETUP_AND_SIGNUP.md#option-b-on-your-own-laptop).

## 📓 Notebooks
| # | Notebook | Open it | You'll learn | ⏱️ in session |
|---|---|---|---|---|
| 01 | [Meet the Qubit](notebooks/01_meet_the_qubit.ipynb) | [▶️ Open in Colab](https://colab.research.google.com/github/quantumtechcluburi/workshops/blob/main/qiskit-from-zero-11-10-26/notebooks/01_meet_the_qubit.ipynb) | What Qiskit is · qubits as arrows on the Bloch sphere · gates X, H, Z, S, T, RY · interactive sliders | 10 min |
| 02 | [Measure & Simulate](notebooks/02_measure_and_simulate.ipynb) | [▶️ Open in Colab](https://colab.research.google.com/github/quantumtechcluburi/workshops/blob/main/qiskit-from-zero-11-10-26/notebooks/02_measure_and_simulate.ipynb) | Measurement & randomness · shots & histograms · the "peek" experiment · interference fringes (quantum double-slit) · quantum dice | 10 min |
| 03 | [Q is for Quantum](notebooks/03_q_is_for_quantum.ipynb) | [▶️ Open in Colab](https://colab.research.google.com/github/quantumtechcluburi/workshops/blob/main/qiskit-from-zero-11-10-26/notebooks/03_q_is_for_quantum.ipynb) | Quantum computing as balls, boxes and mist: NOT, CNOT, SWAP, C-SWAP, Hadamard, Bell & GHZ entanglement | 8 min |
| 04 | [Run on a Real Quantum Computer](notebooks/04_run_on_a_real_quantum_computer.ipynb) | [▶️ Open in Colab](https://colab.research.google.com/github/quantumtechcluburi/workshops/blob/main/qiskit-from-zero-11-10-26/notebooks/04_run_on_a_real_quantum_computer.ipynb) | Connect your IBM account · pick a chip · transpile · run · compare ideal vs. noisy results | 7 min |

Every notebook:
- starts with a **setup cell** that installs Qiskit if needed (works on Colab out of the box),
- is saved **with outputs**, so you can read it like a book even without running it,
- ends with **🏆 challenges** (solutions hidden behind a click).

## 📁 What's in this folder
```
qiskit-from-zero-11-10-26/
├── README.md                 ← you are here
├── SETUP_AND_SIGNUP.md       ← install options + IBM Quantum account, step by step
├── MATERIALS.md              ← one-page Qiskit quick reference
├── requirements.txt          ← pip install -r requirements.txt
├── notebooks/                ← the four workshop notebooks
└── slides/                   ← intro slides (+ QR codes)
```

## 🔗 Useful links
- Workshop materials (this repo): <https://github.com/quantumtechcluburi/workshops>
- IBM Quantum Platform (account, API key, jobs): <https://quantum.cloud.ibm.com>
- IBM Quantum Composer (drag & drop circuits): <https://quantum.cloud.ibm.com/composer>
- IBM Quantum Learning (free courses): <https://quantum.cloud.ibm.com/learning>
- Qiskit documentation: <https://quantum.cloud.ibm.com/docs>
- Google Colab: <https://colab.research.google.com>

*Tested with Python 3.14 · Qiskit 2.6.2 · Qiskit Aer 0.18.2 · qiskit-ibm-runtime 0.52.0.*
