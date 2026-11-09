# EdTech Experiment & Causal Analysis

An end-to-end causal inference and experimentation framework to measure the true business and pedagogical impact of instructional changes in an EdTech setting, decoupling real impact from seasonal trends.

## Project Structure
- `edtech_causal_analysis.ipynb`: Colab notebook implementing data deduplication, dropout realignment, A/B test with CUPED variance reduction, and Difference-in-Differences modeling.
- `experiment_design.md`: Complete experiment design document including hypotheses, metric taxonomy, power analysis, and SRM verification protocols.
- `decision_memo.md`: One-page executive brief containing causal findings, subgroup heterogeneity analysis, threats to validity, and business deployment decisions.

## Key Statistical Methods
- **A/B Testing & SRM Check:** Chi-square goodness-of-fit for assignment integrity and Welch's t-test with 95% Confidence Intervals.
- **CUPED (Controlled-experiment using Pre-Experiment Data):** Variance reduction using baseline assessments to compress test duration.
- **Difference-in-Differences (DiD):** Quasi-experimental estimation of historical policy interventions against control regions with parallel trend validation.
