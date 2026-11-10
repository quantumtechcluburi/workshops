# 🎤 Facilitator Guide: "Qiskit from Zero" (10 Nov 2026)

**Format:** informal, hands-on · **Slot:** 45 min (5:00 to 5:45 PM) + 15 min overflow until 6:00 · **Audience:** total beginners

**Goal:** by the end, every member has (1) run quantum circuits on a simulator, (2) seen superposition, interference and entanglement with their own eyes, and (3) a free IBM Quantum account and the confidence to keep going alone.

**Structure:** notebooks 01 to 03 run entirely on a **simulator (no account needed)**. The IBM account only comes in at the end, for notebook 04 on a real quantum computer.

---

## ✅ Pre-flight checklist (do this BEFORE 5 PM)

- [ ] **Do the sign-up yourself** following `SETUP_AND_SIGNUP.md` Part 2 (or log in if you already have an account). Note anything that differs from the handout (screens change often) and whether it asks for a **credit card** during IBM Cloud registration. IBM's docs describe the Open Plan as free but don't say either way, so warn members if it does.
- [ ] Create an API key and run **notebook 04 with `USE_REAL_HARDWARE = True`** once. Check it connects and note how long the queue takes today.
- [ ] Open `notebooks/01_meet_the_qubit.ipynb` in **Google Colab** and run the first two cells. Confirm the install works there.
- [ ] **Publish the files** to the club's GitHub repo and put the link on slide 5 and in `SETUP_AND_SIGNUP.md`. Members then open notebooks straight from GitHub in Colab (*File → Open notebook → GitHub*), or with links like `https://colab.research.google.com/github/<org>/<repo>/blob/main/notebooks/01_meet_the_qubit.ipynb`
- [ ] For presenting: open each notebook and do **Kernel → Restart & Clear Output** so you can run it live. (The files ship *with* outputs, which is useful as a backup if Wi-Fi dies: just scroll.)
- [ ] Bump the notebook zoom (Cmd +) so the back row can read code.

---

## 🗺️ Run of show (45 min)

| Clock | Block | What you do |
|---|---|---|
| 5:00 | **Welcome & intro** (slides 1 to 4) | What is a quantum computer, what is Qiskit, today's plan. Keep it light. |
| 5:04 | **Get set up** (slide 5) | Everyone opens Colab + notebook 01. No account needed. **You:** submit the real-hardware job from notebook 04 now, so the result is back by the end even if the queue is long. |
| 5:08 | **Notebook 01 · Meet the Qubit** (10 min) | Bloch sphere, X / H / Z, sliders. |
| 5:18 | **Notebook 02 · Measure & Simulate** (10 min) | Coin flips, histogram, the "peek" experiment, interference fringes. |
| 5:28 | **Notebook 03 · Q is for Quantum** (8 min) | Balls and mist: CNOT, Hadamard, Bell, GHZ. |
| 5:36 | **Real hardware** (slide 6 + notebook 04, 7 min) | Show the sign-up QR, then your pre-submitted job: real vs. ideal. |
| 5:43 | **Wrap-up** (slides 7 and 8) | "Where to go next", home challenge. |
| 5:45 | **Overflow (optional, until 6:00)** | Members sign up and run notebook 04 themselves, GHZ noise-scaling cell, challenges, Q&A. |

### What to show vs. skip in each notebook
Everything you skip stays in the notebooks for members to read at home.

| Notebook | ✅ Show live | ⏭️ Skip if short on time |
|---|---|---|
| 01 | Trailer cell, first Bloch sphere, X, H (and H twice), Z, sliders | S/T gate tour, amplitudes section, multi-qubit spheres |
| 02 | 20 coin flips, 1000-shot histogram, peek experiment, interference fringes | Law of large numbers, loaded coin, Bloch steps, Estimator bonus, dice |
| 03 | CNOT truth table, H truth table + two H's, Bell state + histogram + "no arrows", GHZ step by step, 12-ball GHZ | NOT, SWAP from 3 CNOTs, C-SWAP |
| 04 | Memory plot (30 s), chip error plot, transpiled circuit, ideal vs. real histogram | Saving credentials, GHZ noise scaling (do it in the overflow) |

---

## 🗣️ Talking points & demo tips

### Intro (slides)
- A **bit** is a light switch. A **qubit** is an arrow on a sphere, and *measuring* it forces a yes/no answer.
- Quantum computers aren't "faster at everything". They're good at specific problems (simulating molecules and materials, some optimisation, factoring) by using **interference**: making wrong answers cancel and right answers add up.
- Qiskit = Python. If you can write `print("hello")` you can write a quantum program today.
- Today is all simulator until the very end, so nobody needs an account to get started.

### Notebook 01 · Meet the Qubit
- Run the **trailer** cell first for the "wow". Don't explain it yet; promise that they'll understand every line by the end.
- **Sliders**: ask someone to call out values. Point out that φ changes the sphere but **not** the bar chart, and set this up as "this invisible thing will be the star of notebook 02".
- **Z on |0⟩ does nothing**: let them be confused for a few seconds, then do Z on |+⟩.

### Notebook 02 · Measure & Simulate
- Run the 20-coin-flip cell **2 or 3 times**. Different every time, and that's the point.
- The **peek experiment** is the key "aha". Before running, **ask the room to vote**: "Does peeking change the final result?" Most will say no.
- **Fringes**: this is the double slit with a single qubit (H → P(φ) → H).
- Bit-order gotcha: say it out loud. Everybody trips on it later.

### Notebook 03 · Q is for Quantum
- Introduce the game: white ball = 0, black ball = 1, boxes = gates, mist = superposition.
- `truth_table(...)` shows every input and output for a box, like an unplugged lesson.
- The **GHZ cell** prints the mist step by step: H on the middle wire, then CNOT up, CNOT down.
- The **12-ball GHZ**: 4096 possible patterns, only 2 ever appear.

### Notebook 04 · Real hardware
- Show your pre-submitted job (job ID → `service.job("...")` if you restarted the kernel).
- Point at the **error-map / readout-error** plot: real qubits differ in quality, and the transpiler picks good ones for you.
- The tiny `01`/`10` bars are **noise**. That's why it's research, not solved.
- Remind them: **10 free minutes per 28 days**, and send many circuits in one job.

---

## ❓ Questions you'll probably get

| Question | Short answer |
|---|---|
| "Do I need an account to do this at home?" | Not for simulating: notebooks 01 to 03 work in Colab or on a laptop with no account. Only real hardware (notebook 04) needs the free IBM account. |
| "Is the qubit *really* 0 and 1 at the same time?" | It's in a state that is neither: a superposition with amplitudes for both. "Both at once" is a handy cartoon; the arrow/mist pictures are more honest. |
| "Can it break my passwords?" | Not today. Breaking RSA needs millions of error-corrected qubits. That's also why "post-quantum" cryptography is being rolled out now. |
| "Why are they kept so cold?" | IBM's superconducting qubits work at ~15 millikelvin (colder than outer space) so heat doesn't disturb them. |
| "How many qubits does IBM have?" | The Open Plan machines (e.g. `ibm_kingston`) have 156 qubits. Run `backend.num_qubits` in notebook 04 to see yours. |
| "Is the simulator a real quantum computer?" | No: it's ordinary maths on your laptop. It's perfect (no noise) but needs 2ⁿ memory, so it hits a wall around 30 to 50 qubits (plot in notebook 04). |
| "Why does `cx(0,1)` give `'10'` and not `'01'`?" | Bit order: qubit 0 is the rightmost character. |
| "What should I learn next?" | IBM Quantum Learning → *Basics of Quantum Information*; play with the Composer; do the challenges in each notebook. |

---

## 🧯 If things go wrong
- **Wi-Fi dies:** present from the saved outputs (every notebook ships executed). Local installs keep working, and notebook 04 falls back to the fake backend automatically.
- **Colab is slow installing:** pair people up on one screen.
- **Sign-up issues** (verification e-mail late, region confusion): don't block the session. They can use `USE_REAL_HARDWARE = False` and finish sign-up at home with the handout.
- **Real-hardware queue is long:** that's why you submitted at the start. Worst case, show the fake-backend result. It's a faithful noise copy of the real chip.
- **Running late:** cut notebook 03 down to Bell + GHZ, and do notebook 04 as a 3-minute demo of your own result.
