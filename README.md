README: Impact of 2018 Steel/Aluminum Tariffs on the U.S. Automotive Industry
Overview
This repository contains code and analysis for a quasi-experimental study evaluating the downstream effects of the 2018 U.S. steel and aluminum tariffs on the automotive industry. Using a Difference-in-Differences (DiD) framework, the research compares quarterly trends (2005–2024) in real gross output, input prices, value added, and employment between the automotive sector (treatment group) and the chemical manufacturing sector (control group). Despite initial significant results, critical diagnostic tests revealed violations of the parallel trends assumption, rendering causal claims unreliable. This project highlights the methodological challenges of isolating policy impacts in complex economic systems.

Key Features
Data Integration: Harmonizes quarterly economic data from the BEA and monthly employment data from the BLS.

Dynamic Visualization: Time-series plots with tariff implementation markers (2018 Q2) and COVID-19 impact periods (2020 Q1–2021 Q1).

Difference-in-Differences Analysis:

Baseline DiD Models: Tests for relative changes post-tariff.

Robustness Checks:

Parallel Trends Pre-Tests: Event-study plots to validate assumptions.

Placebo Tests: Artificial intervention in 2014 to detect spurious effects.

Transparent Workflow: Fully reproducible R code with detailed comments.

Data Sources
1. Economic Indicators
Bureau of Economic Analysis (BEA)

Variables: Real gross output, real intermediate input prices, real value added.

Industries:

Motor vehicles, bodies and trailers, and parts (treatment group)

Chemical products (primary control group)

Food and beverage/tobacco products (secondary control group)

Frequency: Quarterly (2005–2024)

2. Employment Data
Bureau of Labor Statistics (BLS)

Variables: Employment (converted from monthly to quarterly).

Frequency: Quarterly (2005–2024)

3. External Shocks
COVID-19 Dummy: 2020 Q1–2021 Q1.

Tariff Implementation Date: 2018 Q2.

Methodology
1. Difference-in-Differences (DiD)
Model:

plaintext
Y = β₀ + β₁*Treated + β₂*Post + β₃*(Treated × Post) + β₄*Covid + ε  
Treated: 1 for automotive industry, 0 for chemical industry.

Post: 1 for periods after April 2018.

2. Diagnostic Tests
Parallel Trends Pre-Test: Event-study design with dynamic treatment effects.

Placebo Test: Shift treatment date to 2014 to detect pre-existing trends.

3. Visual Validation
Key Trends: Real gross output, input prices, value added, and employment.

Event-Study Plots: Pre-/post-tariff coefficient dynamics.

Key Findings
1. Initial DiD Results
Outcome	Treated × Post Coefficient	Significance
Real Gross Output	+98.86 (***)	p < 0.001
Real Input Prices	+104.51 (***)	p < 0.001
Employment	+129.41	Not Significant
2. Diagnostic Results
Parallel Trends Violation: Significant pre-tariff divergences in trends (Graph 3).

Placebo Test Significance: Artificial 2014 "tariff" showed similar effects, confirming pre-existing trends.

3. Conclusion
Observed differences likely reflect pre-existing industry trends rather than causal tariff effects.

Chemical industry proved inadequate as a control group due to structural differences.

Reproducing the Analysis
1. Requirements
R Packages:

R
install.packages(c("tidyverse", "readxl", "lubridate", "ggplot2", "Synth", "plm", "did", "patchwork"))
Data: Proprietary BEA/BLS Excel files (not included here).

2. Code Structure
Data Preparation:

GrossOutput.xlsx, IntermediateInputs.xlsx, ValueAdded.xlsx: Economic indicators.

Motor vehicles and parts.xlsx, etc.: Employment data.

Analysis:

Data Cleaning: Harmonize monthly employment to quarterly.

DiD Regressions: lm() models with interaction terms.

Event-Study Plots: did::att_gt() and ggdid().

3. Outputs
Figures:

combined_plots.png: Industry trends with tariff/COVID markers.

realgross_pt.png, valadded_pt.png: Event-study plots for parallel trends.

Tables: Regression results (e.g., Table 2, Table 3).

Limitations
Control Group Adequacy: Chemical industry trends diverged pre-tariff.

Confounding Factors: COVID-19, supply chain disruptions, and retaliatory tariffs not fully isolated.

Data Granularity: Quarterly data may mask short-term dynamics.

Future Directions
Synthetic Control Method (SCM): Construct data-driven counterfactual.

Advanced DiD Estimators: Callaway & Sant'Anna or Gardner two-way fixed effects.

Firm-Level Analysis: Disaggregate industry-wide effects.

Author
Chien Tran

Affiliation: Denison University

Contact: trand.chien1993@gmail.com

GitHub: [Your Profile Link]

Note: This study underscores the importance of rigorous robustness checks in quasi-experimental policy analysis. While the 2018 tariffs were anticipated to impact automotive manufacturers, methodological constraints prevent definitive causal conclusions. Code and visualizations are provided for transparency and further exploration.
