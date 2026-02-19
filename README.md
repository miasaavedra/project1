# Mia Saavedra
## Dataset: Pima Indians Diabetes Database (https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether or not a patient has diabetes, based on certain diagnostic measurements included in the dataset. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage

Observations: 768 female patients
Predictors: 8 clinical and demographic variables
Target Variable: Outcome (0 = No Diabetes, 1 = Diabetes)

Several variables contain zero values that represent biologically impossible measurements and were treated as missing during cleaning.

## Project Overview:
This project analyzes the Pima Indians Diabetes dataset to explore relationships between clinical measurements and diabetes status. The objective is to perform structured exploratory data analysis (EDA), address data quality issues, and examine how variables such as glucose, BMI, blood pressure, age, and pregnancy history relate to diabetes outcome.

The analysis integrates statistical reasoning with clinical interpretation to better understand patterns in the data.

## Variables:
* Pregnancies: Number of pregnancies
* Glucose: Plasma glucose concentration a 2 hours in an oral glucose tolerance test
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
* Created a clinically meaningful age_group variable

## Analyses Performed:
* 10 Point Inspection
* Zero-value frequency and percentage analysis
* Clinical validation of glucose and blood pressure values
* Age group prevalence analysis
* Grouped comparison of average glucose by diabetes status
* Class imbalance assessment
* Correlation heatmap of numeric variables

## Key Findings:
* 34.9% of patients in the dataset have diabetes.
* The dataset is moderately imbalanced (65.1% non-diabetic, 34.9% diabetic).
* Insulin (48.7%) and SkinThickness (29.6%) had high rates of missing values.
* Average glucose levels were 31.68 mg/dL higher in diabetic patients.
* Diabetes prevalence increased with age, peaking in the Mature Adult (50–59) age group.
  * The lower prevalence in the 60+ group may reflect smaller sample size rather than reduced risk.

## Limitations:
* Observational dataset cannot establish causation.
* Missing data encoded as zeros in original dataset.
* No lifestyle variables (diet, exercise, medication) available.
* Dataset includes only adult female patients (21+) of Pima Indian heritage, limiting generalizability.

## Requirements:
This project was implemented in Python using:
* pandas
* numpy
* matplotlib
* seaborn

