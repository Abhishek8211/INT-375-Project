# Student Outcome Analysis and Prediction

This project explores student academic data to understand patterns behind student outcomes and to build baseline machine learning models for predicting whether a student is likely to:

- Drop out
- Remain enrolled
- Graduate

The analysis is implemented in a Jupyter notebook and includes data preprocessing, feature engineering, visual analytics, and classification models.

## Project Overview

The notebook performs an end-to-end workflow:

1. Load and inspect the dataset (`data.csv`)
2. Clean column names and handle missing/infinite values
3. Engineer academic performance features
4. Explore distributions and relationships with visualizations
5. Train and evaluate classification models

Primary target column:

- `Target` with three classes: `Dropout`, `Enrolled`, `Graduate`

## Dataset Summary

Quick facts from `data.csv`:

- Total records: 4,424
- Total columns: 37 original columns (plus engineered columns created in the notebook)
- Class counts:
  - Dropout: 1,421
  - Enrolled: 794
  - Graduate: 2,209

The dataset contains demographic, academic history, curricular performance, and macroeconomic indicators.

## Feature Engineering

The notebook creates additional features to improve model signal:

- `Total Approved` = 1st sem approved + 2nd sem approved
- `Total Enrolled` = 1st sem enrolled + 2nd sem enrolled
- `Performance` = Total Approved / Total Enrolled

It also replaces infinite values and fills numeric missing values with column means.

## Visualizations Included

The project includes multiple plots for exploratory data analysis:

- Target class distribution (bar chart + pie chart)
- Admission grade boxplot
- Performance histogram
- Average performance by target class
- Correlation heatmap
- Pairplot for key numeric variables
- Line plot of performance vs admission grade

## Machine Learning Models

The notebook trains and compares:

- Logistic Regression
- Decision Tree Classifier

Modeling setup:

- Features: `Admission grade`, `Age at enrollment`, `Performance`
- Target mapping:
  - `Dropout -> 0`
  - `Enrolled -> 1`
  - `Graduate -> 2`
- Train/test split: 80/20 (`random_state=42`)
- Metric: Accuracy

## How to Run

### 1) Create and activate a virtual environment (recommended)

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
```

### 2) Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3) Launch Jupyter

```bash
jupyter notebook
```

Then open:

- `INT 375 Project.ipynb`

## Project Structure

- `INT 375 Project.ipynb` - Main notebook with all analysis, plots, and models
- `data.csv` - Input dataset

## Notes

- The notebook has repeated preprocessing/modeling blocks, likely from iterative development. You can keep only the final cleaned pipeline for a more concise submission.
- Performance values may include division-by-zero cases; these are handled by replacing infinities and imputing numeric means.

## Future Improvements

- Add model metrics beyond accuracy (precision, recall, F1-score, confusion matrix)
- Use cross-validation for more reliable model comparison
- Tune decision tree hyperparameters
- Add feature scaling and model pipelines
- Export the best model and document inference steps

## Author

INT 375 Project
"# INT-375-Project" 
