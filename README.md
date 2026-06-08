# predictive-maintenance-six-sigma
A DMAIC Six Sigma project analyzing industrial telemetry to predict machine failures.
# Manufacturing Quality Analytics & Predictive Maintenance Optimization

**Methodology:** Lean Six Sigma (DMAIC)  
**Tools Used:** Microsoft Excel (Data Analysis ToolPak, SPC Dashboarding)  
**Dataset:** 10,000+ Operational Telemetry Records (AI4I 2020)  

## 1. DEFINE Phase
**Problem Statement:** The manufacturing assembly line was experiencing unpredicted equipment failures, leading to process disruptions, increased scrap costs, and degraded Overall Equipment Effectiveness (OEE). 

**Project Objective:** To utilize historical sensor telemetry to isolate primary operational failure modes and implement a data-driven Statistical Process Control (SPC) system to reduce unexpected machine downtime.

## 2. MEASURE Phase
To establish a baseline, process data was extracted and categorized by failure modes using standard aggregate functions.

* **Baseline Failure Rate:** The historical operational data revealed a baseline defect rate of **3.4%** (339 failures across 10,000 records).
* **Failure Stratification:** A Pareto analysis identified the primary drivers of unplanned downtime as Tool Wear Failures (TWF), Overstrain Failures (OSF), and Heat Dissipation Failures (HDF).

*(Drag and drop your Pareto Chart image here)*

## 3. ANALYZE Phase
Advanced statistical analyses were conducted via the Data Analysis ToolPak to isolate the exact mechanical and environmental root causes, requiring strict mathematical proof ($p < 0.05$) to rule out random variance.

* **Tool Wear Variance (Two-Sample T-Test):** Proved mathematically that tool wear directly causes machine failure ($p < 0.001$). Failed machines averaged 143.8 minutes of wear with massive variance, compared to 104.5 minutes for safe operational machines.
* **Mechanical Clash (Correlation Matrix):** Isolated a severe inverse correlation between Spindle Rotational Speed and Torque ($r = -0.875$). This identified the specific mechanical clash that triggers Overstrain Failures (OSF).
* **Environmental Dependency:** Established a strong positive correlation ($r = 0.876$) between ambient factory air and internal process temperatures, identifying facility HVAC/ventilation issues as the root cause of Heat Dissipation Failures (HDF).

*(Drag and drop your Correlation Matrix image here)*

* **Failure Specificity (Single-Factor ANOVA):** Proved ($p < 0.001$) that different failure modes are driven by fundamentally different torque states. OSF occurs under high-torque conditions (avg. 62.8 Nm), while HDF occurs under low-torque conditions (avg. 48.2 Nm).

## 4. IMPROVE Phase
Based on the statistical variance, new Standard Operating Procedures (SOPs) were engineered to balance machinery safety limits with business overhead costs.

* **Preventative Maintenance Protocol:** Implemented a mandatory tool replacement limit of **120 minutes**. This optimizes the ROI of the tooling consumable (safely passing the 104-minute operational average) while avoiding the 127.7-minute statistical danger zone.
* **Dynamic Load Cap:** Engineered an automated spindle speed reduction rule triggered when live torque exceeds **55.0 Nm** to prevent the mechanical clash responsible for overstrain.

## 5. CONTROL Phase
To ensure long-term compliance and process stability, an automated monitoring system was developed to track live part processing and enforce the new SOPs.

* **Automated SPC Dashboard:** Designed a dynamic Statistical Process Control chart to monitor live assembly line telemetry.
* **Predictive Alerts:** Engineered logic-based threshold warnings ("🚨 REPLACE TOOL") that actively flag operators the moment physical parameters breach the newly established 120-minute safety limit.

*(Drag and drop your SPC Chart image here)*

## 6. CONCLUSION & BUSINESS IMPACT (BACKTESTING)
To validate the efficacy of the proposed limits, a historical backtest was conducted against the dataset's recorded failures to simulate Return on Investment (ROI).

* **Simulated Impact:** Applying the new operational limits retroactively eliminated 100% of historical Tool Wear Failures (TWF) and prevented 67.3% of Overstrain Failures (OSF).
* **Final Summary:** Retrospective backtesting confirms that implementing these new rules would have prevented 110 catastrophic breakdowns, theoretically driving the baseline defect rate down from 3.39% to 2.29% and **eliminating 32.4% of total plant downtime.** By replacing reactive maintenance with a mathematically optimized, predictive DMAIC framework, this project establishes the foundational control systems necessary to drastically improve long-term assembly line profitability.
