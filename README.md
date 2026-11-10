# Startup Due Diligence & Survival Predictive Engine

## Project Overview
This project acts as a comprehensive Business Intelligence and Machine Learning case study for a Venture Capital firm or crowdfunding investor. The objective was to analyze historical startup data to identify the key factors that predict long-term survival, and to build a predictive model that screens investment opportunities for risk.

## The Business Problem
Retail investors and VC firms need to make high-stakes investment decisions. Relying solely on a founder's pitch deck leads to high failure rates. The firm needed a data-driven way to evaluate: *"Is this startup a better investment than the other 50 startups asking for money right now, both in absolute financial terms and compared to its industry peers?"*

## The Dataset
The primary dataset was sourced from historical startup tracking databases (e.g., Crunchbase via Kaggle). The baseline features include:
*   Total Funding Raised & Number of Funding Rounds.
*   Industry Category (SaaS, FinTech, Healthcare, etc.).
*   Geographic Location (Country/Region).
*   **Target Status:** Operating (Survived) vs. Closed (Failed).

## The 4-Pillar Due Diligence Framework
To move beyond basic metrics, this project integrates a deep-dive analytical framework:

### 1. Financial Health & Cash Flow (The "Muscle")
*   **Burn Rate & Runway:** Analyzed the rate at which startups are spending capital to determine how many months they have left before insolvency.
*   **Profitability (P&L):** Evaluated gross margins and revenue against expenses to identify businesses that are scaling unprofitably.

### 2. Competitive Ecology (The "Ecosystem")
*   **Industry Benchmarking:** Instead of evaluating startups in a vacuum, we compared each startup's growth and profitability to the median average of its specific sector.
*   **Market Saturation:** Analyzed the density of competitors in the same geographic location and industry category.

### 3. Traction & Unit Economics (The "Proof")
*   **LTV to CAC Ratio:** Evaluated the Lifetime Value (LTV) of a customer against the Customer Acquisition Cost (CAC) to determine if the startup's growth engine is mathematically sustainable.
*   **MRR Growth:** Analyzed month-over-month recurring revenue to identify momentum.

### 4. Red Flag Risk Assessment (The "Warning Signs")
*   **Founder Dynamics:** Flagged solo-founder startups, which historically have higher failure rates than co-founder teams.
*   **Zombie Rounds:** Identified startups that have raised too many rounds (Series D/E) without an exit event (IPO/Acquisition), indicating potential stagnation.

## Methodology & Technical Stack
*   **Language:** Python
*   **Libraries:** Pandas, NumPy, Scikit-Learn
*   **Model:** Random Forest Classifier / Logistic Regression
*   **Visualization:** Power BI / Tableau

### Technical Steps:
1.  **Data Cleaning & Feature Engineering:** Handled missing values in funding amounts, encoded categorical variables (Industry, Geography), and engineered new features (e.g., `funding_per_round`, `company_age`).
2.  **Exploratory Data Analysis (EDA):** Visualized the baseline survival rate and identified which industries had the highest failure rates.
3.  **Machine Learning (Feature Importance):** Trained a Random Forest model to rank the most important predictors of survival. The model revealed that [Insert your finding here, e.g., "Number of funding rounds was 3x more predictive of survival than the total amount raised"].
4.  **Dashboard Integration:** Designed a "Risk Screener" dashboard concept that allows an investor to input a startup's profile and receive a Survival Probability Score.

## Business Impact
*   Transformed raw, messy startup data into a clear set of investment risk factors.
*   Provided the investment committee with a data-backed framework to evaluate potential portfolio companies.
*   Reduced the risk of investing in high-risk profiles (e.g., "solo founder, pre-revenue" startups) by flagging them early.

## Status
🚧 **Work in Progress:** The Jupyter Notebook containing the ML pipeline and the dashboard visualizations will be uploaded shortly.
