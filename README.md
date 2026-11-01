# AdSpend IQ

AdSpend IQ is a Streamlit dashboard for exploring digital advertising performance. It reports marketing KPIs across campaigns and platforms, includes audience and budget analysis, and provides downloadable reports. The included demo data is synthetic and should not be treated as real advertising results.

## Features

- Executive overview of spend, revenue, conversions, and return on ad spend (ROAS)
- Campaign analysis, including conversion funnels and campaign/platform comparisons
- Audience insights by city, device, age group, and gender
- Processing benchmarks for comparing dataset sizes
- Budget allocation recommendations and what-if scenarios
- CSV uploads, shared dashboard filters, and report exports

## Requirements

- Python 3.10 or later
- Dependencies listed in `requirements.txt`

## Run locally

Open a terminal in the project directory and run:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
streamlit run app.py
```

Streamlit will print a local URL (usually `http://localhost:8501`) to open in your browser.

## Use the dashboard

Choose **Synthetic Demo Data** to explore generated data, or choose **Upload CSV** to load your own dataset. The filters in the sidebar apply across the dashboard pages.

Uploaded CSV files must contain these columns:

| Column | Description |
| --- | --- |
| `date` | Date for the record |
| `campaign` | Campaign name |
| `platform` | Advertising platform |
| `impressions` | Number of impressions |
| `clicks` | Number of clicks |
| `spend` | Advertising spend |
| `conversions` | Number of conversions |
| `revenue` | Revenue attributed to the record |
| `age` | Audience age |
| `gender` | Audience gender |
| `city` | Audience city |
| `device` | Device category |

Values for the required columns must be present and valid. Numeric metrics must be non-negative; clicks cannot exceed impressions, and conversions cannot exceed clicks.

## Deploy on Streamlit Community Cloud

1. Push this project to a GitHub repository. Include `app.py`, the `components`, `config`, `pages`, and `utils` folders, and `requirements.txt`.
2. Sign in to [Streamlit Community Cloud](https://share.streamlit.io/) with GitHub and select **Create app**.
3. Choose the repository and branch, set the main file path to `app.py`, and deploy.

Community Cloud installs the packages from `requirements.txt`. Do not commit credentials or private data to the repository.

## Run tests

```powershell
python -m unittest discover -s tests
```

## Project structure

```text
app.py                  Streamlit application entry point
components/             Shared dashboard components and charts
config/                 Application settings
data/                   Data directory and sample-data location
pages/                  Dashboard pages
tests/                  Unit tests
utils/                  Data, metrics, optimization, and reporting helpers
requirements.txt        Python dependencies
```
