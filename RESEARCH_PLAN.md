# Research Plan: IT Job Market Downfall in USA

## Current State

| Component | Status |
|---|---|
| Raw data (5 sources) | Complete |
| Integration pipelines | Complete |
| Main analysis notebook | **Complete (Phase 2 EDA done)** |
| Modeling / predictions | **Complete (Phase 3 done)** |

---

## Phase 1 — Environment Setup

- [x] Create the Python 3.11 venv: `py -3.11 -m venv .venv`
- [x] Install required packages: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `jupyter`, `ipykernel`
- [x] Register the Jupyter kernel (optionally rename from `us-it-role-downfall` to a project-specific name)

---

## Phase 2 — EDA in `Models/Notebook.ipynb`

### Step 1 — Load datasets

| Purpose | File |
|---|---|
| Primary EDA & merging | `it_occupations_master_long.csv` |
| Which roles were hit most | `it_occupations_wide_total.csv` |
| Age group analysis | `it_occupations_wide_all_metrics.csv` |
| Layoff events | `Layoffs_USA.csv` |
| Hiring demand proxy | `Job postings data collection.csv` |
| Labor turnover indicators | `combined_job_data.csv` |
| Long-term wage/employment trend | `IT_yearly_summary.csv` |

### Step 2 — Role-level impact analysis

- [x] Use `it_occupations_wide_total.csv` to rank the 16 tracked roles by employment change 2020–2025
- [x] Identify biggest losers (web developers, network admins, programmers) and gainers (security analysts)

### Step 3 — Time-series trends

- [x] Plot IT employment over time (2001–2024) using `IT_yearly_summary.csv`
- [x] Overlay layoff events from `Layoffs_USA.csv` on the timeline
- [x] Plot job posting demand indices (Indeed FRED data) over time

### Step 4 — Labor market turnover context

- [x] Use `combined_job_data.csv` (JOLTS) to show how hires, openings, and layoff rates evolved (Dec 2000–2025)
- [x] Correlate JOLTS layoff spikes with layoffs.fyi events

### Step 5 — Age-based analysis

- [x] Use `it_occupations_wide_all_metrics.csv` to compare age group distributions per role
- [x] Identify if certain age groups were disproportionately affected by role declines

---

## Phase 3 — Predictive Modeling

- [x] Build a trend/regression model on role-level employment data to project which roles will decline further
- [x] Candidate approaches: linear regression per role, time-series extrapolation, or a simple forecasting model on `IT_yearly_summary.csv`

---

## Phase 4 — Finalize

- [ ] Add summary conclusions to the notebook (written markdown cells)
- [ ] Update `README.md` to match `README copy.md`

---

## Key Reference Files

- `Project References/Dataset Links.txt` — source URLs and notes on which processed file to use for each task
- `Project References/1)install environment.txt` — environment setup commands
- `README copy.md` — full project documentation
