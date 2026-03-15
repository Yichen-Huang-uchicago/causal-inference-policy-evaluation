## causal-inference-policy-evaluation
End-to-end causal inference analysis (RCT, DiD, IV/LATE) evaluating the Oregon Health Insurance Experiment using R.

## 📌 Project Overview
This repository contains a comprehensive suite of applied statistical analyses focusing on **Causal Inference**. Using data from the landmark Oregon Health Insurance Experiment (OHIE) and macroeconomic trade data, this project demonstrates the end-to-end process of evaluating policy impacts, handling imperfect real-world data, and isolating true causal effects from spurious correlations. 

The analysis progresses from foundational Randomized Controlled Trials (RCTs) to advanced econometric techniques like Difference-in-Differences (DiD) and Instrumental Variables (IV/LATE), implemented in **R**.

## 🎯 Executive Summary & Strategic Takeaways

* **The "So What?" of the Policy:** Expanding health insurance (Medicaid) functions primarily as a crucial **financial safety net** (significantly reducing out-of-pocket costs) rather than an immediate cure for physical health or subjective well-being in the short term.
* **Strategic User Segmentation:** The intervention's effectiveness is highly heterogeneous. Vulnerable populations (e.g., those with poor baseline health) and specific demographics exhibit a much higher propensity to utilize outpatient care when financial barriers are removed.
* **The Value of Rigorous Data Science:** Relying on simple correlations in observational data leads to severely biased decisions (e.g., the illusion that higher healthcare spending directly increases life expectancy, which disappears when controlling for GDP). Advanced methods like **Instrumental Variables (IV)** are essential to adjust for real-world non-compliance and uncover the true, actionable impact of an intervention.

## 🛠️ Tech Stack & Methodology
* **Language:** R (`tidyverse`, `AER`, `sandwich`, `lmtest`)
* **Core Methods:** * A/B Testing & RCT Balance Verification
  * Multivariate OLS Regression & Omitted Variable Bias (OVB) Diagnosis
  * Heterogeneous Treatment Effects (HTE) & Linear Hypothesis Testing
  * Difference-in-Differences (DiD)
  * Two-Stage Least Squares (2SLS) / Instrumental Variables (IV)

## 🚀 Key Modules & Analytical Insights

### Module 1: RCT Validation & Intent-to-Treat (ITT) Analysis
* **Objective:** Verify the integrity of the randomized lottery and evaluate the baseline ITT effect.
* **Insight:** Verified that the lottery successfully eliminated selection bias. Found immediate, statistically significant improvements in financial security (reduced out-of-pocket spending), though short-term health scores remained unchanged.

### Module 2: Diagnosing Omitted Variable Bias (OVB) in Observational Data
* **Objective:** Expose the dangers of interpreting simple correlations as causation in observational datasets.
* **Insight:** Demonstrated that a highly significant positive correlation between healthcare expenditure and life expectancy ($p < 0.001$) completely disappeared ($p \approx 0.55$) once per capita GDP was controlled. Highlighted the necessity of rigorous control variables.

### Module 3: Heterogeneous Treatment Effects (HTE) & Model Precision
* **Objective:** Identify which user segments responded most strongly to the intervention.
* **Insight:** Discovered that the intervention disproportionately increased healthcare utilization among vulnerable populations (e.g., poor baseline health) and specific demographic cohorts. Successfully optimized the model fit ($R^2$ improved by >400%) by incorporating full baseline controls.

### Module 4: Overcoming Non-Compliance with Instrumental Variables (IV)
* **Objective:** Measure the *Local Average Treatment Effect (LATE)* when faced with real-world non-compliance (e.g., not all lottery winners enrolled).
* **Insight:** Deployed the randomized lottery assignment as an **Instrumental Variable (2SLS)** to isolate the causal effect of *actual enrollment*. Calculated that actual Medicaid enrollment significantly increased doctor visits for "compliers", successfully resolving endogeneity issues.
