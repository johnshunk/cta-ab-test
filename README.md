# A/B Testing: CTA Button Experiment

This project analyzes a simulated A/B test comparing two versions of a call‑to‑action (CTA) button to determine whether a new design (Variant B) improves conversion rates compared to the existing version (Variant A). The goal is to demonstrate a full end‑to‑end experimentation workflow, including data generation, statistical testing, visualization, and business interpretation.

---

## Project Overview

Modern product teams rely heavily on A/B testing to make data‑driven decisions. This project simulates a realistic experiment by generating synthetic web analytics data for 10,000 users, randomly assigning them to Variant A or Variant B, and modeling conversions based on predefined probabilities.

The analysis walks through:

- Experiment design  
- Data exploration  
- Conversion rate comparison  
- Two‑proportion z‑test  
- Confidence intervals  
- Lift analysis  
- Statistical power  
- Final recommendation  

This project is intentionally scoped to be clean, interpretable, and portfolio‑friendly.

---

## Experiment Design

**Objective:**  
Determine whether Variant B’s CTA increases conversion rate compared to Variant A.

**Primary Metric:**  
`converted` (1 = user converted, 0 = did not convert)

**Randomization:**  
Users were assigned 50/50 to Variant A or Variant B.

**Simulated Conversion Rates:**  
- Variant A: 8%  
- Variant B: 9.5%  

These values create a modest but realistic lift, allowing for meaningful statistical testing.

---

## Dataset

The dataset contains 10,000 rows and three columns:

| Column     | Description |
|------------|-------------|
| `user_id`  | Unique identifier for each user |
| `variant`  | A (control) or B (treatment) |
| `converted`| 1 if the user converted, 0 otherwise |

The dataset is generated using Python and included in the repository as `cta_ab_test_data.csv`.

---

## Analysis Summary

### **Conversion Rates**
Variant B showed a higher conversion rate than Variant A.

### **Statistical Significance**
A two‑proportion z‑test found the difference to be statistically significant at the 95% confidence level.

### **Confidence Intervals**
The confidence intervals for the two variants show some overlap, which suggests the lift is modest and the exact effect size has some uncertainty.

### **Lift**
Variant B produced a positive lift relative to Variant A.

### **Power**
The experiment had sufficient power to detect the observed effect size.

---

## Final Recommendation

Variant B’s CTA shows a statistically significant improvement in conversion rate. The confidence intervals overlap a bit, which means the lift is modest, but the direction is clearly positive. I recommend rolling out Variant B to all traffic and keeping an eye on performance as it scales.

---

## Repository Structure

```
├── data/
│   └── cta_ab_test_data.csv
├── notebooks/
│   └── cta_ab_test_analysis.ipynb
├── src/
│   └── generate_data.py
└── README.md
```

---

## Tools & Libraries

- Python  
- pandas  
- numpy  
- seaborn  
- matplotlib  
- statsmodels  

---

## Future Improvements

- Add secondary metrics (page views, session time, bounce rate)  
- Run Bayesian A/B testing  
- Explore segmentation (device type, traffic source)  
- Build a dashboard in Power BI or Tableau  
- Simulate sequential testing or multi‑armed bandits
