# IT Job Market Downfall in USA

This project analyzes the decline in the U.S. IT job market by combining multiple labor-market signals, including layoffs, job postings, occupational employment, labor turnover, and employment by occupation and age.

Then we are using EDA and visualization to identify which IT roles were most affected, how the trends evolved over time, and how different age groups were impacted. The goal is to provide insights into the dynamics of the IT job market and the factors contributing to its decline while predinting which role will  be affected most in next few years.

## Main Project Structure

```text
EDA-of-IT-job-market-downfall-in-USA/
|-- Data/
|   |-- Integrated/
|   |   |-- Employed persons by detailed occupation and age BLS/
|   |   |-- Job postings - hiring demand dataset/
|   |   |-- Layoffs/
|   |   |-- Occupational Employment and Wage Statistics/
|   |   \-- Official labor turnover dataset - BLS JOLTS/
|   \-- raw/
|       |-- IT-Operations-and-Helpdesk-Job-Postings-on-Indeed.csv
|       |-- Job-Postings-on-Indeed.csv
|       |-- layoffs.csv
|       |-- Software-Development-Job-Postings-on-Indeed.csv
|       |-- Employed persons by detailed occupation and age BLS/
|       \-- Occupational Employment and Wage Statistics/
|-- Models/
|   \-- Notebook.ipynb
|-- Project References/
|   |-- install environment.txt
|   \-- Dataset Links.txt
\-- README.md
```

## Folder Purpose

- `Data/raw/`: Original source files collected from external datasets.
- `Data/Integrated/`: Cleaned, merged, or transformed datasets used for analysis.
- `Models/Notebook.ipynb`: Main notebook for preprocessing, EDA, and analysis.
- `Project References/1)install environment.txt`: Existing local environment setup commands.
- `Project References/Dataset Links.txt`: Source references and notes about which processed files to use.

## Main Datasets

- `Layoffs`: Layoff trends sourced from layoffs.fyi.
- `Job postings - hiring demand dataset`: Hiring demand proxies from FRED.
- `Official labor turnover dataset - BLS JOLTS`: Labor turnover indicators from BLS.
- `Occupational Employment and Wage Statistics`: Yearly IT employment and wage data.
- `Employed persons by detailed occupation and age BLS`: Occupation-level employment data with role and age views.

## Which Files To Use

Based on the notes in `Project References/Dataset Links.txt`:

- Use `it_occupations_master_long.csv` for preprocessing, EDA, charts, and merging with other datasets.
- Use `it_occupations_wide_total.csv` to identify which roles were most affected from 2020 to 2025.
- Use `it_occupations_wide_all_metrics.csv` for age-based analysis.
- Use `it_occupations_merged.xlsx` for manual viewing and sharing.

## Main Instructions

### 1. Create a Python environment

The existing setup note uses Python 3.11:

```powershell
py -3.11 -m venv .venv
```

### 2. Install the required packages

```powershell
& ".\.venv\Scripts\python.exe" -m pip install --upgrade pip setuptools wheel
& ".\.venv\Scripts\python.exe" -m pip install ipykernel jupyter pandas numpy scikit-learn matplotlib seaborn
```

### 3. Register the notebook kernel

```powershell
& ".\.venv\Scripts\python.exe" -m ipykernel install --user --name telecom-churn --display-name "Telecom Churn (.venv)"
```

Note: the kernel name in the existing setup file is `telecom-churn`, which appears to be reused from another project. You can keep it as-is or register a clearer project-specific name.

### 4. Open the main notebook

Start with `Models/Notebook.ipynb`, then load the processed datasets from `Data/Integrated/` depending on the analysis you want to run.

### 5. Rebuild or inspect source data when needed

Each integrated dataset folder contains a collection notebook and processed outputs. Use those notebooks if you need to refresh the raw data pipeline or inspect how a dataset was prepared.

## Dataset Sources

- Job postings: FRED series listed in `Project References/Dataset Links.txt`
- JOLTS: BLS employment data portal
- Employed persons by occupation and age: BLS CPS tables
- Layoffs: layoffs.fyi

## Recommended Workflow

1. Set up the environment and Jupyter kernel.
2. Review the processed files in `Data/Integrated/`.
3. Use `Models/Notebook.ipynb` as the main analysis entry point.
4. Go back to the dataset-specific notebooks only when you need to regenerate or validate intermediate data.