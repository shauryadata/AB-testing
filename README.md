# A/B Testing - Onboarding Activation 

**Goal:** Does Variant **B** increase 7-day activation compared to **A**?

This repo contains a simple, reproducible A/B test workflow:
- synthetic dataset (balanced A/B),
- activation rate & uplift,
- two-proportion z-test,
- 95% confidence intervals (Wilson),
- visualization with error bars,
- power analysis (sample size needed).

---

## 🗂️ Data

- **File:** `ab_onboarding_full.csv`  
- **Rows:** 2,000 (A=1000, B=1000)  
- **Columns:**  
  - `user_id` — unique identifier  
  - `variant` — experiment group (A or B)  
  - `country` — user location  
  - `device` — iOS / Android  
  - `activated` — 1 if activated, else 0  

Synthetic but realistic: slight country/device effects, binary target `activated`.

---

## 📓 Notebook Walkthrough

Open `AB-Testing.ipynb` and run cells in order:

1. **Load & quick EDA** → preview rows, counts per variant  
2. **Activation rates & uplift** → compute pA, pB, absolute uplift  
3. **Two-proportion z-test** → statistical significance test (p-value)  
4. **Wilson 95% CIs** → confidence intervals for A and B  
5. **Visualization** → bar chart with error bars  
6. **Power analysis** → required sample size for given MDE

---

## ✅ Results (from this dataset)

| Metric             | Variant A       | Variant B       |
|--------------------|----------------:|----------------:|
| Activated (count)  | 171 / 1000      | 189 / 1000      |
| Activation rate    | **17.1%**       | **18.9%**       |
| 95% CI             | [14.9%, 19.6%]  | [16.6%, 21.4%]  |

- **Absolute uplift:** +1.8 percentage points  
- **z-test:** z = 1.05, p = 0.295 → *not significant*  
- **Power (α=0.05, 80%):** ~7,147 users per group required to detect this uplift  

**Decision:** Do **not** ship Variant B yet. Collect more data or aim for a larger effect.
