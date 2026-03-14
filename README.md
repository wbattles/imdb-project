# IMDb Movie Rating Prediction

A data mining project using machine learning to predict whether a film will be highly rated by viewers, based on publicly available IMDb datasets.

## Abstract

This project explores whether a film's rating can be predicted from factors like genre, runtime, director, and lead actor. Using IMDb data, films were binned into four rating categories (Terrible, Poor, Average, Excellent) and four classification models were evaluated. Results showed that all models performed similarly in overall accuracy, but struggled to correctly identify *Excellent* films due to class imbalance — most films fall in the Average bin. The key finding is that public opinion is too subjective and variable-sparse to reliably predict from a limited set of film traits.

## Models Used

- Logistic Regression
- Naive Bayes
- Bagging (Bootstrap Aggregating)
- Random Forest

## Dataset

Five publicly available IMDb datasets (accessed March 2023), filtered to:
- English-language films only
- Non-adult, traditional movie titles
- Released 2000 or later
- Minimum 20,000 user votes

Final dataset: **4,777 films** with features for rating, runtime, up to 3 genres, director, and lead actor.

## Rating Bins (Target Variable)

| Class     | Rating Range |
|-----------|-------------|
| Excellent | 7.5 – 10    |
| Average   | 5.9 – 7.4   |
| Poor      | 3.6 – 5.8   |
| Terrible  | 0 – 3.5     |

## Key Results

| Model               | RMSE   |
|---------------------|--------|
| Logistic Regression | 0.3968 |
| Naive Bayes         | 0.4021 |
| Bagging             | 0.3956 |
| Random Forest       | 0.3909 |

All models achieved high F1 scores for predicting *non-Excellent* films (~0.91) but performed poorly on positive classification of Excellent films (0.13–0.34), revealing a significant class imbalance problem.

## Tech Stack

- Python (Jupyter Notebook)
- pandas
- scikit-learn
- scikit-plot / matplotlib

## Repo Structure

```
├── README.md
├── paper.pdf              # Full paper
├── rawData/               # Source IMDb datasets (projectData.csv)
├── finalCode/             # Consolidated notebook with all four models
├── logReg/                # Logistic regression notebook
├── nieveBayes/            # Naive Bayes notebook
├── trees/                 # Bagging and random forest notebooks
└── cluster/               # Exploratory hierarchical clustering analysis
```

## Full Paper

See [`paper.pdf`](./paper.pdf) for the complete methodology, results, and references.
