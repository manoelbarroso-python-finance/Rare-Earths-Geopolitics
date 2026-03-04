# Geopolitical Alpha: The 'Friendshoring' Signal in Critical Minerals

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-LightGBM-orange)
![NLP](https://img.shields.io/badge/NLP-FinBERT-green)
![Alternative Data](https://img.shields.io/badge/Alternative%20Data-GDELT-red)

💡 **Interactive Visualization Notice:** GitHub's native viewer does not render interactive JavaScript charts (Plotly). For the full experience including dynamic cumulative returns and the SHAP beeswarm plot please view this notebook via **NBViewer** or run it live on **Google Colab**:

[![Open in nbviewer](https://img.shields.io/badge/render-nbviewer-orange.svg)](https://nbviewer.org/github/manoelbarroso-python-finance/Rare-Earths-Geopolitics/blob/main/alpha_geopolitics.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/manoelbarroso-python-finance/Rare-Earths-Geopolitics/blob/main/alpha_geopolitics.ipynb)

## 📌 Project Overview
This quantitative research project investigates whether **geopolitical sentiment shocks**—specifically related to **US–China tensions** and **critical minerals supply-chain disruptions** contain **incremental short-horizon signal** for the returns of critical-minerals mining equities.

The core “friendshoring” angle tests whether companies with **Brazil-related exposure** behave differently from global peers during periods of elevated geopolitical stress, after controlling for broad market, sector, FX, and risk-regime factors.

## 🧠 The Differentiator: Alternative Data & NLP (Natural Language Processing)

Instead of relying solely on standard financial news feeds, this project builds an **Alternative Data + NLP** pipeline:

1. **GDELT Project:** Querying a global open event/news database to proxy **geopolitical friction intensity** in near real time.

2. **FinBERT (Hugging Face):** Applying a financial language model to score the sentiment of thousands of English headlines.

3. **Geopolitical Shock Z-Score:** Engineering a rolling standardized metric to isolate **meaningful shifts** in geopolitical stress from day-to-day news noise.

## ⚙️ Methodology & Risk Controls

This project follows strict quantitative research practices to reduce common pitfalls in financial modeling.

- **Temporal Alignment (Anti-Leakage):** All controls (SPY, sector/theme ETFs, VIX, FX) and NLP signals are **lagged** and used to predict **forward returns (T+1 / T+2 / T+5)**. Contemporaneous information is excluded.
- **Validation:** Uses **TimeSeriesSplit** (expanding window) rather than random K-Fold to preserve chronological integrity and simulate a true out-of-sample setting.
- **Algorithm:** Gradient boosting via **LightGBM**, suitable for non-linear tabular relationships.

## 📊 Explainable AI (XAI) Insights

To provide transparency into the model, **SHAP (Shapley Additive exPlanations)** is used to interpret feature impact.

Key takeaways:
- **Signal presence:** The engineered **Geo_Shock_Z** consistently appears among the higher-importance features alongside market/sector proxies.
- **Short-term dynamics:** In the immediate horizon (D+1), elevated geopolitical stress behaves predominantly as a **risk-off / liquidity-drain** signal, pushing next-day direction downward—suggesting any systematic “rotation” may require more time to materialize.

> Note: predicting **daily direction** is inherently noisy, so results are presented with an emphasis on **robust validation, leakage controls, and interpretability** rather than headline performance claims.
*(For detailed visual outputs, including the SHAP summary plot and cumulative return benchmarks, refer to the Jupyter Notebook in this repository).*

## 🚀 How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/manoelbarroso-python-finance/rare-earths-geopolitics.git](https://github.com/manoelbarroso-python-finance/rare-earths-geopolitics.git)
   cd rare-earths-geopolitics

2. Create and activate a virtual environment

python -m venv venv
# On Windows:
.\venv\Scripts\activate

3. Install dependencies

pip install -r requirements.txt

Run the Jupyter Notebook: Open alpha_geopolitics.ipynb in VS Code or Jupyter Lab and execute the cells chronologically.
