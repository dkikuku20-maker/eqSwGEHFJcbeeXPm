# Customer Satisfaction Prediction (Survey ML)

## Overview
This project predicts whether a customer is **Happy (1)** or **Unhappy (0)** using answers from a short survey (X1–X6).

The goal was to:
- build a model that can predict happiness
- find which survey questions matter most
- recommend which questions can be removed in future surveys

## Dataset
- Each row = 1 customer
- Features: **X1–X6** (survey question scores)
- Target: **Y** (0 = Unhappy, 1 = Happy)

> Note: This is a small dataset, so model results can change depending on how the data is split.

## Approach (What I Did)
1. **Loaded and checked the data**
   - verified shape, data types, missing values
2. **Exploratory Data Analysis (EDA)**
   - distributions of Y and survey questions
   - correlation matrix
   - average question scores for happy vs unhappy customers
3. **Modeling**
   - tried multiple models (Logistic Regression, Decision Tree, Random Forest, KNN, SVM)
   - used careful evaluation because the dataset is small
4. **Model Evaluation**
   - single train/test split was unstable
   - used **Repeated Stratified K-Fold Cross-Validation** for a more reliable estimate
5. **Feature Importance / Selection**
   - compared correlations + tree-based feature importance
   - suggested a smaller set of survey questions that still captures most signal

## Results (Simple Summary)
- Best model found: **SVM (RBF kernel)** with scaling
- Best performance observed (repeated cross-validation): **88% accuracy** (peak)
- Average performance across splits was lower due to high variance in small datasets

### Why repeated cross-validation?
Because the dataset is small, a single train/test split can give very different results.  
Repeated cross-validation tests the model across many different splits to better understand performance stability.

## Key Insights (For Stakeholders)
- Some survey questions contribute more than others.
- There is overlap between happy and unhappy answers, so prediction is not always easy.
- Recommendation: consider removing the lowest-impact question(s) in the next survey and re-test.

## Files in this Repo
- `notebooks/Customer_Satisfaction_Project.ipynb` — main notebook (EDA + modeling)
- `data/ACME-HappinessSurvey2020.csv` — dataset (if allowed to upload)
- `slides/Customer_Happiness_Project_Full_Summary.pptx` — project summary slides
- `README.md` — this file

## How to Run (Google Colab)
1. Open the notebook in Google Colab
2. Upload the CSV into the Colab session
3. Run cells from top to bottom

## Next Improvements (Future Work)
- Collect more data (bigger sample size)
- Try improving survey design (new questions, clearer scoring)
- Use metrics beyond accuracy (precision/recall/F1) if class imbalance grows
- Add model interpretability tools (per-question impact)
