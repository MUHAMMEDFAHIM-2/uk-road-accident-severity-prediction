# Road Traffic Collision Severity Classification (UK)

## Project Overview
This project investigates the use of supervised machine learning models to predict **road traffic collision severity** in the United Kingdom using official government data.

Using the **DfT STATS19 (2024)** road safety dataset, two classification models—**Logistic Regression** and **Random Forest**—were developed, evaluated, and compared to understand how environmental, road, and vehicle-related factors influence collision outcomes.

The work emphasises:
- Interpretability vs predictive performance  
- Handling severe **class imbalance**
- Practical relevance for **transport safety policy**

This repository contains both the **analysis notebook** and the **formal project report**.

---

## Objectives
- Perform data cleaning and exploratory data analysis (EDA) on real-world collision data
- Train and evaluate multiple classification models
- Address class imbalance using appropriate techniques
- Compare model performance using suitable metrics
- Interpret results in a **policy and safety context**

---

## Dataset
- **Source:** UK Department for Transport (DfT) – STATS19 (2024)
- **Records:** ~100,000 police-reported collisions
- **Features:** Environmental conditions, road type, speed limits, vehicle counts, casualties, time and location indicators
- **Target variable:** Collision severity  
  - `1 = Fatal`
  - `2 = Serious`
  - `3 = Slight`

The dataset is anonymised and compliant with GDPR requirements.

---

## Methodology
### Preprocessing
- Missing value handling (median for numeric, mode for categorical)
- One-hot encoding for categorical variables
- Standardisation of numeric features
- Stratified train–test split (80/20)

### Models Implemented
1. **Logistic Regression**
   - Multinomial classification
   - Class-weight balancing
   - High interpretability

2. **Random Forest**
   - Ensemble decision-tree model
   - Class-weight balancing
   - Variant with **Random Oversampling** for minority classes

### Evaluation Metrics
- Accuracy
- Precision, Recall, F1-score
- **Macro F1-score** (primary metric due to class imbalance)
- Confusion matrices

---

## Key Results
- **Random Forest** achieved the best balance between performance and generalisability.
- Logistic Regression offered superior **interpretability**, but struggled with minority (Fatal) cases.
- Oversampling improved **Fatal collision recall**, at the cost of slight accuracy reduction.
- Speed limit, number of vehicles, and casualty count were the strongest predictors.

---

## Feature Importance Insights
Top contributing factors:
- Speed limit
- Number of vehicles involved
- Number of casualties
- Urban vs rural road classification
- Lighting and road conditions

Environmental variables played a secondary role compared to **structural and behavioural factors**.

---

## Policy Relevance
Findings support data-driven interventions such as:
- Targeted speed-limit enforcement in high-risk rural corridors
- Improved lighting on high-severity road segments
- Infrastructure-based safety planning rather than enforcement-only strategies

The project aligns with the UK’s **Road Safety Strategy** and **Vision Zero** principles.

---

## Repository Structure
├── notebook.ipynb # Full analysis and modelling workflow
├── Project_Report.pdf # Formal academic report
└── README.md # Project overview (this file)

---

## Tools & Technologies
- Python
- pandas, NumPy
- scikit-learn
- imbalanced-learn
- matplotlib, seaborn
- Jupyter Notebook

---

## Limitations
- Severe class imbalance (Fatal <2%)
- No spatial or temporal sequencing of collisions
- Ensemble models reduce interpretability compared to linear models
- Oversampling may introduce synthetic noise

---

## Future Work
- Incorporate spatial (GIS) and temporal features
- Apply advanced imbalance techniques (SMOTE, cost-sensitive learning)
- Experiment with gradient boosting models (XGBoost, LightGBM)
- Develop an interactive dashboard for policymakers

---

## Acknowledgements
- UK Department for Transport (DfT)
- University of Salford

---

## Note
This repository and portfolio content were structured and refined with assistance from **ChatGPT**, based on the author’s original academic work and analysis.
