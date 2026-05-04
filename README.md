# Traveler Trip Cost Prediction with and without SIS

## Overview

**TravelerTripDatasetwithSIS.ipynb** contains the implementation with the proposed **Seasonal Intensity Score (SIS)** feature.  
SIS is computed using **only the training data** to ensure a **leakage-free framework**, capturing seasonal variations in travel cost across destinations and months.

**TravelerTripDatasetwithOutSIS.ipynb** contains the baseline implementation **without SIS** for comparison.

Experimental results show that the model **with SIS performs better** in capturing seasonal patterns and improving predictive performance, particularly in explainability and decision-support scenarios.

---

## Dataset

The dataset used in this study is publicly available on Kaggle:

🔗 https://www.kaggle.com/datasets/rkiattisak/traveler-trip-data

It includes features such as:
- Destination
- Duration
- Traveler demographics
- Accommodation type
- Transportation type
- Month
- Cost variables (Accommodation, Transportation, Total)

---

## Key Contribution

- Introduction of **Seasonal Intensity Score (SIS)**  
- Leakage-safe feature engineering  
- Multi-target prediction:
  - Accommodation Cost
  - Transportation Cost
  - Total Cost  
- Explainable AI using counterfactual analysis  
- Comparative evaluation (with vs without SIS)

---

## Results Summary

- SIS improves **seasonal awareness** of the model  
- Enhances **interpretability and decision-making**  
- Provides **more realistic and stable predictions**  

---

## Files

- `TravelerTripDatasetwithSIS.ipynb` → Model with SIS  
- `TravelerTripDatasetwithOutSIS.ipynb` → Model without SIS  

---

## Usage

1. Download dataset from Kaggle  
2. Open notebook in Google Colab or Jupyter  
3. Run all cells sequentially  

---

## Notes

- SIS is computed **only from training data** to avoid data leakage  
- Counterfactual explanations are included for decision support  
- Suitable for research in **AI-driven travel cost optimization**

---

## License

This project is for academic and research purposes.
