
# Project Overview

The project aimed to predict mental illness category from text data using pre-trained model from the hugging face. It focuses on identifying categories such as depression, anxiety, bipolar disorder, and more.
The workflow includes:

**Data Preprocessing:** Cleaning and preparing the dataset for analysis.

**Loading Model :** Used a pre-trained model for classification tasks. The model used in the project: https://huggingface.co/kingabzpro/Llama-3.1-8B-Instruct-Mental-Health-Classification

**Evaluation:** Generating metrics such as confusion matrix and accuracy to assess performance.


# Dataset

**Source:** The dataset used is https://huggingface.co/datasets/AhmedSSoliman/sentiment-analysis-for-mental-health-Combined-Data

**Details:** Contains ~53k records with fields:

statement: The textual data (input).

status: The mental health condition label (output).

**Preprocessing Steps:** Dropped unnecessary columns.Removed missing values and duplicates.

# Model

**Base Model:** kingabzpro/Llama-3.1-8B-Instruct-Mental-Health-Classification.
**Fine-Tuning:** The model was fine-tuned using the Hugging Face Transformers library to classify text into seven mental health categories:
Anxiety, Depression, Bipolar, Stress, Normal, Personality Disorder, Suicidal.
