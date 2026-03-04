# Geopolitical Alpha: The 'Friendshoring' Signal in Critical Minerals

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-LightGBM-orange)
![NLP](https://img.shields.io/badge/NLP-FinBERT-green)
![Alternative Data](https://img.shields.io/badge/Alternative%20Data-GDELT-red)

## 📌 Project Overview
This quantitative research project investigates whether geopolitical sentiment shocks—specifically regarding **US-China tensions and critical minerals supply chain disruptions**—possess directional predictive power over the short-term returns of mining companies. 

The core thesis explores the **"Friendshoring"** effect: testing if capital systematically rotates toward alternative, neutral jurisdictions (like Brazil) during periods of high geopolitical stress, utilizing the rare earths and lithium sectors as the primary testing ground.

## 🧠 The Differentiator: Alternative Data & NLP
Instead of relying on standard financial news APIs (which often suffer from lag and retail bias), this project leverages **institutional-grade alternative data**:
1. **The GDELT Project:** Querying the global database of events (monitored by global intelligence agencies) to extract real-time geopolitical friction points regarding critical minerals.
2. **FinBERT (Hugging Face):** Applying a fine-tuned financial NLP model locally to extract a continuous sentiment confidence score from unstructured global headlines.
3. **Geopolitical Z-Score:** Engineering a rolling standardized shock metric to isolate true systemic stress from everyday news noise.

## ⚙️ Methodology & Risk Controls
This project adheres to strict quantitative development standards to prevent the most common pitfall in financial modeling: **Look-Ahead Bias**.

* **Temporal Alignment:** All macroeconomic controls (SPY, VIX, FX) and NLP signals are strictly lagged ($T-1$) to predict forward daily returns ($T$). Contemporaneous data is explicitly dropped.
* **Validation:** Utilized `TimeSeriesSplit` (expanding window) rather than K-Fold cross-validation to maintain chronological integrity and simulate a true out-of-sample trading environment.
* **Algorithm:** Gradient Boosting framework via `LightGBM` for robust handling of non-linear financial tabular data.

## 📊 Explainable AI (XAI) Insights
To provide transparency into the "black box" model, **SHAP (Shapley Additive exPlanations)** was implemented. Key findings include:
* **The Alpha Signal:** The engineered Geopolitical Shock Z-score ranked as the 4th most important predictive feature, outperforming traditional metrics like the VIX and FX rates.
* **Risk-Off vs. Friendshoring:** SHAP beeswarm analysis reveals that in the immediate short-term ($D+1$), geopolitical shocks predominantly trigger a generalized "risk-off" liquidity flight, temporarily penalizing emerging market assets regardless of their structural "friendshoring" advantages.

*(For detailed visual outputs, including the SHAP summary plot and cumulative return benchmarks, refer to the Jupyter Notebook in this repository).*

## 🚀 How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/rare-earths-geopolitics.git](https://github.com/your-username/rare-earths-geopolitics.git)
   cd rare-earths-geopolitics

2. Create and activate a virtual environment

python -m venv venv
# On Windows:
.\venv\Scripts\activate

3. Install dependencies

pip install -r requirements.txt

Run the Jupyter Notebook: Open alpha_geopolitics.ipynb in VS Code or Jupyter Lab and execute the cells chronologically.