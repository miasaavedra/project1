# Week 3 Assignment: Pima Indians Diabetes Dataset Analysis

## I 320D: Data Science for Biomedical Informatics | Spring 2026

### 📋 Assignment Version A

---

## 🎯 This Week's Mantra

> **"Every Column Tells a Story"**

In this assignment, you'll apply the 10-Point Data Inspection to a real-world healthcare dataset focused on diabetes prediction. By the end, you'll understand not just *what* the data contains, but *why* each variable matters for clinical decision-making.

---

## Learning Objectives

By completing this assignment, you will be able to:

1. ✅ Apply the systematic 10-Point Inspection to a new healthcare dataset
2. ✅ Identify and classify feature types (continuous, discrete, categorical, ordinal)
3. ✅ Detect and document data quality issues (missing values, zero-encoded values)
4. ✅ Research and document clinical meaning for healthcare variables
5. ✅ Create meaningful data groupings based on clinical standards
6. ✅ Formulate answerable research questions about diabetes risk factors

---

## About the Dataset

**Dataset:** Pima Indians Diabetes Database  
**Source:** Originally from the National Institute of Diabetes and Digestive and Kidney Diseases  
**File:** `diabetes.csv`  
**Target Variable:** `Outcome` (whether the patient has diabetes: 1 = Yes, 0 = No)

### Clinical Context

Diabetes affects over 37 million Americans and is the 8th leading cause of death in the United States. Type 2 diabetes, which accounts for 90-95% of all diabetes cases, can often be prevented or delayed with lifestyle changes when risk factors are identified early.

This dataset contains diagnostic measurements from female patients of Pima Indian heritage, all at least 21 years old. The Pima Indians have one of the highest rates of diabetes in the world, making this population particularly important for understanding diabetes risk factors. Understanding these variables is crucial for:

- Early identification of high-risk patients
- Preventive care planning
- Resource allocation in healthcare settings
- Clinical decision support systems

---

## Getting Started

First, load the dataset and import your libraries:

```python
# Import libraries


# Load the dataset


# Display first few rows to confirm it loaded

```

---

## Part 1: The 10-Point Data Inspection (40 points)

Complete each inspection step and document your findings.

### Step 1: Shape (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How many rows (observations)? _______________
- How many columns (features)? _______________
- What does each row represent in clinical terms? _______________

---

### Step 2: Column Names (4 points)

**Your Code:**
```python

```

**Your Findings:**
- List all column names:

- Which columns might need further research to understand?

---

### Step 3: Data Types (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns are numeric?

- Which columns are categorical (object/string)?

- Are there any data types that seem incorrect?

---

### Step 4: First Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What do the actual values look like?

- Do you notice anything unusual or unexpected?

- Are there any values that look like they might be placeholders for missing data?

---

### Step 5: Last Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Does the data end cleanly?

- Are the last rows consistent with the first rows?

---

### Step 6: Memory Usage (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How much memory does the dataset use? _______________ KB
- Is this a "small" or "large" dataset by data science standards?

---

### Step 7: Missing Values (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have missing values (according to `.isnull()`)?

- What percentage of each column is missing?

- ⚠️ **IMPORTANT:** This dataset uses **zeros to encode missing values** for certain physiological measurements. Which columns have zeros that are biologically impossible? (Hint: Can a living person have a blood pressure of 0? A BMI of 0? Glucose of 0?)

---

### Step 8: Duplicates (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Are there any duplicate rows? _______________
- If there are duplicates, how many? _______________

---

### Step 9: Basic Statistics (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What is the age range in the dataset? _______________ to _______________
- What is the range of glucose levels? _______________ to _______________
- What is the range of BMI values? _______________ to _______________
- Do any min values of 0 represent biologically impossible measurements?

---

### Step 10: Unique Counts (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have very few unique values (likely categorical or binary)?

- Which columns have many unique values (likely continuous)?

- What does the `Outcome` column represent and how many unique values does it have?

---

## Part 2: Data Dictionary (20 points)

Complete the following data dictionary. For each column, you must:
1. **Research** the clinical meaning
2. **Identify** the feature type (Continuous, Discrete, Categorical-Nominal, Categorical-Ordinal, Binary, Identifier)
3. **Document** the valid values/range you observe
4. **Note** any issues or questions

| Column | Description | Feature Type | Valid Values/Range | Notes/Issues |
|--------|-------------|--------------|-------------------|--------------|
| `Pregnancies` | | | | |
| `Glucose` | | | | |
| `BloodPressure` | | | | |
| `SkinThickness` | | | | |
| `Insulin` | | | | |
| `BMI` | | | | |
| `DiabetesPedigreeFunction` | | | | |
| `Age` | | | | |
| `Outcome` | | | | |

### Clinical Research Questions for Version A

Answer these questions based on your research (you may need to use Google):

**1. What is a normal fasting glucose level? What level indicates pre-diabetes? What level indicates diabetes?**

Your answer:

---

**2. What is the Diabetes Pedigree Function? How does it attempt to capture genetic/hereditary risk?**

Your answer:

---

**3. Why is BMI (Body Mass Index) relevant to diabetes risk? What are the BMI categories (underweight, normal, overweight, obese)?**

Your answer:

---

**4. Why might the number of pregnancies be related to diabetes risk? (Hint: Research gestational diabetes)**

Your answer:

---

## Part 3: Data Validation (15 points)

### 3.1 Zero-Value Analysis (5 points)

A unique challenge in this dataset is that **zeros are used to encode missing values** for several columns where zero is biologically impossible.

Write code to count how many zeros exist in each column:

**Your Code:**
```python

```

**Your Findings:**

- Which columns have zeros that are biologically impossible?

- For each problematic column, what percentage of values are zeros?

- Why would the original data collectors use zeros instead of leaving these as empty/null values?

---

### 3.2 Glucose Validation (5 points)

Write code to examine glucose values. Check for zeros and look at the distribution.

**Your Code:**
```python

```

**Your Findings:**

- How many patients have a glucose value of 0?

- What would happen if you calculated the mean glucose without handling the zeros?

- What is the mean glucose when you exclude the zero values?

---

### 3.3 Blood Pressure Validation (5 points)

Write code to examine blood pressure values and identify problematic entries.

**Your Code:**
```python

```

**Your Findings:**

- How many patients have a blood pressure of 0?

- What is a normal diastolic blood pressure range?

- Are there any non-zero blood pressure values that seem clinically unlikely (too high or too low)?

---

## Part 4: Create Clinical Age Groups (10 points)

Create a new column called `age_group` that categorizes patients into clinically-meaningful groups.

### Version A: Life Stage Categories

Use these categories based on adult life stages and diabetes risk:

| Age Group | Range | Clinical Rationale |
|-----------|-------|-------------------|
| Young Adult | 21-29 | Baseline risk, early screening important |
| Adult | 30-39 | Risk begins to increase |
| Middle Age | 40-49 | Significant risk increase, regular screening recommended |
| Mature Adult | 50-59 | High risk population |
| Senior | 60+ | Highest risk, may have longer disease duration |

*Note: All patients in this dataset are at least 21 years old.*

### Your Code:

```python
# Create the age_group column
# You can use a custom function with .apply() OR pd.cut()
# Remember: if using pd.cut(), use include_lowest=True!


```

### Verify your groupings worked:

```python
# Show counts per age group

```

### Calculate diabetes rate by age group:

```python
# Calculate the percentage of patients who have diabetes (Outcome=1) in each age group

```

### Analysis Questions:

**1. How many patients are in each age group?**

Your answer:

---

**2. What is the diabetes rate (percentage with Outcome=1) for each age group?**

Your answer:

---

**3. At what life stage does diabetes prevalence appear to increase most dramatically? Does this match what you learned in your clinical research?**

Your answer:

---

## Part 5: Research Questions (15 points)

### 5.1 Write Three Answerable Questions (9 points)

Write three questions that THIS dataset can answer. Remember: the data can show relationships and patterns, but cannot prove causation.

**Your questions must explore these specific areas:**

1. **A question about glucose levels and diabetes outcome:**


---

2. **A question comparing patients by pregnancy history:**


---

3. **A question about the combination of BMI AND age:**


---

### 5.2 Identify One Question the Data CANNOT Answer (3 points)

Write one question about **diet, exercise, or medication** that this dataset cannot answer, and explain why.

**Question:**


**Why it cannot be answered with this data:**


---

### 5.3 Grouping Analysis (3 points)

Answer this question using a groupby analysis:

**"What is the average glucose level for patients with diabetes (Outcome=1) versus without diabetes (Outcome=0)?"**

(Note: You should exclude zero glucose values before calculating!)

**Your Code:**
```python

```

**Your Interpretation:**

What is the difference in average glucose between diabetic and non-diabetic patients? Does this make clinical sense?


---

## Part 6: Target Variable Analysis (Bonus - 5 points)

The `Outcome` column is our **target variable** - what we're trying to predict. Analyze its distribution.

**Your Code:**
```python
# Show the count and percentage of diabetic vs non-diabetic patients

```

### Bonus Questions:

**1. What percentage of patients in this dataset have diabetes?**

Your answer:

---

**2. Is this dataset balanced or imbalanced? (A balanced dataset has roughly equal classes)**

Your answer:

---

**3. Why does class imbalance matter for machine learning? (You may need to research this)**

Your answer:

---

**4. The Pima Indians have one of the highest rates of diabetes in the world (around 50% in some studies). How does this dataset's diabetes rate compare? What might this tell you about the patient selection criteria?**

Your answer:

---

## Submission Checklist

Before submitting, verify you have completed:

- [ ] **Part 1:** All 10 inspection steps with code AND written findings
- [ ] **Part 2:** Complete data dictionary with all 9 columns filled in
- [ ] **Part 2:** Answered all 4 clinical research questions
- [ ] **Part 3:** All 3 validation checks with code and answers
- [ ] **Part 4:** Created `age_group` column using the **Life Stage Categories**
- [ ] **Part 4:** Calculated diabetes rate by age group with interpretation
- [ ] **Part 5:** Three research questions (glucose, pregnancy, BMI+age)
- [ ] **Part 5:** One unanswerable question about diet/exercise/medication
- [ ] **Part 5:** Glucose by outcome groupby analysis
- [ ] **Bonus (Optional):** Target variable analysis

---

## Grading Rubric

| Component | Points | Requirements for Full Credit |
|-----------|--------|------------------------------|
| Part 1: 10-Point Inspection | 40 | All 10 steps complete with working code AND thoughtful written analysis |
| Part 2: Data Dictionary | 20 | All 9 columns documented with correct feature types and clinical research |
| Part 3: Data Validation | 15 | All validation checks complete with working code and insightful answers |
| Part 4: Age Groups | 10 | Working code that creates correct groups AND meaningful interpretation |
| Part 5: Research Questions | 15 | Three good questions in specified areas, one clear limitation, groupby analysis complete |
| **Bonus:** Target Analysis | +5 | Thoughtful analysis of class imbalance with real-world connection |
| **Total** | 100 (+5 bonus) | |

---

## Hints (Read Before You Get Stuck!)

### ⚠️ Common Pitfalls:

1. **Zeros as Missing Values**
   - Unlike most datasets, this one uses **0** to represent missing values for columns like `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, and `BMI`
   - The `.isnull()` method won't detect these!
   - You need to check for zeros manually in columns where 0 is biologically impossible

2. **Pregnancies column can legitimately be 0** - a woman who has never been pregnant has 0 pregnancies, this is valid data

3. **All patients are female and at least 21 years old** - this limits what generalizations you can make

4. **DiabetesPedigreeFunction** - this is a calculated score, not a raw measurement. Research what it represents.

### 💡 Pro Tips:

- Use `value_counts()` liberally to understand distributions
- Use `df[df['ColumnName'] == 0].shape[0]` to count zeros in a column
- When calculating statistics like mean, filter out zeros first for affected columns
- The `describe()` function is your friend - look at those min values!
- Remember that correlation ≠ causation

---

## Useful Resources

- **Original Dataset Source:** UCI Machine Learning Repository
- **Diabetes Information:** https://www.diabetes.org/
- **Blood Glucose Levels:** https://www.diabetes.org/healthy-living/medication-treatments/blood-glucose-testing-and-control
- **BMI Categories:** https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html
- **Pandas Documentation:** https://pandas.pydata.org/docs/

---

*Remember: "Every Column Tells a Story" - your job is to figure out what that story is!*

---

**Due Date:** [See Canvas]

**Submission:** Upload your completed Jupyter notebook (.ipynb) to Canvas
