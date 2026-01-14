# Commodity-pricing-two-factor
Kalman filter

**Author:** Talihaer Mahaya  
**Institution:** Emlyon Business School (MSc in Quantitative Finance)  
**Tech Stack:** Python, Kalman Filter, Monte Carlo Simulation, Stochastic Calculus

---

## 1. Project Overview

This project computationally validates the theoretical framework proposed by Schwartz and Smith (2000) for commodity pricing. By analyzing the term structure of **Crude Oil Futures**, the model decomposes spot price dynamics into two stochastic factors:
1.  **$\chi_t$ (Short-Term Deviation):** A mean-reverting process representing temporary supply/demand imbalances.
2.  **$\xi_t$ (Equilibrium Level):** A geometric Brownian motion representing fundamental economic changes.

The goal is to calibrate these latent state variables from noisy futures data and use them to value derivative contracts.

## 2. Key Technical Implementations

This repository demonstrates the application of advanced quantitative methods in asset pricing:

### A. State-Space Modeling & Kalman Filter
- Formulated the **State-Space representation** of the two-factor model.
- Engineered a **Kalman Filter** algorithm (utilizing `pykalman`) to recursively estimate the unobservable state variables ($\chi_t, \xi_t$) from observed futures prices.
- Implemented the **Expectation-Maximization (EM)** algorithm to calibrate structural parameters ($\kappa, \sigma_\chi, \sigma_\xi, \rho$) against historical data.

### B. Derivatives Pricing (Analytical & Numerical)
- **Risk-Neutral Valuation:** Derived and implemented closed-form pricing formulas for Futures and European Options on Futures.
- **Monte Carlo Simulation:** Developed a simulation engine generating **10,000 stochastic price paths** to cross-validate the analytical pricing results.
- **Characteristic Functions:** Implemented characteristic functions for the log-spot price to facilitate Fourier Transform-based pricing methods.

## 3. Repository Structure

```text
├── data/
│   └── Prices.xlsx            # Historical Crude Oil Futures data
├── notebooks/
│   └── Two_Factor_Model.ipynb # Complete Jupyter Notebook (Code + Math + Analysis)
├── Commodity_Pricing_Report.html # Rendered HTML report (Best for viewing)
└── README.md                  # Project Documentation
