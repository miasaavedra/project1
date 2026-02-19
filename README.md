# Mia Saavedra
## Dataset: Pima Indians Diabetes Database (https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

This dataset, originally collected by the National Institute of Diabetes and Digestive and Kidney Diseases (NIDDK), contains diagnostic measurements used to predict diabetes status.

The dataset includes:
* 768 adult female patients (age ≥ 21)
* All participants are of Pima Indian heritage
* 8 predictor variables (clinical and demographic)
* 1 target variable: Outcome (0 = No Diabetes, 1 = Diabetes)

Several variables contain biologically impossible zero values, which were treated as missing during data cleaning.

## Project Overview:
This project conducts structured exploratory data analysis to examine relationships between clinical predictors and diabetes status.
* The analysis focuses on:
 * Assessing diabetes prevalence
 * Comparing predictor distributions by diabetes outcome
 * Evaluating age-group differences in prevalence
 * Investigating correlations among numeric variables

Objective: To investigate how clinical measurements relate to diabetes status through structured exploratory data analysis, integrating statistical reasoning with clinical interpretation while explicitly addressing data quality considerations and assumptions.

## Variables:
* Pregnancies: Number of pregnancies
* Glucose: Plasma glucose concentration at 2 hours in an oral glucose tolerance test
* BloodPressure: Diastolic blood pressure (mm Hg)
* SkinThickness: Triceps skin fold thickness (mm)
* Insulin: 2-Hour serum insulin (muU/ml)
* BMI: Body mass index (weight in kg/(height in m)^2)
* DiabetesPedigreeFunction: Diabetes pedigree function
* Age: Age (years)
* Outcome: Class variable (0 or 1)
  * 268 of 768 are 1, the others are 0

## Data Cleaning:
* Identified biologically impossible zero values in:
  * Glucose
  * BloodPressure
  * SkinThickness
  * Insulin
  * BMI
* Replaced invalid zero values with NaN and analyzed only non-zero values
* Treated Outcome as a categorical target variable for analysis
* Created a clinically meaningful age_group variable for grouped comparisons

## Deliverables/Outputs:
* Comprehensive 10-Point Data Inspection
* Zero-value (missing data) analysis and cleaning documentation
* Exploratory analysis of key predictors (glucose, blood pressure, age, BMI)
* Age-group diabetes prevalence analysis
* Data validation and class imbalance assessment
* Correlation matrix and heatmap of numeric variables
* Presentation slides summarizing methods, results, limitations, and implications

## Key Findings:
* 34.9% of patients in the dataset have diabetes.
* The dataset is moderately imbalanced (65.1% non-diabetic, 34.9% diabetic).
* Insulin (48.7%) and SkinThickness (29.6%) had high rates of missing values.
* Average glucose levels were 31.68 mg/dL higher in diabetic patients.
* Diabetes prevalence increased with age, peaking in the Mature Adult (50–59) age group.
  * The lower prevalence in the 60+ group may reflect a smaller sample size rather than a reduced risk.

## Limitations:
* The dataset is an observational dataset and does not allow causation.
* Missing data encoded as zeros in the original dataset.
* No lifestyle variables (diet, exercise, medication) available.
* Dataset includes only adult female patients (21+) of Pima Indian heritage, limiting generalizability.

## Requirements:
This project was implemented in Python using:
* pandas
* numpy
* matplotlib
* seaborn
