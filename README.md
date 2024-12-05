
# Project Overview

The project aimed to predict mental illness category from text data using pre-trained model from the hugging face. It focuses on identifying categories such as depression, anxiety, bipolar disorder, and more.
The workflow includes:

**Data Preprocessing:** Cleaning and preparing the dataset for analysis.

**Evaluation:** Generating metrics such as confusion matrix and accuracy to assess performance.


# Dataset

**Source:** The dataset used is https://huggingface.co/datasets/AhmedSSoliman/sentiment-analysis-for-mental-health-Combined-Data

**Details:** Contains ~53k records with fields:

statement: The textual data (input).

status: The mental health condition label (output).

**Preprocessing Steps:** Dropped unnecessary columns.Removed missing values and duplicates.

# Model

**Base Model:** kingabzpro/Llama-3.1-8B-Instruct-Mental-Health-Classification.
 Used a pre-trained model for classification tasks. The model used in the project: https://huggingface.co/kingabzpro/Llama-3.1-8B-Instruct-Mental-Health-Classification

# Results

## Accuracy:

The overall accuracy of the model is 64.05%, meaning that 64.05% of the predictions match the true labels.

## Classification Report Insights:

**Precision:** Measures how many of the predicted positive samples are correct.
Highest precision is for "Personality disorder" (1.00), but this might be misleading due to its very low recall.
Relatively high precision for "Stress" (0.94) and "Suicidal" (0.84).

**Recall:** Measures how many actual positive samples are correctly predicted.
High recall for "Normal" (0.97) and "Depression" (0.81).
Extremely low recall for "Personality disorder" (0.04), "Stress" (0.14), and "Suicidal" (0.05).

**F1-score:** Balances precision and recall.
Best F1-score is for "Normal" (0.82), while other categories have lower scores, especially for underrepresented classes like "Personality disorder."

The result is not good for Personality disorder, Stress and Suicidal because there are not enough data to train the model on these labels.

## Confusion Matrix Observations:

**"Normal" and "Depression" dominate predictions:** "Normal" has the highest number of correct predictions (593), and "Depression" is often correctly classified (494).

**Severe misclassifications for "Suicidal":** Most "Suicidal" cases are misclassified as "Depression" (285 cases).

**Poor performance on minor classes:** Classes like "Personality disorder" and "Stress" suffer from low recall and high misclassification rates, likely due to class imbalance.

The model is biased predicting towards to depression and normal and against Suicidal as the model predicted wrong for most suicidal cases.

# Key Observations:

**Imbalanced Classes:**
Smaller classes like "Personality disorder" and "Stress" have significantly fewer samples compared to dominant classes like "Depression" and "Normal." This imbalance likely affects recall and the overall performance of the model on these categories.

**Overlap in Mental Health Categories:**
The confusion matrix shows significant overlap between similar categories, particularly "Suicidal" and "Depression." This suggests that the model struggles to differentiate between nuanced mental health conditions.

**Bias Toward Larger Classes:**
The model performs better on larger classes such as "Normal" and "Depression," while smaller classes (e.g., "Personality disorder," "Stress") are underrepresented in correct predictions.


# Conclusion:

**Handle Class Imbalance:** The model needs more data for smaller groups like "Personality disorder" and "Stress" or adjustments to treat all groups more equally by oversampling or undersampling.

**Improve Differentiation:** The model confuses similar categories, like "Suicidal" and "Depression," so it may need better input features or more detailed training examples.

**Focus on Smaller Groups:** We need to make sure the model recognizes less common categories better, not just the big ones like "Normal" or "Depression".

We should check how well the model predicts on other labels if we dismiss “Depression” and “Suicidal”.

![Unknown-3](https://github.com/user-attachments/assets/d0d4c85a-0ef2-4015-8ef9-4d5278939d46)

