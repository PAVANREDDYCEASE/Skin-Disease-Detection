# Skin Disorder Prediction (PRCP-1027)

## Project Overview

Machine learning classification of six
erythemato-squamous skin disease categories using
clinical and histopathological patient features.

This is an educational project, not a clinically
validated diagnostic system.

## Dataset

- Total patients: 366
- Input features: 34
- Disease classes: 6
- Missing values: 8 (Age)
- Training patients: 292
- Test patients: 74

## Methodology

1. Dataset inspection and EDA
2. Data quality assessment
3. Stratified train-test splitting
4. Median imputation and feature scaling
5. Five-fold cross-validation
6. Model comparison and selection
7. Final test evaluation
8. Model export and prediction demonstration

## Model Comparison

| Model | CV Accuracy | CV Macro F1 |
|---|---:|---:|
| Dummy Classifier | 0.3048 | 0.0779 |
| Logistic Regression | 0.9794 | 0.9768 |
| Gaussian Naive Bayes | 0.8972 | 0.8776 |
| Random Forest | 0.9760 | 0.9704 |
| SVM | 0.9794 | 0.9768 |

## Selected Model

Logistic Regression with median imputation
and StandardScaler.

### Held-Out Test Results

- Accuracy: 95.95%
- Macro F1: 0.9574
- Balanced Accuracy: 96.11%
- Weighted F1: 0.9606
- Correct predictions: 71/74

## Visualizations

### Confusion Matrix
![Confusion Matrix](skin_disorder_outputs/confusion_matrix.png)

### Per-Class Recall
![Per-Class Recall](skin_disorder_outputs/per_class_recall.png)

### Model Comparison
![Model Comparison](skin_disorder_outputs/model_comparison.png)

### Clinical-Only vs Full Features
![Clinical Comparison](skin_disorder_outputs/clinical_vs_full.png)

## Clinical-Only Experiment

A 12-feature clinical-only model achieved
an out-of-fold Macro F1 of 0.8733.

The full-feature model achieved 0.9771.

This suggests that histopathological
measurements contributed additional predictive
information in this dataset.

## Installation

Install the dependencies:

    pip install -r requirements.txt

Place the dermatology dataset CSV in the project
folder and run the Jupyter Notebook cells in order.

## Saved Outputs

The skin_disorder_outputs folder contains the
trained model, metadata, evaluation reports,
prediction demonstration and visualization files.

## Challenges

- Small dataset
- Missing patient ages
- Uneven disease-class distribution
- Similar features across disease categories
- Lower clinical-only classification performance

## Limitations

The dataset contains only 366 patients.
Class 6 has only four test patients.
No external clinical validation was performed.

The model is not intended for clinical diagnosis,
treatment decisions or unsupervised medical use.

## Conclusion

Logistic Regression was selected as the final
model after evaluating five algorithms.

It achieved 95.95% accuracy and a Macro F1 of
0.9574 on the reserved test set.
