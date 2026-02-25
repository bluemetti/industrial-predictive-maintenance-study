# Predictive Maintenance – Industrial Failure Prediction (Mini Study)

This repository contains an end-to-end predictive maintenance baseline aligned with Industry 4.0 and production AI use-cases.

The objective is to predict machine failure using operational sensor data from the AI4I 2020 dataset.

---

## Project Overview

This mini-study demonstrates:

- Structured data preprocessing using pandas
- Exploratory Data Analysis (EDA)
- Baseline ML modeling with scikit-learn
- Handling of class imbalance
- Decision threshold tuning
- Feature importance analysis

The workflow mirrors a simplified industrial AI pipeline for production systems.

---

## Dataset

- AI4I 2020 Predictive Maintenance Dataset
- 10,000 samples
- 339 failure events (~3.4%)
- Multiple sensor features (temperature, torque, rotational speed, tool wear, etc.)

The dataset is intentionally imbalanced, reflecting realistic industrial scenarios.

---

## Modeling Approach

### 1. Preprocessing
- Removal of ID columns
- Removal of failure subtype leakage features (TWF, HDF, PWF, OSF, RNF)
- One-hot encoding of categorical variable (`Type`)
- Train-test split with stratification

### 2. Baseline Model
- RandomForestClassifier (300 trees)
- Class weight balanced

### 3. Threshold Tuning

Initial model:
- Failure recall ≈ 0.45

After adjusting decision threshold:
- Failure recall ≈ 0.67
- F1-score ≈ 0.71

This demonstrates awareness of precision–recall trade-offs in predictive maintenance systems.

---

## Key Insights

- Operational features such as torque, rotational speed, and temperature differences significantly influence failure prediction.
- Threshold tuning improves early detection capability, which is critical in maintenance planning.
- The pipeline is modular and can be extended to API deployment (e.g., FastAPI + Docker).

---

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run Jupyter:

```bash
jupyter notebook
```

Open:

```
notebook/predictive_maintenance_study.ipynb
```

---

## Next Steps

- Hyperparameter optimization
- Time-aware validation
- Model calibration
- FastAPI inference endpoint
- Containerization with Docker

---

## Alignment with Production AI

This study reflects a simplified Industry 4.0 workflow:

data → preprocessing → modeling → evaluation → operational tuning

It is designed to simulate real-world predictive maintenance system development.