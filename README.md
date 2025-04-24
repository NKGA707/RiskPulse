# RiskPulse – Market Risk Monitoring Tool

A Python-based command-line tool to track, analyze, and report market risk using real-time data. Built as a showcase project for risk analyst roles in trading, energy, and financial markets.

### 🎥 Video Demo  
[Watch the full walkthrough on Loom](https://www.loom.com/share/f1e3ebc66e8a40c9b3574c95dfbfbf5d?sid=3df8a70f-5c5b-4a08-ad77-53dcf8265d0d)

---

## 📊 Overview

RiskPulse lets you:

- Load market positions from a CSV
- Pull live price data using `yfinance`
- Calculate key risk metrics: volatility, Value at Risk (VaR), Sharpe Ratio
- Generate clear visual charts
- Output a risk summary directly in the terminal

---

## 🧠 Use Case

Designed to simulate how a market risk analyst would:

- Track portfolio exposure across multiple asset types
- Analyze historical performance and tail risk
- Build tools to automate recurring risk reporting

---

## 🗂 Project Structure

```
RiskPulse/
├── riskpulse.py              # Main script
├── risk_data.csv             # Input file with tickers and weights
├── requirements.txt          # Python dependencies
├── charts/                   # Folder to save visual charts
├── test_pulse.py             # (Optional) Unit tests
└── README.md                 # This file
```

---

## 📁 Input: `risk_data.csv`

Sample format:

```csv
Ticker,Weight,AssetType
CL=F,0.3,Oil
NG=F,0.25,Gas
^GSPC,0.2,Equity
^IRX,0.15,Treasury
GC=F,0.1,Commodities
```

Each row defines:
- A market instrument (`Ticker`)
- Portfolio weight (sum ≈ 1)
- Asset class for labeling (optional)

---

## ⚙️ How It Works

1. **Load market positions**
   Reads tickers, weights, and asset types from a CSV file.

2. **Download price data**
   Uses `yfinance` to pull historical adjusted close prices for all assets.

3. **Calculate daily returns**
   Computes percentage changes in prices, handling missing data.

4. **Construct portfolio**
   Multiplies each asset’s returns by its weight to form an aggregate portfolio.

5. **Compute metrics**
   Outputs:
   - Latest daily return
   - Average daily return
   - Volatility (std deviation)
   - Value at Risk (5% quantile)
   - Sharpe Ratio (annualized, assumes 1% risk-free rate)

6. **Generate visuals**
   Automatically saves:
   - Line chart of portfolio value
   - Histogram of return distribution
   - Rolling volatility chart

7. **Summary printout**
   All metrics printed to terminal in a clean, readable format.

---

## 📊 Output Metrics

Example terminal output:

```
📊 Portfolio Risk Summary
----------------------------
• Latest Daily Return: 0.16%
• Average Daily Return: 0.02%
• Volatility (std): 1.46%
• Sharpe Ratio: 1.23
----------------------------

📉 1-Day Historical VaR (95% confidence): -2.1%
```

---

## 📈 Charts

Saved to `charts/`:

- `portfolio_value.png`
- `return_distribution.png`
- `rolling_volatility.png`

---

## 🛠 Installation

### 1. Clone the repo

```bash
git clone https://github.com/your-username/RiskPulse.git
cd RiskPulse
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Usage

Run with:

```bash
python riskpulse.py
```

Make sure `risk_data.csv` exists in the same folder.

---

## 🧪 Optional: Testing

If you’re submitting for CS50 or want to polish, create `test_pulse.py` with unit tests for:

- CSV validation
- Return calculations
- VaR logic

Run tests with:

```bash
pytest test_pulse.py
```

---

## ✨ Future Features

- Streamlit interface
- Email reports or export PDFs
- Add sector or region filters
- More risk metrics (Beta, CVaR)

---

## 👤 Author

Nana Asare  
London, UK  
Email: nkga707@gmail.com

---

RiskPulse — Built to think like a risk analyst.