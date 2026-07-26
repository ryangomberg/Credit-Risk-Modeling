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

### Exploratory Data Analysis
* VIF

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

### Amortization and Loss Modeling
* Debt-to-income ratio
* Interest and principal calculations
* Hazard rate and survival probability
* PD, EAD, LGD
* First order Macaulay duration

## Notable Results
* Identified multicollearity between age, employment experience, and credit history length
* Previous loan defaults appeared to have the strongest contribution in loan defaults
* A boosted ensemble model promises the highest predictablility and separability power, with F1-scores of 96% and 85% for default and paid-on-time, respectively, as well as an AUC of 97.93%
* Found a monotonic decrease and increase between interest and principal, respectively
* The expected loan value has a concave relationship with survival probability: ELV monotonically decreases as survival probability decreases. Consequently, the expected loss ratio increases
* As the interest rate increases, the present value of expected payments declines due to heavier discounting
* Increases in interest rates substantially reduces the present value of expected loan payments, exposing the lender to interest rate risk

## Repository Structure
```
Credit-Risk-Modeling/
│             
├── code/
│   ├── 1 - Introduction to the Dataset, Objectives
│   ├── 2 - Preprocessing
│   ├── 3 - Exploratory Data Analysis
│   ├── 4 - Models & Methodology
│   ├── 5 - Amortization Modeling
│   ├── 6 - Default Risk Measurement
│   ├── 7 - Expected Loss Modeling
│   └── 8 - Sensitivity
├── data/
│   └── loan_data.csv
├── report/
│   └── Credit Risk Modeling.pdf
│
└── README.md
```


## Technologies
### Data
See data/loan_data.csv

### Software
Python (Jupyter Notebook)

### Modules
* Pandas
* Numpy
* Matplotlib
* Sklearn
* Seaborn
* Statsmodels

## Report
<img width="568" height="457" alt="image" src="https://github.com/user-attachments/assets/fb2e05d0-ab07-4bc1-9f3b-1e18e1fc678e" />
<img width="589" height="350" alt="image" src="https://github.com/user-attachments/assets/dd194267-449f-44c3-8ff2-15cb16373f7e" />

See report/Credit Risk Modeling.pdf

## Skills Demonstrated
* Data Preprocessing and Cleaning
* Exploratory Data Analysis
* Multicollinearity, VIF
* Classification modeling and probability estimation
* Classification accuracy
* Confusion matrices
* Feature importance
* Precision, recall, F1-score
* AUC curves
* K-fold cross validation
* Bootstrapping
* Confidence intervals
* Interest and principal computation
* Amortization scheduling
* Debt-to-income (DTI) ratio
* Hazard rates and survival curves
* Expected loan value and lender return
* PD, EAD, LGD
* Macaulay duration
* Loan amount sensitivity
