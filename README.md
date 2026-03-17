# Labor Force Survey 2016: Employment Status Classification

**Course Project – Data Science / Machine Learning**

This repository contains a machine learning analysis of the **Philippine Labor Force Survey (LFS) April 2016 Public Use File**.
The project focuses on predicting an individual's **employment status** using demographic, education, and labor market variables.

The analysis includes:

* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature preparation
* Dimensionality reduction
* Supervised machine learning classification
* Model evaluation and visualization

---

# Project Overview

The objective of this project is to build a **classification model** capable of predicting an individual's **employment status** using survey microdata.

The target variable is:

**`PUFNEWEMPSTAT` — New Employment Criteria**

| Class | Label                  | Meaning                                                    |
| ----- | ---------------------- | ---------------------------------------------------------- |
| 1     | Employed               | Engaged in any economic activity during the reference week |
| 2     | Unemployed             | Not working but actively looking and available for work    |
| 3     | Not in the Labor Force | Not employed and not seeking work                          |

Predicting employment status can provide insights into **labor market structure, demographic patterns, and employment dynamics** in the Philippines.

---

# Dataset

## Source

Philippine Statistics Authority (PSA)
Labor Force Survey (LFS) – April 2016 Public Use File

The Labor Force Survey is a **nationwide quarterly household survey** that collects data on:

* employment
* unemployment
* labor force participation
* demographic characteristics

The survey is conducted using **face-to-face household interviews**.

---

## Dataset Characteristics

| Property            | Value                 |
| ------------------- | --------------------- |
| File format         | CSV                   |
| Observations        | 180,862 individuals   |
| Features            | 50 variables          |
| Unit of observation | Individual respondent |
| Geographic scope    | Philippines           |

The dataset contains **micro-level socio-economic data** describing individuals within sampled households.

---

## Data Access

Due to GitHub file size limitations, the dataset is **not included in this repository**.

To reproduce the analysis:

1. Download the dataset from the **Philippine Statistics Authority**.
2. Place the dataset in:

```
data/raw/LFS_PUF_April_2016.csv
```

---

# Feature Groups

The dataset includes variables across multiple categories.

## Demographic and Geographic Variables

Examples include:

* Region
* Province
* Urban/Rural classification
* Household size
* Relationship to household head
* Sex
* Age
* Marital status
* Education level

These variables capture **population characteristics** relevant to labor participation.

---

## Labor Force Participation

Variables describing employment characteristics:

* Whether the individual worked last week
* Occupation
* Industry
* Nature of employment
* Working hours
* Class of worker
* Payment structure
* Wage information

These provide **core indicators of labor market engagement**.

---

## Multiple Jobs and Workload

Additional labor information:

* Number of jobs
* Total working hours
* Reasons for limited work hours

These variables capture **underemployment and workload dynamics**.

---

## Job Search and Availability

Variables describing unemployment behavior:

* Job search activity
* Job search method
* Duration of job search
* Availability for work
* Willingness to accept employment

These are essential for **distinguishing unemployed individuals from those outside the labor force**.

---

## Previous Work Experience

Historical employment variables:

* Previous occupation
* Previous industry
* Recent work experience

These features capture **employment history and skill alignment**.

---

# Data Cleaning and Preprocessing

Several preprocessing steps were applied before modeling.

## Handling Missing Values

Survey datasets often contain **structured missing values** because certain questions are only asked depending on previous responses.

Missing fields were standardized to `NaN` to ensure consistent processing.

---

## Removing Invalid Observations

Rows with missing values in the **target variable (`PUFNEWEMPSTAT`)** were removed because supervised learning requires labeled observations.

---

## Educational Attainment Cleaning

Some entries in `PUFC07_GRADE` did not correspond to valid education codes defined by the PSA data dictionary.

These invalid codes were removed to maintain data integrity.

---

## Duplicate Removal

Duplicate records were identified and removed where applicable.

---

## Filtering Relevant Population

Survey logic sometimes includes respondents outside the labor force definition.

Filtering steps ensured the dataset reflects **valid respondents for employment classification**.

---

# Exploratory Data Analysis

EDA was conducted to understand the relationships between variables and employment status.

Key visualizations include:

* Employment status distribution
* Age distribution by employment category
* Education level vs employment status
* Gender differences in employment
* Marital status and labor force participation
* Urban vs rural employment differences
* Hours worked distribution
* Job search behavior among unemployed respondents
* Correlation matrix of numerical variables

These visualizations help reveal **patterns in labor participation and demographic influences**.

---

# Feature Engineering

Before modeling, relevant variables were selected and transformed.

Key steps included:

* Encoding categorical variables
* Handling missing values
* Standardizing numeric variables
* Selecting predictive features

These steps prepare the data for **machine learning algorithms**.

---

# Dimensionality Reduction

Principal Component Analysis (PCA) was applied to reduce dimensionality and visualize class separation.

PCA helps:

* reduce multicollinearity
* compress high-dimensional features
* visualize clusters between employment classes

A 2D PCA projection was used to visualize the separation between:

* employed
* unemployed
* not in the labor force

---

# Machine Learning Model

A classification model was trained to predict employment status.

The workflow included:

1. Splitting the dataset into training and testing sets
2. Training a classification model
3. Evaluating performance using standard metrics

The objective is to determine whether **demographic and labor characteristics can accurately predict employment status**.

---

# Model Evaluation

Model performance was evaluated using:

* accuracy
* confusion matrix
* classification metrics

These metrics assess the model's ability to distinguish between employment categories.

---

# Project Structure

```
lfs2016-labor-market-analysis
│
├── data
│   ├── raw
│   └── metadata
│
├── notebooks
│   └── labor_force_survey_analysis.ipynb
│
├── figures
│   ├── employment_status_distribution.png
│   ├── age_distribution_by_employment.png
│   ├── education_vs_employment.png
│   ├── employment_by_gender.png
│   ├── employment_by_marital_status.png
│   ├── urban_vs_rural_employment.png
│   ├── hours_worked_distribution.png
│   ├── job_search_activity.png
│   ├── correlation_matrix.png
│   └── pca_projection.png
│
├── requirements.txt
└── README.md
```

---

# Installation

Clone the repository:

```
git clone https://github.com/yourusername/lfs2016-labor-market-analysis.git
```

Install dependencies:

```
pip install -r requirements.txt
```

Run the notebook:

```
jupyter notebook
```

Open:

```
notebooks/labor_force_survey_analysis.ipynb
```

---

# Tools and Libraries

The analysis was conducted using:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

These tools support **data processing, visualization, and machine learning modeling**.

---

# Academic Context

This project was completed as part of a **data science coursework requirement**.

The objective was to demonstrate:

* data preprocessing
* exploratory analysis
* statistical reasoning
* machine learning model implementation

using real-world survey microdata.

---

# Contributors

This project was developed collaboratively by:

* Jonalaine Aporado
* Dustin Daniel Jamias
* Vince Jefferson Tadeo

---

# Disclaimer

The dataset used in this project originates from the **Philippine Statistics Authority**.
All analysis and interpretations presented in this repository are solely for **academic and educational purposes**.

---
