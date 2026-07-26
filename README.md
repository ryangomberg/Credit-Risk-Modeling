# Credit Risk Modeling
*Loan default predictive analysis and valuation using classification and loss models*

## Project Overview
This project develops classification, loss, and sensitivity modeling for 45,000 loan borrowers. The dataset consists of predictive features, including personal demographics,  loan properties, and credit/loan history, with loan default as the binary response variable (1 = default, 0 = no default). Three families of classification models were employed: logistic regression, linear discriminant analysis (LDA), and ensemble methods. The best performing model was then translated into a continuous-time hazard system to approximate survival curves and probabilities used to measure expected losses for outstanding loan balances. Lastly, first-order Macaulay durations were employed to measure loan sensitivity under varying perturbations in the borrower's loan interest rate. 

## Primary Objectives
* Data cleaning and preprocessing 
* Explore potential correlations for feature v. feature and feature v. response
* Fitting classification models and identifying the best fit based on default F1-scores, RUC, and 10-fold cross-validation on accuracy
* Interest and principal comparison for categorical features
* Use survival curves to model expected loan value and expected losses
* Apply sensitivty and duration principles to estimate the updated value of a loan under a change in interest rate

## Methods
### Preprocessing
* Created a dataframe of entries with missing entries in any column
* Outputted the number of unique values in each feature
* Reordered the education feature to mimic standard progession (ex. high school -> associates -> bachelors -> ...)
* Build categorical and quantiative exclusive dataframes
* One-hot encoding for classification modeling
* 75%/25% train/test split

### Models
* Logistic Regression: with all features, without age and employment experience, and L1-regularization
* Linear Discriminant Analysis with all features
* Ensemble Methods: Random Forest and Gradient Boosting

### Model Evaluation
* Percentage of correct predictions (Accuracy)
* Confusion matrix
* Precision, recall, and F1-scores for default and paid-on-time
* Feature importance
* AUC
* K-fold cross-validation on accuracy
* Bootstrapping 95% confidence intervals on AUC

### Loss Modeling



## Notable Results

## Repository Structure

## Technologies

## Report

## Skills Demonstrated
