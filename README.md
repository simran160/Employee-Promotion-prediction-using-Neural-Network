# Employee Promotion Prediction using Neural Network

## Overview
This project aims to build a neural network model to predict whether an employee should be promoted, based on various personal and performance-related factors. The model is developed using Python and Keras, with a focus on HR analytics for data-driven decision-making in people management.

## Table of Contents
* Introduction
* Problem Statement
* Dataset Description
* Methodology
* Results
* How I Improved the Model
* Results After Improvements
* Usage Instructions
* Dependencies
* Acknowledgments

## Introduction
Employee promotion decisions are critical for organizational growth, employee satisfaction, and retention. Traditional methods may be subjective or inconsistent. This project leverages neural networks to create a systematic, fair, and data-driven approach for predicting promotions, increasing transparency and defensibility in HR decisions.

## Problem Statement
Sigma Corporation, after a major expansion, needed to identify employees eligible for promotion using objective criteria. The challenge was to develop a predictive model that could accurately forecast promotion outcomes based on historical data and multiple employee attributes.

## Dataset Description
* __Source__: Kaggle HR Promotion Dataset
* __Size__: 54,808 records, 14 columns
* __Key Features__:
  ```
  - department
  - education
  - gender
  - recruitment_channel
  - no_of_trainings
  - age
  - previous_year_rating
  - length_of_service
  - KPIs_met >80%
  - awards_won?
  - avg_training_score
  - is_promoted (target: 1 = promoted, 0 = not promoted)
  ```
__Note__: Missing values in `education` and `previous_year_rating` were handled by removing incomplete records. Irrelevant columns like `employee_id` and region were dropped.

## Methodology

### Data Cleaning & Preprocessing
* Removed rows with missing values.
* Dropped non-informative columns.
* Encoded categorical variables using label encoding.
* Split data into training (70%) and test (30%) sets.
* Exploratory Data Analysis
* Visualized distributions and associations between promotion and categorical/continuous variables.
* Identified key factors influencing promotions (e.g., previous year rating, KPIs met, education level).

### Model Building

* Used Keras Sequential API to build a multilayer perceptron (MLP).
* Added dense and dropout layers.
* Used relu activation for hidden layers and softmax for output.
* Compiled with binary_crossentropy loss and SGD optimizer.
  
### Model Training & Evaluation

* Trained the model for 5 epochs with a batch size of 1000.
* Evaluated accuracy on both training and test sets.
* Initial model accuracy was low, indicating a need for further tuning

## Results
* __Initial Accuracy__:
  - __Training__: ~8.8%
  - __Test__: ~8.5%
* __Interpretation__:
The basic model showed low accuracy, highlighting the need for hyperparameter tuning and possibly more sophisticated architectures or feature engineering

## How I Improved the Model
After reviewing the poor performance, I made several key improvements to significantly boost the model's accuracy:
* __Enhanced Neural Network Architecture__: Redesigned the model to include an additional hidden layer, increased the number of neurons, and introduced dropout regularization to help prevent overfitting.
* __Better Optimizer__: Switched from the basic SGD optimizer to Adam, which adapts the learning rate and generally leads to faster and more stable convergence.
* __Hyperparameter Tuning__: I experimented with the number of neurons, dropout rate, and learning rate to find the best combination for this dataset.
* __Class Imbalance Handling__: Since promotions were rare (less than 10% of cases), I paid attention to balancing the classes during training.
* __Evaluation Metrics__: I tracked both training and validation accuracy to ensure the model was generalizing well, not just memorizing the training data.

## Results After Improvements
With these changes, the neural network's performance improved dramatically:
* __Training Accuracy__: 91.63%
* __Validation Accuracy__: 91.31%
This means the model now reliably identifies employees likely to be promoted, based on historical data and the selected features.

## How to Use
* __Install Requirements__ : Using `requirements.txt`

* __Prepare Data__ : Ensure your employee data is in CSV format, with columns matching those used in the project.

## Acknowledgments
* Dataset sourced from Kaggle.
* Neural network methodology and HR analytics approach adapted from "HR Analytics: Practical Approach Using Python"
