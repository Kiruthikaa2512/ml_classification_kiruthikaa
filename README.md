# Midterm Project:Classification Analysis - Mushroom Classification Project — Edibility Prediction

**Author:** Kiruthikaa Natarajan Srinivasan  
**Date:** November 7, 2025

## Overview

This project uses the Mushroom dataset to predict whether a mushroom is **edible** or **poisonous** based on its physical characteristics. The goal is to explore feature patterns, train classification models, and compare their performance. Two models were implemented: **Random Forest** and **Logistic Regression**, using categorical features such as odor, gill size, cap color, and habitat.

## Objectives

- Implement and evaluate two classification models:
  - Random Forest Classifier
  - Logistic Regression
- Explore feature distributions and identify dominant traits
- Encode categorical features and handle zero-variance columns
- Compare model performance using:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - Confusion Matrix
- Reflect on feature impact and model behavior

## Dataset

The Mushroom dataset was loaded from UCI and includes:
- `class`: Target variable (`e` = edible, `p` = poisonous)
- `odor`, `gill-size`, `cap-color`, `habitat`: Selected input features
- `veil-type`: Dropped due to zero variance (only one value `'p'`)

All features are categorical. No missing values were found. Label encoding was applied to prepare the data for modeling.

## Feature Selection

Four features were selected for modeling:

- `odor`: Strong signal for edibility (e.g., foul or fishy odors often indicate poisonous)
- `gill-size`: Broad vs narrow gills may relate to species
- `cap-color`: Visual trait that may help distinguish mushroom types
- `habitat`: Environmental context influencing mushroom growth

These features were chosen based on visual dominance in count plots and biological relevance.

## Model Performance Summary (Test Set)
## Model Performance Summary (Test Set)

| Model Type          | Features Used                        | Accuracy | Precision | Recall | F1-Score | Notes                                           |
|---------------------|--------------------------------------|----------|-----------|--------|----------|-------------------------------------------------|
| Random Forest       | odor, gill-size, cap-color, habitat  | 99.75%   | 99.75%    | 99.75% | 99.75%   | Excellent performance, few misclassifications   |
| Logistic Regression | odor, gill-size, cap-color, habitat  | 95.50%   | 95.60%    | 95.50% | 95.50%   | Slightly lower, limited by linear assumptions   |

## Visualizations

- **Count Plots**: Distribution of `class`, `odor`, `cap-color`, `gill-size`, and `habitat`
- **Confusion Matrices**: For both models
- **Feature Encoding Summary**: Label encoding applied to all categorical features

## Reflections

### Model Behavior

- Random Forest captured nonlinear relationships and performed best overall.
- Logistic Regression was slightly less accurate, likely due to its linear decision boundary.
- `odor` was the most predictive feature, confirming initial exploration.

### Surprises

- The dataset was clean and required minimal preprocessing.
- Even with just four features, the models achieved high accuracy.

### Why Some Models Performed Better

- Random Forest handles categorical data and feature interactions naturally.
- Logistic Regression assumes linear separability, which may not hold for mushroom traits.

## Final Insights

| Model              | Setup                         | Accuracy | Key Insight                                      |
|--------------------|-------------------------------|----------|--------------------------------------------------|
| Random Forest      | Default settings              | 99.75%   | Nonlinear model captured complex feature interactions |
| Logistic Regression| max_iter=1000                 | 95.50%   | Good baseline, but limited by linear assumptions |

## Challenges

- **Kernel Execution Order**: Initial plotting failed due to import cell not running first.
- **Feature Interpretation**: Required careful reading of count plots to identify dominant and rare categories.
- **Encoding Strategy**: Ensured consistent label encoding across all categorical features.

## Next Steps

- Try additional models: Decision Tree, Gradient Boosting, XGBoost
- Explore feature importance scores from Random Forest
- Perform hyperparameter tuning using GridSearchCV
- Visualize decision boundaries and misclassified samples

## Setup Instructions

To run this project locally:

### 1. Clone the repository

```bash
git clone https://github.com/your-username/mushroom-classification.git
cd mushroom-classification
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open `mushroom_classification.ipynb` and run the cells in order.

## 📂 Project Files

- [Click here to view the Jupyter Notebook](https://github.com/Kiruthikaa2512/ml_classification_kiruthikaa/blob/main/classification_ml_kiruthikaa.ipynb)
- [Click here to view the Peer Review Markdown file](https://github.com/Kiruthikaa2512/ml_classification_kiruthikaa/blob/main/peer_review.md)

## Author

**Kiruthikaa Natarajan Srinivasan**  
GitHub: [Kiruthikaa2512](https://github.com/Kiruthikaa2512)
```
