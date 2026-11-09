# Executive Decision Memo: Causal Impact of Instructional Rollout

**TO:** Academic Board & Operations Leadership  
**FROM:** Experimentation & Analytics Team  
**DATE:** November 2026  
**RECOMMENDATION:** **GO (Scale Rollout with Monitoring)**

---

### 1. Key Analytical Findings

#### A/B Randomized Experiment (Current Initiative)
- **Primary Metric Lift:** Treatment group showed a statistically significant improvement in final assessment score: **+2.20 points** (95% CI: [1.88, 2.52], $p < 0.001$).
- **Variance Reduction (CUPED):** Utilizing early quiz scores as a baseline covariate reduced metric variance by **38.4%**, tightening the 95% CI to [1.94, 2.44]. This allows future trials to achieve the same statistical power with **~38% shorter duration** or a smaller cohort.
- **Guardrail Metric (Attrition):** Drop-off rate was 24.1% in Control vs. 24.3% in Treatment (+0.2% difference, $p = 0.68$), well within the 1.5% guardrail boundary.

#### Difference-in-Differences (Historical Rollout)
- **Reported Raw Lift:** +5.40 points.
- **Causal Average Treatment on Treated (ATT):** **+1.84 points** (95% CI: [1.12, 2.56], $p < 0.001$).
- **Insight:** Approximately 66% of the historically claimed improvement was attributable to natural seasonal progression across terms, confirming that raw before-and-after metrics overstated impact. The net causal lift remains positive.

---

### 2. Heterogeneous Treatment Effects
- **Lower Educational Baseline:** Learners entering with lower prior formal education experienced the largest lift (+3.1 points).
- **Advanced Baseline:** Advanced learners experienced a modest positive lift (+0.9 points).
- No tracked demographic segment exhibited statistically significant performance decline.

---

### 3. Threats to Causal Validity & Mitigations
1. **Parallel Trends Vulnerability:** Regional divergence can confound DiD estimates if local disruptions affect the treated center disproportionately.
2. **Selective Attrition:** If weaker students drop out at unequal rates, assessment scores become subject to survivor bias. This was mitigated by confirming balanced attrition across arms.
3. **SUTVA / Spillover:** Cross-batch student communication in study forums may dilute treatment effects. Center-level cluster randomization is recommended for offline batch rollouts.

---

### 4. Implementation Next Steps
1. Scale the instructional model to all active branches.
2. Integrate continuous automated SRM validation into weekly analytics dashboards.
3. Retain the 14-day inactivity trigger to flag early dropouts for academic intervention.
