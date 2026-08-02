# Exploratory Data Analysis (EDA)

Exploratory data analysis of the **Stack Overflow Developer Survey 2025** (`results.csv`) — examining what drives developer compensation worldwide.

## Overview

This project uses `main.ipynb` to analyze developer salary data. It cleans the raw survey responses, then explores:

- **Salary distribution** — median/mean annual compensation (USD)
- **Top paying programming languages** — median salary per language (min 500 respondents)
- **Remote vs on-site work** — how work setup affects compensation
- **Geographic disparities** — median salary across the most represented countries
- **Experience vs salary** — relationship between years coding and compensation

## Requirements

- Python 3.8+
- Jupyter Notebook
- [Pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)

## Installation

```bash
# Create a virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter
```

## Usage

1. Place the survey data (`results.csv`) in the project root.
2. Run the notebook:

```bash
jupyter notebook main.ipynb
```

## Data & Cleaning

The notebook loads only the columns needed to reduce memory usage:

`ResponseId, MainBranch, Employment, RemoteWork, EdLevel, YearsCode, DevType, Country, LanguageHaveWorkedWith, DatabaseHaveWorkedWith, PlatformHaveWorkedWith, ConvertedCompYearly`

Cleaning steps:

- Drop rows with missing salary
- Filter to realistic annual salaries (**$5,000 – $500,000**)
- Convert `YearsCode` text values (`Less than 1 year` → `0.5`, `More than 50 years` → `51`) to numeric
- Explode the semicolon-separated `LanguageHaveWorkedWith` column for per-language analysis

## Key Findings (as of this run)

- **Median global salary**: ~$XX,XXX USD — computed in the notebook
- Remote workers earn more on median than on-site workers
- US, Germany, and India dominate respondent counts
- Experience has a weak-to-moderate positive correlation with salary

> Update this section with the actual figures printed by the notebook.

## Project Structure

```
Exploratory Data Analysis/
├── main.ipynb    # EDA notebook
├── results.csv   # Survey dataset (2025 schema)
└── README.md
```
