# Slope Analysis with Machine Learning (Iran)

This project applies **logistic regression** to classify locations as **high-slope** or **low-slope** using environmental and geological factors.  
The goal is to explore whether slope-critical areas can be identified **without directly using slope measurements**, which is relevant for preliminary slope risk screening in geotechnical and mining contexts.

---

## Dataset
The dataset contains terrain, hydrological, land-use, geological, and climate-related variables for locations in Iran.

Main variables include:
- Elevation
- Average annual precipitation (AAP)
- Distance to rivers
- Distance to faults
- Land-use type
- Geological unit
- Climate type

> Note: The raw dataset is not included in the repository.  
> Place `Landslide_Factors_IRAN.csv` inside the `data/` folder before running the code.

---

## Target Definition
A binary target variable is engineered:

- **High slope (1):** slope ≥ 30%
- **Low slope (0):** slope < 30%

To avoid data leakage, **slope percentage is not used as an input feature** in the model.

---

## Methodology
- Data preprocessing using `ColumnTransformer`
- One-hot encoding for categorical variables
- Feature scaling for numerical variables
- Logistic Regression classifier
- Train/test split (80/20) with stratification

---

## Results (Baseline)
- Overall accuracy: ~77%
- Strong performance for low-slope areas
- Lower recall for high-slope areas, reflecting class imbalance and prediction difficulty

These results highlight the challenge of predicting steep terrain using indirect environmental factors alone.

---

## How to Run
```bash
pip install -r requirements.txt
python src/train_logreg.py
