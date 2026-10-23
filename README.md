# FlyRank ML Internship — Ahmed Mossad's work repo

**Applied Search Intelligence: Google Search Ranking & Discoverability**

This is my workspace for the [FlyRank ML Internship](https://internship.flyrank.ai), built from the
public [starter repo](https://github.com/flyrank-bih/flyrank-ml-internship-starter) (*Use this
template*). Everything I do lives here — weekly notebooks, experiments, and the capstone — and this
URL is what I submit on every assignment card.

All work runs on a small **anonymized** slice of real FlyRank search data. No credentials, no
private client data.

---

## Progress

| Week | Card | Deliverable | Status |
|---|---|---|---|
| 1 | **ML-01** — Run the starter | `notebooks/01`, `02` executed + "your turn" cells | ✅ **Done** |
| 1 | ML-02 — Research question | `work/notebooks/w01_research_question.ipynb` | ⏳ Next |
| 2 | ML-03 — ML task framing | `work/notebooks/w02_ml_task_framing.ipynb` | — |
| 3 | ML-04 / ML-05 — Data contract, leakage check | `work/notebooks/w03_*.ipynb` | — |
| 4 | ML-06 / ML-07 — Signal audit, baseline | `work/notebooks/w04_*.ipynb` | — |
| 5 | ML-08 — Model | `work/notebooks/w05_model.ipynb` | — |
| 6 | ML-09 — Validation audit | `work/notebooks/w06_validation_audit.ipynb` | — |
| 7 | ML-10 — Action playbook | `work/notebooks/w07_action_playbook.ipynb` | — |
| 8 | ML-11 — Capstone paper | `work/notebooks/capstone.ipynb` + `submission/paper_url.txt` | — |

### What the starter run showed (ML-01, computed live)

The reference pipeline ranks pages for "refresh review" two ways — a hand-written rule and a
learned model — scored on **Precision@50** (of the top 50 pages flagged, how many are actually
declining):

```text
Hand-written rule   Precision@50: 0.240   (~12 of the top 50 right)
Random forest       Precision@50: 0.680   (~34 of the top 50 right)   ~2.8x the rule
```

Two things I found in the "your turn" cells:

1. **Belief test — "old pages are the ones declining": OPPOSITE.** The share of pages trending
   down falls with age: highest in the mid-age tiers (31–180 days) and smallest in the 365+ tier
   (every bucket n ≥ 492). Survivors that reach a year old tend to be the stable ones.
   *Observed / directional — not causal.*
2. **Client-holdout experiment (the caveat cell):** I re-ran the hand-rule-vs-tree comparison with
   a split by `client_id` — the tree trained on half the clients, scored on clients it never saw.
   The gap held out-of-sample (test Precision@20: 0.750 vs 0.500; @50: 0.660 vs 0.620), though a
   depth-2 tree produces tied score blocks, so I state what this run shows rather than claiming
   "the model is always better."

---

## First-win notebooks (open in Colab)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/notebooks/01_first_look_and_discovery.ipynb?flush_cache=true) **Week 1 — Run it, then discover a real truth yourself**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/notebooks/02_your_first_readable_model.ipynb?flush_cache=true) **Week 2 — The model is just a rule you can read**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/notebooks/03_working_with_the_full_release.ipynb?flush_cache=true) **Weeks 3+ — the ~79M-row warehouse via DuckDB** (gated: [`FlyRank/internship-warehouse`](https://huggingface.co/datasets/FlyRank/internship-warehouse), instant approval)

## Assignment notebooks

| Week | Notebook | Open |
|---|---|---|
| 1 | `w01_research_question` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w01_research_question.ipynb?flush_cache=true) |
| 2 | `w02_ml_task_framing` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w02_ml_task_framing.ipynb?flush_cache=true) |
| 3 | `w03_data_contract` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w03_data_contract.ipynb?flush_cache=true) |
| 3 | `w03_feature_leakage_check` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w03_feature_leakage_check.ipynb?flush_cache=true) |
| 4 | `w04_signal_audit` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w04_signal_audit.ipynb?flush_cache=true) |
| 4 | `w04_baseline_score` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w04_baseline_score.ipynb?flush_cache=true) |
| 5 | `w05_model` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w05_model.ipynb?flush_cache=true) |
| 6 | `w06_validation_audit` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w06_validation_audit.ipynb?flush_cache=true) |
| 7 | `w07_action_playbook` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/w07_action_playbook.ipynb?flush_cache=true) |
| 8 | `capstone` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmedm0ssad/Machine-Learning-Intern/blob/main/work/notebooks/capstone.ipynb?flush_cache=true) |

---

## Run it locally

```bash
git clone https://github.com/ahmedm0ssad/Machine-Learning-Intern.git
cd Machine-Learning-Intern
pip install -r requirements.txt
python scripts/run_all.py
```

For running notebooks top-to-bottom locally (Windows note: `scripts/run_all.py` prints a Unicode
arrow — set UTF-8 mode first so the console can encode it):

```bash
pip install nbconvert ipykernel

# PowerShell / Windows
$env:PYTHONUTF8 = '1'
jupyter nbconvert --to notebook --execute --inplace notebooks/01_first_look_and_discovery.ipynb
jupyter nbconvert --to notebook --execute --inplace notebooks/02_your_first_readable_model.ipynb
```

On Colab none of this is needed — open a badge and *Runtime → Run all*.

---

## Repo map

| Path | What it is |
|---|---|
| `notebooks/` | Week 1–2 first-win notebooks (Colab-ready). |
| `scripts/01–05` + `run_all.py` | The reference pipeline: prepare → baseline → train → evaluate → PDF. Read and copy from it; never edit it. |
| `data/raw/content_refresh_anonymized.csv` | Anonymized starter dataset (~30k pages × 44 cols). Column reference: [`docs/data-dictionary.md`](docs/data-dictionary.md). |
| `outputs/` | Pipeline products (`model_report.md`, ranked queue, charts) — the target shape for my own reports. |
| `work/` | **My space.** Every assignment and the capstone live here. |
| `docs/` | Setup/guides, the lane guide, and the core data docs. |

Data gotchas I keep in mind (full list in the
[dataset guide](docs/ml-intern-dataset-and-lane-guide.md)): rate columns are ×100 percentages
(`ctr = 0.76` means 0.76%), `avg_position = 0` means *no data*, `scroll_rate`/`ai_traffic_pct` can
exceed 100 legitimately, and `trend_pct`/`trend_direction` are the label side — never features.

---

## Data safety

- Only the small anonymized CSV ships here — no client names, domains, URLs, titles, or keywords.
- **Never** add raw private client data to this repo. Don't paste client data into third-party AI
  tools.
- Every result framed as **observed / measured / directional / decision-support** — never
  "I predicted Google's algorithm."
- `.gitignore` blocks datasets by default; CI fails any commit that contains one.

---

## How submission works

One repo, the whole internship: do the work → commit it here → submit **this repo URL** on the
card. At the end, the capstone paper deploys and its URL goes in `submission/paper_url.txt` —
same repo submitted at every step.

---

*Starter repo by FlyRank (track leads: Mirza Ašćerić — ML, Hole — data engineering). Code under
MIT (see `LICENSE`); data under `DATA_USE.md`. Intern work above is mine — usual disclaimers:
cohorts of one, numbers computed live, opinions observed not proved.*
