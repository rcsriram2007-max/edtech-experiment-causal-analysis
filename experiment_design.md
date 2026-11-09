# Experiment Design Document (EDD)

## 1. Problem Statement & Objective
A coaching chain implemented an operational and curriculum change last quarter and attributed improved performance to the intervention. However, the reported lift was not verified against baseline seasonality. This experiment design provides a rigorous statistical framework to test future rollouts using randomized controlled trials and quasi-experimental techniques.

## 2. Hypothesis Formulation
- **Null Hypothesis ($H_0$):** The new instructional intervention has no effect on average assessment performance ($\mu_{\text{treatment}} - \mu_{\text{control}} = 0$).
- **Alternative Hypothesis ($H_1$):** The new instructional intervention leads to a statistically significant increase in average assessment performance ($\mu_{\text{treatment}} - \mu_{\text{control}} > 0$).

## 3. Metric Framework
- **Primary Metric:** Average Assessment Score (Continuous, range: 0–100).
- **Secondary Metrics:**
  - Course Completion Rate (Binary indicator: Pass or Distinction).
  - Timely Assignment Submission Rate (% of assessments submitted on or before due date).
- **Guardrail Metric:** Course Drop-off / Withdrawal Rate (`is_dropout`).
  - *Termination Threshold:* If treatment attrition exceeds control attrition by $> 1.5\%$ absolute ($p < 0.05$), the test is halted.

## 4. Power Analysis & Sample Size Sizing
- Significance Level ($\alpha$): 0.05 (two-tailed)
- Statistical Power ($1 - \beta$): 0.80
- Standard Deviation ($\sigma$): Estimated at 28.5 points from baseline cohort
- Minimum Detectable Effect (MDE): 1.5 score points
- **Sample Size per Variant ($n$):**
  $$n = \frac{2 \cdot (Z_{\alpha/2} + Z_{\beta})^2 \cdot \sigma^2}{\text{MDE}^2} = \frac{2 \cdot (1.96 + 0.84)^2 \cdot (28.5)^2}{(1.5)^2} \approx 5,640$$
- Total Active Learners Required: $\approx 11,280$ across both arms.

## 5. Experiment Integrity & SRM Rules
- **Unit of Randomization:** Learner ID (`id_student`), stratified by course module.
- **Sample Ratio Mismatch (SRM):** Evaluated via Chi-Square goodness-of-fit test ($\alpha = 0.01$). If $p < 0.01$, data ingestion is halted to audit assignment hashing.
