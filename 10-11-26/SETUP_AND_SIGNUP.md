# 🚀 Setup & Sign-up: get running in 10 minutes

You need **two things** today:

1. **A place to run the notebooks** (pick ONE option below; Option A is the fastest)
2. **A free IBM Quantum account**, but only for notebook 04 (running on a *real* quantum computer). Notebooks 01 to 03 run on a simulator and need **no account at all**.

> 💡 **Tip:** Finished a notebook early? Start the IBM sign-up (Part 2) on your phone. Verification e-mails can take a few minutes to arrive.

---

## Part 1 · Run the notebooks

### Option A: Google Colab (recommended, zero install) ⭐
Works in any browser and only needs a Google account.

1. Go to **<https://colab.research.google.com>** and sign in with Google.
2. **File → Upload notebook** → choose `01_meet_the_qubit.ipynb` (get the files from the link the organiser shares).
3. Run the first code cell (**Shift + Enter**). It installs Qiskit automatically (30 to 60 seconds).
4. You should see: `✅ Qiskit 2.x.x | Aer 0.x.x | ready to go!`

Repeat step 2 for each notebook (each notebook installs what it needs).

### Option B: On your own laptop (best for later)
Requires **Python 3.10 or newer** (64-bit). In a terminal:

```bash
# 1. make a project folder and a virtual environment
mkdir qiskit-workshop && cd qiskit-workshop
python3 -m venv .venv                 # Windows: python -m venv .venv

# 2. activate it
source .venv/bin/activate             # Windows PowerShell: .venv\Scripts\Activate.ps1

# 3. install everything we use today
pip install -U pip
pip install qiskit qiskit-aer qiskit-ibm-runtime matplotlib pylatexenc ipywidgets jupyter

# 4. start Jupyter and open the notebooks
jupyter notebook
```

Or, from inside this workshop folder: `pip install -r requirements.txt`.

> Using **VS Code**? Install the *Python* and *Jupyter* extensions, open the `.ipynb` file and pick the `.venv` kernel (top right).

### Option C: No code at all
**IBM Quantum Composer**: <https://quantum.cloud.ibm.com/composer>. Drag-and-drop gates in the browser. Needs the IBM account from Part 2.

---

## Part 2 · Free IBM Quantum account (Open Plan, for notebook 04)

The **Open Plan** is free and gives you **up to 10 minutes of real quantum-computer time every 28 days** (rolling window). That's plenty for learning: a small circuit uses only a few seconds.

1. Go to **<https://quantum.cloud.ibm.com>** and click **Sign in / Create account**
   (direct link: <https://quantum.cloud.ibm.com/registration>).
2. Sign in with an **IBMid** or your **Google account**. If you don't have an IBMid, the site walks you through creating one (check your e-mail for a verification code).
3. If asked, create/link an **IBM Cloud account**. The platform guides you through it.
4. In the header, make sure the **region is `us-east`**: Open Plan instances only exist there.
5. Go to **Instances → Create instance** and choose the **Open Plan** (free).
6. Back on the **dashboard (Home)**, click **Create API key**. **Copy it and keep it somewhere safe** (password manager or a private note). You may not be able to see it again!

✅ Done! In notebook 04, set `USE_REAL_HARDWARE = True` and the notebook will ask for your key.

### 🔐 Keeping your API key safe
Your API key is like a password: anyone with it can use your free minutes.
- **Never** paste it into a notebook you'll share, screenshot, or upload to GitHub.
- On **Colab**: click the 🔑 **Secrets** icon in the left sidebar → add a secret named `IBM_QUANTUM_TOKEN` → paste the key → enable *Notebook access*. Notebook 04 picks it up automatically.
- On **your own laptop**, save it once and forget about it:
  ```python
  from qiskit_ibm_runtime import QiskitRuntimeService
  QiskitRuntimeService.save_account(token="YOUR-KEY", set_as_default=True, overwrite=True)
  # from now on: service = QiskitRuntimeService()
  ```
- Leaked it? Delete the key on the platform dashboard and create a new one.

---

## 🧯 Troubleshooting

| Problem | Fix |
|---|---|
| `ModuleNotFoundError: No module named 'qiskit'` | Run the first **SETUP** cell. Locally: make sure Jupyter uses your `.venv` kernel. |
| Plots/circuit drawings don't appear, or `pylatexenc` error | `pip install pylatexenc matplotlib` and re-run |
| Sliders don't show up (notebook 01) | `pip install ipywidgets`; the static picture below the sliders shows the same thing |
| Weird errors after editing cells | **Runtime/Kernel → Restart**, then run all cells from the top |
| Can't find my instance / "no instances" | Switch the region to **us-east** in the platform header |
| `401` / unauthorized / invalid token | Re-copy the API key (no spaces at the ends), or create a new one |
| My real-hardware job is stuck in `QUEUED` | That's normal on busy days. Note the job ID, close the notebook, and fetch it later (see notebook 04) or check the **Workloads** page |
| Results look "backwards" (e.g. `01` instead of `10`) | Qiskit puts **qubit 0 on the right** of the bitstring. That's expected! |
