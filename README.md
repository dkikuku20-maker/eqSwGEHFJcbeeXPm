# Customer Satisfaction Prediction (Machine Learning)

## Project Overview
This project predicts whether a customer is **Happy (1)** or **Unhappy (0)** based on survey responses.  
The objective is to identify the **key drivers of customer satisfaction** and evaluate whether fewer survey questions can still provide strong predictive performance.

## Problem Statement
Organizations rely on customer surveys, but long surveys reduce response rates and clarity.  
This project addresses:
- Which survey questions matter most for predicting satisfaction
- Whether survey length can be reduced without losing predictive power
- How machine learning can support data-driven customer experience decisions

**Dataset**
- ~126 customer responses
- Features: X1–X6 (survey question scores)
- Target: Y (customer satisfaction label)

## Approach & Methodology

### 1. Data Preparation
- Loaded and validated survey data
- Checked class balance and feature distributions
- No missing values detected

### 2. Exploratory Data Analysis (EDA)
- Distribution analysis of satisfaction labels
- Correlation analysis between survey questions and satisfaction
- Group comparison of average scores for happy vs unhappy customers

### 3. Modeling
Tested multiple classification models:
- Logistic Regression
- Decision Tree
- Random Forest
- K-Nearest Neighbors
- Support Vector Machine (SVM)

### 4. Evaluation Strategy
- Standard train/test splits showed high variance due to small dataset size
- Used **Repeated Stratified K-Fold Cross-Validation** to obtain more reliable performance estimates
- Performance measured using accuracy

### 5. Feature Selection
- Used correlation analysis and tree-based feature importance
- Identified lower-impact questions that can be removed in future surveys

## Key Results

- **Best-performing model:** Support Vector Machine (RBF kernel)
- **Peak accuracy achieved:** 88% (repeated cross-validation)
- Other models did not consistently reach the required accuracy threshold
- Feature analysis showed that not all survey questions contribute equally

## Business Insights
- A smaller subset of survey questions captures most satisfaction signal
- Long surveys can be shortened while preserving insight quality
- Machine learning can support more focused, efficient customer feedback collection

## Technologies Used
- Python
- pandas
- NumPy
- scikit-learn
- matplotlib / seaborn

## Repository Structure



## How to Run
1. Open the notebook in **Google Colab**
2. Upload the dataset when prompted
3. Run cells from top to bottom

## Future Improvements
- Collect more survey responses to reduce variance
- Test additional satisfaction questions
- Evaluate metrics beyond accuracy (precision, recall, F1-score)
- Add advanced interpretability techniques (e.g., SHAP)
