# Traveler Trip Cost Prediction with Seasonal Intensity Score (SIS) and LLM-Based Decision Support

## Overview

**TravelerTripDatasetwithSIS.ipynb** contains the implementation with the proposed **Seasonal Intensity Score (SIS)** feature.  
SIS is computed strictly using **training data only**, ensuring a **leakage-free learning framework** while capturing seasonal variations across destinations and months.

**TravelerTripDatasetwithOutSIS.ipynb** contains the baseline implementation **without SIS**, used for comparative evaluation.

Experimental analysis demonstrates that incorporating SIS enhances:
- seasonal pattern learning  
- interpretability  
- decision-support capability  

---

## Dataset

The dataset used in this study is publicly available:

🔗 https://www.kaggle.com/datasets/rkiattisak/traveler-trip-data

### Dataset Features

- Destination  
- Duration (days)  
- Traveler age, gender, nationality  
- Accommodation type  
- Transportation type  
- Month  
- Accommodation cost  
- Transportation cost  
- Total cost  

---

## Key Contributions

- Introduction of **Seasonal Intensity Score (SIS)**  
- Leakage-safe feature engineering (train-only computation)  
- Multi-target prediction:
  - Accommodation Cost  
  - Transportation Cost  
  - Total Cost  
- Counterfactual explainability framework  
- Integration of **LLM-based decision support layer**  

---

## Seasonal Intensity Score (SIS)

SIS captures seasonal demand variation:

\[
SIS(d, m) = \frac{\mu_{d,m}^{train}}{\mu_d^{train}}
\]

Where:
- \( \mu_{d,m}^{train} \): mean accommodation cost for destination *d* in month *m* (training only)  
- \( \mu_d^{train} \): mean accommodation cost for destination *d* across all months  

### Interpretation

- SIS > 1 → Peak season  
- SIS ≈ 1 → Normal conditions  
- SIS < 1 → Off-peak  

### Leakage Safety

- Computed **only on training split**
- Applied to test data using:
  - destination fallback  
  - month fallback  
  - default value = 1.0  

---

## Data Augmentation Strategy

To improve robustness, a controlled augmentation strategy is applied:

- Synthetic expansion using:
  - **inflation trend simulation**
  - **low Gaussian noise (≈3%)**
- Maintains:
  - statistical consistency  
  - real-world cost patterns  

This approach increases dataset size without introducing unrealistic patterns.

---

## 🤖 LLM-Based Decision Support

A lightweight reasoning layer converts predictions into actionable insights.

### Example Output
