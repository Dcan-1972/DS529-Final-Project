# DS529 Final Project

Final project repository for DS529. The project analyzes Spotify Top 200 chart data and builds time-series forecasting models for track streaming performance.

## Repository Contents

- `DS529-Final-Project Code.ipynb` - main analysis and forecasting notebook
- `DS529-Final-Project Report.docx` - final written report
- `DS529-Final-Project Forecasts.xlsx` - submitted forecast output
- `requirements.txt` - Python packages needed to run the notebook

## Project Overview

The notebook prepares Spotify chart data, creates song-level time series, visualizes streaming patterns, and compares several forecasting methods, including:

- Naive forecasting
- Average forecasting
- Moving-average forecasting
- Exponential smoothing
- ARIMA / Auto ARIMA
- SARIMAX

Model performance is evaluated with common forecast-error metrics such as MAE and MSE.

## Data Requirement

The notebook expects the raw input workbook below to be available in the repository root:

```text
Top 200 Spotify Chart Full List.xlsx
```

That raw workbook is not currently included in this repository. The included `DS529-Final-Project Forecasts.xlsx` file is the submitted forecast output, not the raw input dataset.

## Setup

Python 3.11 is recommended for this project because the time-series dependencies have more reliable prebuilt wheels on that version.

Create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start Jupyter:

```bash
jupyter notebook
```

Then open `DS529-Final-Project Code.ipynb`.

## Reproduce the Notebook

After adding the raw input workbook to the repository root, run:

```bash
jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=1200 --output executed_final_project.ipynb "DS529-Final-Project Code.ipynb"
```

This command executes the notebook and writes an executed copy named `executed_final_project.ipynb`.

## Verification Status

The notebook was tested with `jupyter nbconvert --execute`. The current clean-clone execution stops because `Top 200 Spotify Chart Full List.xlsx` is not present. The repository includes a GitHub Actions workflow that validates the repository structure, notebook JSON, and required project files.

## Notes

This repository is organized as a coursework final project. The report, notebook, and forecast spreadsheet are preserved as submitted project artifacts. The forecast workbook includes a `Notes` sheet documenting rows where MAE/MSE were unavailable.
