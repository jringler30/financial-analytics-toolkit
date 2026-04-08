# Financial Analytics Toolkit

A collection of Python-based financial modeling notebooks covering portfolio return estimation, discounted cash flow models, bond valuation, and time-value-of-money analytics.

These tools were developed to support investment modeling workflows and demonstrate applied financial computation using reproducible Jupyter notebooks.

---

## Included Models

- Portfolio Returns Engine (MVP prototype)
- Discounted Dividend Model (DDM)
- Coupon Bond Present Value Calculator
- Time Value of Money Calculator (PV / FV / annuities / perpetuities)

---

## Tech Stack

- Python
- Jupyter Notebook
- NumPy / Pandas
- Matplotlib / Plotly

---

## Run Locally

```bash
git clone https://github.com/jringler30/financial-analytics-toolkit.git
cd financial-analytics-toolkit
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

Then open and run notebooks from the `notebooks/` directory.

---

## Notebook Notes

- `notebooks/DDM.ipynb` uses `yfinance` and requires internet access for market-price lookups.
- `notebooks/portfolio_returns_engine_MVP.ipynb` expects portfolio price data in a CSV/Parquet source and includes example inline assertions.
- `notebooks/PV_FV_Calculator.ipynb` and `notebooks/PV_Coupon_Calculator.ipynb` are interactive calculators that prompt for input values.

---

## Audit

An April 8, 2026 repository audit and remediation summary is available at `AUDIT_REPORT.md`.
