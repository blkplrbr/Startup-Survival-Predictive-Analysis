# Startup Due Diligence & Survival Predictive Engine

## Project Overview
A comprehensive Business Intelligence, Machine Learning, and Risk Management case study for a Venture Capital firm or crowdfunding investor. The objective is to analyze historical startup data to identify the key factors that predict long-term survival, build a predictive model that screens investment opportunities for risk, and translate that risk into an actionable **investment treatment recommendation** using a formal risk management framework.

## The Business Problem
Retail investors and VC firms need to make high-stakes investment decisions. Relying solely on a founder's pitch deck leads to high failure rates. The firm needs a data-driven way to evaluate: *"Is this startup a better investment than the other 50 startups asking for money right now, both in absolute financial terms and compared to its industry peers?"*

A survival probability score alone does not answer this. The engine must also answer: *"Given this risk profile, what is the rational treatment?"* — i.e., whether to avoid, mitigate, or retain the risk.

## The Dataset
The primary dataset is sourced from historical startup tracking databases (e.g., Crunchbase via Kaggle). Baseline features include:
*   Total Funding Raised & Number of Funding Rounds.
*   Industry Category (SaaS, FinTech, Healthcare, etc.).
*   Geographic Location (Country/Region).
*   **Target Status:** Operating (Survived) vs. Closed (Failed).

## The 4-Pillar Due Diligence Framework

### 1. Financial Health & Cash Flow (The "Muscle")
*   **Burn Rate & Runway:** Analyzed the rate at which startups are spending capital to determine how many months they have left before insolvency.
*   **Profitability (P&L):** Evaluated gross margins and revenue against expenses to identify businesses that are scaling unprofitably.

### 2. Competitive Ecology (The "Ecosystem")
*   **Industry Benchmarking:** Compared each startup's growth and profitability to the median average of its specific sector rather than evaluating startups in a vacuum.
*   **Market Saturation:** Analyzed the density of competitors in the same geographic location and industry category.

### 3. Traction & Unit Economics (The "Proof")
*   **LTV to CAC Ratio:** Evaluated the Lifetime Value (LTV) of a customer against the Customer Acquisition Cost (CAC) to determine if the startup's growth engine is mathematically sustainable.
*   **MRR Growth:** Analyzed month-over-month recurring revenue to identify momentum.

### 4. Red Flag Risk Assessment (The "Warning Signs")
*   **Founder Dynamics:** Flagged solo-founder startups, which historically have higher failure rates than co-founder teams.
*   **Zombie Rounds:** Identified startups that have raised too many rounds (Series D/E) without an exit event (IPO/Acquisition), indicating potential stagnation.

## Risk Management Module (Phase 4)
*The following module is designed and integrated into the repo scaffold. Implementation is planned for Phase 4.*

The engine integrates a formal risk management layer that converts raw survival prediction into a documented investment decision. The methodology draws on a standard risk management framework (identification → measurement → treatment → monitoring) applied to venture capital due diligence.

### Risk Identification (Pure, Speculative, and Financial)
Each startup is tagged against a structured risk taxonomy:
*   **Pure risks:** Operational failure, key-person loss, litigation.
*   **Speculative risks:** Market timing, competitive entry.
*   **Financial risks:** Currency, interest-rate, and sector-cyclicality exposure.
*   **Diversifiable vs. Nondiversifiable:** Company-specific risk vs. sector/macro risk.

### Risk Measurement (Likelihood × Severity Matrix)
Each identified risk is scored on a 1–5 likelihood scale and a 1–5 impact scale, producing a composite **Risk Score = L × I**. This mirrors the "Measure and Analyze" step of the risk management process.

### Risk Treatment Recommendation
Every risk is mapped to one of five standard treatment strategies:

| Treatment | Engine Recommendation |
|---|---|
| **Avoidance** | "Do not invest — Risk Score > 20." |
| **Loss Prevention** | "Invest conditionally — require revenue-share structure to cap downside." |
| **Loss Reduction** | "Invest with milestone tranches." |
| **Retention** | "Invest and self-fund monitoring — risk within tolerance." |
| **Transfer** | "Invest via SAFE/revenue-share or syndicate to share the risk." |

### Retention Capacity Check
The user specifies a maximum acceptable loss (default $500). Any investment where `Probability of Loss × Investment Amount > Retention Capacity` is automatically flagged as **"Exceeds retention capacity — must transfer or avoid."**

### Financial Math Integration
Risk assessment integrates with the existing financial engine:
*   **DCF, NPV, IRR, Gordon Growth terminal value, VC method** — standard valuation.
*   **Risk-adjusted haircut** — replaced by the structured risk register (see above) for defensible, documented risk adjustment.

## Technical Stack
*   **Language:** Python
*   **Libraries:** Pandas, NumPy, Scikit-Learn, `numpy_financial`
*   **Frontend:** Streamlit
*   **ML Model:** Random Forest Classifier / Logistic Regression
*   **Visualization:** Power BI / Tableau / Streamlit dashboards

## Methodology & Technical Steps
1.  **Data Cleaning & Feature Engineering:** Handled missing values in funding amounts, encoded categorical variables (Industry, Geography), and engineered new features (e.g., `funding_per_round`, `company_age`).
2.  **Exploratory Data Analysis (EDA):** Visualized the baseline survival rate and identified which industries had the highest failure rates.
3.  **Machine Learning (Feature Importance):** Feature importance analysis will reveal the dominant survival predictor (e.g., funding-round count vs. total capital raised); results will be added when the model is trained.
4.  **Financial Engine (`financial_math.py`):** Implemented TVM (present value, future value), NPV, IRR, terminal value (Gordon Growth), VC method, and burn-rate/runway calculations.
5.  **Risk Register (`risk_register.py`):** Implemented the identification → measurement → treatment pipeline described above.
6.  **Streamlit Frontend (`app.py`):** Built the user-facing dashboard where investors input startup metrics and receive a survival probability, a risk register, and a treatment recommendation.

## Project Structure
