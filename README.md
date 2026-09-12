# Oil Production Exploratory Data Analysis

This repository contains an exploratory data analysis of monthly oil and condensate production from major Nigerian terminals/streams between 2024 and mid-2026. The project uses public terminal-level production data from the Nigerian Upstream Petroleum Regulatory Commission (NUPRC) to explore production volatility, directional trends, and Pareto concentration across terminals.

## Project overview

The analysis was designed to answer three core questions:

1. How volatile is output at each terminal from month to month?
2. Are terminal outputs trending upward, downward, or remaining stable over time?
3. Do the top 20% of terminals account for roughly 80% of total production, in line with the Pareto principle?

Because field-level production data is not publicly available without a paid license, the project works with the terminal/stream-level data that has been made available publicly by NUPRC.

## Why this project matters

Oil and gas production analytics are critical for:

- understanding operational stability across terminal systems,
- spotting structural changes in output over time,
- identifying high-concentration producers,
- supporting strategic review and benchmarking.

This project provides a practical, data-first view of Nigerian terminal output patterns without requiring proprietary field-level reporting.

## Repository structure

```text
Oil-Production---Exploratory-Data-Analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/
│   │   ├── NUPRC_2024_production_raw.csv
│   │   ├── NUPRC_2025_production_raw.csv
│   │   └── NUPRC_2026_production_raw.csv
│   └── cleaned/
│       ├── NUPRC_2024_production_cleaned.csv
│       ├── NUPRC_2025_production_cleaned.csv
│       └── NUPRC_2026_production_cleaned.csv
├── notebooks/
│   └── analysis.ipynb
└── .venv/
```

## Data description

The source data contains monthly production figures for major oil terminals and streams in Nigeria. Each file includes:

- Terminal/Stream name
- Liquid Type (for example, Crude Oil, Condensate, Blend Total)
- Monthly production values from January to December

### Example schema

```text
Terminal/Stream,Liquid Type,January,February,...,December
BONNY,Crude Oil,6351778.0,4604102.0,...
```

### Data coverage

- 2024 production dataset
- 2025 production dataset
- 2026 production dataset (partial-year, January to June in the current analysis timeline)

### Data preparation

The workflow includes comparing terminal names across years and addressing naming inconsistencies such as:

- OTAKPIPO (Ex Ima Terminal) vs OTAKPIPO
- OYO vs OYO / OBODO

These variations are normalized during cleaning so the analysis is consistent across years.

## Notebook workflow

The main analytical notebook is located at `notebooks/analysis.ipynb`.

It is organized around the following steps:

1. Load raw CSV files for 2024-2026
2. Inspect schema and data types
3. Standardize terminal naming
4. Clean and normalize the dataset
5. Compare monthly terminal output across years
6. Evaluate trend and volatility across terminals
7. Test whether the top 20% of terminals account for 80% of output
8. Visualize findings with Matplotlib and Seaborn

## Key analytical questions

### 1. Volatility analysis

Monthly output variation is examined to understand how much each terminal fluctuates from month to month. This is important for identifying operational instability, seasonal effects, and production shocks.

### 2. Trend analysis

The project looks for the direction of each terminal's production trend over time. This helps distinguish between:

- consistently declining terminals,
- steadily improving operators,
- stable outputs with limited month-to-month movement.

### 3. Pareto check

The analysis tests whether a relatively small number of terminals dominate total output, which is a common characteristic in resource extraction systems and a useful lens for operational concentration.

## Environment and dependencies

This project uses Python and Jupyter. The full dependency list is in `requirements.txt`.

### Core packages

- pandas
- numpy
- matplotlib
- seaborn
- jupyter
- notebook

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/loteehenry/Oil-Production---Exploratory-Data-Analysis.git
cd Oil-Production---Exploratory-Data-Analysis
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

On Windows:

```powershell
.venv\Scripts\Activate.ps1
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter

```bash
jupyter notebook
```

Or use JupyterLab:

```bash
jupyter lab
```

Then open `notebooks/analysis.ipynb`.

## Running the analysis

From the project root:

```bash
jupyter notebook notebooks/analysis.ipynb
```

The notebook loads the raw CSV files from `data/raw` and performs exploratory analysis and visualization.

## Expected outputs

The notebook is designed to generate:

- terminal-level volatility comparisons,
- trend observations by terminal,
- monthly production visualizations,
- Pareto concentration summaries,
- charts highlighting year-over-year production patterns.

## Limitations and notes

- The dataset is terminal/stream-level rather than field-level.
- The 2026 data is partial and may not represent a full calendar year.
- Some naming changes between years require manual standardization before analysis.
- This is an exploratory analysis, not a production-grade operational forecasting system.

## License

This project is intended for data analysis and learning purposes. Please refer to the repository's licensing configuration, if any, before reusing the data or notebooks in a commercial or public setting.

## Contributing

Contributions are welcome if they improve the analysis, add more rigorous cleaning logic, expand the visualizations, or make the notebook easier to reproduce.

## Contact

For questions or collaboration opportunities, please open an issue or contact the repository maintainer through the GitHub project page.

## Project Status: In Progress
Data loading, inspection, cleaning, and preparation have been completed. Exploratory analysis is currently underway.
