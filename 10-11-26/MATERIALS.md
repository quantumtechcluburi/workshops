# 📚 Workshop Materials: Qiskit Quick Reference

Everything from today's notebooks on one page. Keep it open while you code, and come back to it whenever you build your own circuits.

## Build a circuit
```python
from qiskit import QuantumCircuit
qc = QuantumCircuit(2)        # 2 qubits, all start in |0⟩
qc.h(0)                       # gate on qubit 0
qc.cx(0, 1)                   # control 0, target 1
qc.measure_all()              # measure everything
qc.draw("mpl")                # draw it
```

## Gates
| Gate | Code | Bloch sphere / effect |
|---|---|---|
| X (NOT) | `qc.x(q)` | 180° around x · flips 0 ↔ 1 |
| Y | `qc.y(q)` | 180° around y |
| Z | `qc.z(q)` | 180° around z · flips the phase (\|+⟩ ↔ \|−⟩) |
| H (Hadamard) | `qc.h(q)` | \|0⟩ → \|+⟩ (equator) · makes superpositions |
| S / T | `qc.s(q)` / `qc.t(q)` | 90° / 45° around z |
| RX / RY / RZ | `qc.ry(theta, q)` | rotate by any angle (radians) |
| Phase | `qc.p(phi, q)` | adds phase φ to \|1⟩ |
| CNOT | `qc.cx(c, t)` | flip target if control is 1 |
| CZ | `qc.cz(a, b)` | phase flip if both are 1 |
| SWAP | `qc.swap(a, b)` | exchange two qubits |
| Toffoli | `qc.ccx(c1, c2, t)` | flip target if both controls are 1 |
| Fredkin | `qc.cswap(c, a, b)` | swap a, b if control is 1 |

## Look at the state (simulator only, no measurement)
```python
from qiskit.quantum_info import Statevector
from qiskit.visualization import plot_bloch_multivector, plot_state_qsphere
sv = Statevector(qc_without_measurements)
sv.draw("latex")                 # formula
sv.probabilities_dict()          # {'00': 0.5, '11': 0.5}
plot_bloch_multivector(sv)       # one sphere per qubit
plot_state_qsphere(sv)           # whole-state view
```

## Run on a simulator
```python
from qiskit_aer.primitives import SamplerV2 as Sampler
from qiskit.visualization import plot_histogram
result = Sampler().run([qc], shots=1000).result()
counts = result[0].data.meas.get_counts()     # {'00': 503, '11': 497}
plot_histogram(counts)
```

## Run on a real IBM quantum computer
```python
from qiskit_ibm_runtime import QiskitRuntimeService, SamplerV2 as Sampler
from qiskit.transpiler import generate_preset_pass_manager

service = QiskitRuntimeService()                         # after save_account(...)
backend = service.least_busy(operational=True, simulator=False)
isa_qc  = generate_preset_pass_manager(backend=backend, optimization_level=2).run(qc)
job     = Sampler(mode=backend).run([isa_qc], shots=1000)
print(job.job_id())                                      # keep this!
counts  = job.result()[0].data.meas.get_counts()
```
No account? Use `from qiskit_ibm_runtime.fake_provider import FakeKingston; backend = FakeKingston()`, a noisy copy of a real chip that runs locally.

## ⚠️ Gotchas
- **Bit order:** Qiskit writes results as `q(n-1) … q1 q0`, so **qubit 0 is the rightmost character**. `qc.x(0)` on 3 qubits gives `'001'`.
- Real hardware needs **transpiling** first (the `isa_qc` step), or you'll get an error.
- Angles are in **radians**: π = `np.pi` = 180°.
- Free Open Plan = **10 min / 28 days** of QPU time. Never put real-hardware calls in a big loop; send many circuits in **one** job instead: `sampler.run([c1, c2, c3])`.

## Links
- Platform & account: <https://quantum.cloud.ibm.com>
- Composer (drag & drop): <https://quantum.cloud.ibm.com/composer>
- Free courses: <https://quantum.cloud.ibm.com/learning>
- Docs: <https://quantum.cloud.ibm.com/docs>
