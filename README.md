# Traveler Trip Cost Prediction with Seasonal Intensity Score (SIS) and LLM-Based Decision Support

## Overview

**TravelerTripDatasetwithSIS.ipynb** contains the implementation with the proposed **Seasonal Intensity Score (SIS)** feature.  
SIS is computed using **training data only**, ensuring a **leakage-free framework**.

**TravelerTripDatasetwithOutSIS.ipynb** contains the baseline implementation **without SIS**.

The model with SIS improves:
- seasonal understanding  
- interpretability  
- decision-support capability  

---

## Dataset

Dataset link:  
https://www.kaggle.com/datasets/rkiattisak/traveler-trip-data

---

## Key Contributions

- Seasonal Intensity Score (SIS)  
- Leakage-safe feature engineering  
- Multi-target prediction  
- Counterfactual explainability  
- LLM-based decision support  

---

## Seasonal Intensity Score (SIS)

SIS is defined as:
SIS(d, m) = Mean_Accommodation_Cost(d, m) / Mean_Accommodation_Cost(d)
Where:
- Mean_Accommodation_Cost(d, m) → cost for destination *d* in month *m* (training only)  
- Mean_Accommodation_Cost(d) → overall destination cost (training only)  

### Interpretation

- SIS > 1 → Peak season  
- SIS ≈ 1 → Normal  
- SIS < 1 → Off-peak  

---

## Data Augmentation

To improve robustness:

- Inflation-based scaling  
- Controlled Gaussian noise (~3%)  
- Synthetic data expansion  

This preserves realistic patterns while increasing dataset size.

---

## LLM-Based Decision Support

The system converts predictions into human-readable decisions:
### LLM-Based Decision Output

**Drivers**
- Hotel accommodation choice  
- Trip duration  
- Transportation cost  

**Suggestions**
- Choose budget accommodation options  
- Optimize travel duration  
- Use economical transport alternatives  

**Plan**
- Select affordable lodging and adjust trip schedule  

**Decision**
- Modify  

**Confidence**
- Medium

### Purpose

- Improves interpretability  
- Supports user decisions  
- Bridges ML output → real-world actions  

---

## Model

- Algorithm: Random Forest Regressor  
- Separate models for:
  - Accommodation Cost  
  - Transportation Cost  
  - Total Cost  

---

## Results Summary

### With SIS
- Better seasonal modeling  
- More stable predictions  
- Higher interpretability  

### Without SIS
- Sometimes higher raw accuracy  
- Poor seasonal understanding  
- Less explainable  

---

## Explainability

Includes:

- Counterfactual analysis  
- Error categorization  

---

## Repository Structure

---
## Files

- `TravelerTripDatasetwithSIS.ipynb` → Model with SIS  
- `TravelerTripDatasetwithOutSIS.ipynb` → Model without SIS  

---

## Usage

1. Download dataset  
2. Open notebook in Colab/Jupyter  
3. Run all cells  

---

## Notes

- SIS is computed only from training data (no leakage)  
- Augmentation applied after feature engineering  
- Designed for research + decision support  

---

## Conclusion

This framework combines:

- Feature engineering (SIS)  
- Machine learning  
- Explainable AI  
- LLM-based reasoning  

to build a **practical and interpretable travel cost prediction system**.

---

## License

For academic and research use only.
