# 🚀 Setup & Sign-up: get running in 10 minutes

Today you need:

1. **A place to run the notebooks.** Use Google Colab (Option A). It works in your browser with nothing to install.
2. **A free IBM Quantum account, for notebook 04 only.** Notebooks 01 to 03 need no account.

---

## Part 1 · Run the notebooks

### Option A: Google Colab (recommended) ⭐
You need a Google account.

1. Open the [README](README.md#-notebooks) and click **▶️ Open in Colab** next to notebook 01.
   Or open this link: <https://colab.research.google.com/github/quantumtechcluburi/workshops/blob/main/qiskit-from-zero-11-10-26/notebooks/01_meet_the_qubit.ipynb>
2. Sign in with Google if Colab asks.
3. Click the first code cell and press **Shift + Enter**.
4. If Colab shows a warning, click **Run anyway**.
5. Wait 30 to 60 seconds. You should see: `✅ Qiskit 2.x.x | Aer 0.x.x | ready to go!`
6. Press **Shift + Enter** to run each of the following cells in order.

For the next notebook, go back to the README and click its **▶️ Open in Colab** link.

> 💾 **To keep your changes**, click **File → Save a copy in Drive**. Otherwise Colab doesn't save them.

### Option B: On your own laptop
You need **Python 3.10 or newer**. Check by running `python3 --version` in a terminal.

**1. Download the materials**
- Download <https://github.com/quantumtechcluburi/workshops/archive/refs/heads/main.zip>
- Unzip it.

**2. Open a terminal in the workshop folder**

macOS / Linux:
```bash
cd ~/Downloads/workshops-main/qiskit-from-zero-11-10-26
```
Windows (PowerShell):
```powershell
cd $HOME\Downloads\workshops-main\qiskit-from-zero-11-10-26
```
(Change the path if you unzipped it somewhere else.)

**3. Create and turn on a virtual environment**

macOS / Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
```
Windows (PowerShell):
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**4. Install the packages**
```bash
pip install -r requirements.txt
```

**5. Start Jupyter**
```bash
jupyter notebook
```
Your browser opens. Click `notebooks`, then `01_meet_the_qubit.ipynb`.

**Next time**, repeat only steps 2, 3 and 5.

> Using **VS Code**? Install the *Python* and *Jupyter* extensions. Open a notebook and choose the `.venv` kernel in the top right.

### Option C: No code at all
Use **IBM Quantum Composer**: <https://quantum.cloud.ibm.com/composer>. You drag and drop gates in your browser. It needs the IBM account from Part 2.

---

## Part 2 · Free IBM Quantum account (for notebook 04)

The free **Open Plan** gives you **10 minutes of real quantum-computer time every 28 days**. A small circuit uses only a few seconds.

1. Go to <https://quantum.cloud.ibm.com/registration>.
2. Sign in with your **Google account** or an **IBMid**. To create an IBMid, follow the steps on screen and enter the code from the verification e-mail.
3. If the site asks you to create an **IBM Cloud account**, follow the steps on screen.
4. At the top of the page, set the **region** to **`us-east`**.
5. Click **Instances → Create instance**, choose **Open Plan (free)** and create it.
6. Go to the **Home** page and click **Create API key**.
7. **Copy the key and save it somewhere private**, like a password manager. You may not be able to see it again.

✅ Done! In notebook 04, set `USE_REAL_HARDWARE = True` and run the cells. The notebook asks for your key.

### 🔐 Keep your API key safe
Your API key works like a password. Anyone who has it can use your free minutes.
- **Never** paste it into a notebook you share, screenshot or upload.
- **On Colab:** click the 🔑 **Secrets** icon on the left → **Add new secret** → name it `IBM_QUANTUM_TOKEN` → paste your key → turn on **Notebook access**. Notebook 04 finds it automatically.
- **On your laptop:** save your key once in a terminal, not in a notebook. Then Qiskit remembers it. Do this after you finish Option B.
  1. Open a terminal in the workshop folder and turn on the virtual environment (Option B, steps 2 and 3).
  2. Type `python` and press **Enter**. You should see `>>>`.
  3. Paste these two lines. Replace `YOUR-KEY` with your real key and press **Enter**:
     ```python
     from qiskit_ibm_runtime import QiskitRuntimeService
     QiskitRuntimeService.save_account(token="YOUR-KEY", set_as_default=True, overwrite=True)
     ```
  4. Type `exit()` and press **Enter**.

  Notebook 04 now finds your key automatically. Only do this on your own computer.
- **If you shared it by mistake:** delete the key on the IBM Quantum Home page and create a new one.

---

## 🧯 Troubleshooting

| Problem | Fix |
|---|---|
| `ModuleNotFoundError: No module named 'qiskit'` | Run the first cell of the notebook. On your laptop: choose the `.venv` kernel. |
| Plots or circuit drawings don't appear | Run `pip install pylatexenc matplotlib`, then run the cell again. |
| Sliders don't show up (notebook 01) | Run `pip install ipywidgets`. The picture below the sliders shows the same thing. |
| Strange errors after editing cells | Click **Runtime → Restart** (Colab) or **Kernel → Restart** (Jupyter). Then run all cells from the top. |
| "No instances" or can't find my instance | Set the region to **us-east** at the top of the IBM Quantum page. |
| `401`, "unauthorized" or "invalid token" | Copy the API key again with no spaces at the start or end. Or create a new key. |
| My real-hardware job stays `QUEUED` | This is normal on busy days. Write down the job ID and check it later (see "Lost your notebook?" in notebook 04) or on the **Workloads** page. |
| Results look backwards (`01` instead of `10`) | This is expected. Qiskit puts **qubit 0 on the right**. |
