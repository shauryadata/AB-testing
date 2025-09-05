# A/B Testing — Onboarding Activation 

**Goal:** Does Variant **B** increase 7-day activation compared to **A**?

This repo contains a simple, reproducible A/B test workflow:
- synthetic dataset (balanced A/B),
- activation rate & uplift,
- two-proportion z-test,
- 95% confidence intervals (Wilson),
- visualization with error bars,
- power analysis (sample size needed).

---

## 📂 Project Structure
ab-testing-onboarding/
├─ data/
│  └─ ab_onboarding_full.csv
├─ notebooks/
│  └─ ab_test_onboarding.ipynb
├─ reports/
│  └─ figures/
│     ├─ ab_activation_ci.png
│     └─ power_curve.png
├─ README.md
├─ requirements.txt   # OR environment.yml
└─ .gitignore
---

## 🔧 Environment & Setup

### Option A — pip (virtualenv)
```bash
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows
# .venv\Scripts\activate

pip install -r requirements.txt
jupyter lab  # or: jupyter notebook
