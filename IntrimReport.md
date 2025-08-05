# Interim Report – Brent Oil Price Change Point Analysis

## Project Overview

This project investigates how major political, economic, and geopolitical events influence Brent crude oil prices. The objective is to identify statistically significant change points in the price series and associate these with real-world events, such as conflicts, OPEC policy shifts, economic crises, and pandemics. The project supports Birhan Energies in providing actionable insights for investors, policymakers, and energy companies.

---

## Planned Analysis Workflow

1. **Data Understanding & Preparation**
   - Load daily Brent oil price data (1987–2022).
   - Clean and structure the data (date parsing, missing checks).
   - Convert prices to log returns to stabilize variance and achieve stationarity.

2. **Exploratory Data Analysis (EDA)**
   - Visualize trends, shocks, and volatility clusters in the data.
   - Examine stationarity using the Augmented Dickey-Fuller (ADF) test.

3. **Event Research and Annotation**
   - Curate a structured dataset of 10–15 global events likely to impact oil prices.
   - Align event dates with the price data for later correlation.

4. **Bayesian Change Point Modeling (PyMC3)**
   - Implement a probabilistic model to detect structural changes in the time series.
   - Estimate the timing and magnitude of regime shifts in oil prices.

5. **Event Association & Impact Analysis**
   - Compare detected change points with known events.
   - Quantify how events impacted price behavior (mean/volatility shifts).

6. **Dashboard Development**
   - Build an interactive dashboard (Flask + React) to explore findings.
   - Provide filters, event highlights, and volatility visualizations for stakeholders.

---

## Model Understanding

We are using a **Bayesian Change Point Model**, implemented via PyMC3, which allows us to estimate:

- When a change likely occurred (`τ`, the switch point).
- What changed in the data (e.g., mean level of prices or returns).
- How certain we are about these changes (via posterior distributions).

### Key Concepts:
- **Priors:** Encode our initial beliefs before seeing the data.
- **Likelihood:** Connects our model parameters to the observed data.
- **Posterior:** Updated belief after observing data using Bayes' Rule.
- **MCMC (Markov Chain Monte Carlo):** Sampling algorithm to estimate posterior distributions.

---

## Assumptions & Limitations

- **Correlation ≠ Causation:** Change point detection shows *temporal alignment*, not proof of causality.
- **Market Complexity:** Oil price changes result from many interacting factors; this model focuses on *structural shifts*.
- **Event Timing:** The effect of an event may be lagged or gradual rather than immediate.
- **Model Simplicity:** Initial models assume only one change point; more complex models may be needed.

---

## Communication & Delivery

- **Primary Stakeholders:** Investors, policy advisors, and energy analysts.
- **Communication Channels:** Medium blog post and interactive dashboard.
- **Format:** Visual-first communication (interactive time series + event overlays).

---

## Attached Files

- `data/BrentOilPrices.csv`: Raw historical oil price data.
- `data/brent_events.csv`: Structured list of major events.
- `notebooks/1_eda.ipynb`: EDA and transformation notebook.
