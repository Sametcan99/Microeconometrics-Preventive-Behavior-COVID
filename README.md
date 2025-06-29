# Microeconometric Analysis of Preventive Behavior (Python)

This repository contains the Python code and analysis for a microeconometric project investigating the causal impact of retirement status on preventive health behaviors during the COVID-19 pandemic. As part of a group, our work involved applying robust econometric methods to address endogeneity and ensure reliable causal inference from observational data.

📝 Project Overview
This academic project, developed in a group setting, delves into micro-level survey data from Europe to understand the factors influencing individual preventive behaviors during a public health crisis. It showcases the application of advanced econometric techniques to establish causality in a complex social science context.

🎯 Objectives
To estimate the impact of retirement status on individuals' likelihood of maintaining social distance.

To identify and address potential endogeneity of the 'retirement' variable through Instrumental Variable (IV) methods.

To perform heteroskedasticity testing and implement robust standard errors for valid statistical inference.

To analyze the influence of various socioeconomic and demographic factors (age, gender, education, country) on preventive behavior.

To compare and interpret the results from OLS and IV estimations to highlight the importance of econometric rigor.

📊 Dataset
The project utilizes a cross-sectional dataset (group1.csv) of older individuals in Europe, collected during the first wave of the COVID-19 pandemic. Key variables include:

alwaysdis: Binary (1/0) for always keeping distance outside home (dependent variable).

retired: Binary (1/0) for retirement status (endogenous regressor).

eligibleSR: Binary (1/0) for eligibility for old age pension (instrumental variable).

age, age2: Individual's age and its squared value.

female: Binary (1/0) for gender.

couple: Binary (1/0) for having a partner.

iscedX: Dummy variables for different education levels.

country dummies: For country of residence.

⚙️ Methodology & Workflow
Our group's structured econometric approach involved the following key steps, implemented in Python:

Data Loading & Initial Exploration:

Ingested group1.csv into a pandas DataFrame.

Performed initial data shape and df.head() inspection.

Checked for missing values (df.isnull().sum()) and basic descriptive statistics (df.describe()).

OLS Regression (Baseline & Robust):

Estimated an initial Ordinary Least Squares (OLS) model (statsmodels.api.OLS) to establish baseline relationships.

Heteroskedasticity Testing: Conducted formal Breusch-Pagan and White tests (statsmodels.stats.diagnostic.het_breuschpagan, het_white) on OLS residuals.

Implemented OLS with robust (HC0) standard errors (model.fit(cov_type='HC0')) after confirming heteroskedasticity, ensuring valid statistical inference.

Endogeneity Diagnosis:

Theoretically discussed reasons for endogeneity of 'retired' (e.g., omitted variables like health, reverse causality).

(Optional, but good to mention if explored) Performed Wu-Hausman test of exogeneity (linearmodels.iv.wu_hausman) as a statistical test.

Instrumental Variable (IV) Regression:

Applied Two-Stage Least Squares (2SLS) and Generalized Method of Moments (GMM) estimations using the linearmodels.iv library (IV2SLS, IVGMM).

Instrument Selection: Utilized eligibleSR (pension eligibility) as a strategic instrument for 'retired', arguing for its relevance and exogeneity.

First-Stage Analysis: Explicitly examined the first-stage regression results to confirm instrument relevance (e.g., checking the F-statistic of the instrument's coefficient).

Results Comparison & Interpretation:

Compared coefficients and standard errors across OLS and IV (2SLS/GMM) models.

Interpreted the causal effects of retirement and other covariates, highlighting how IV methods yielded more consistent (often larger) estimates by addressing endogeneity bias.

🛠️ Technologies & Tools
Python: Primary programming language.

Pandas: For data loading, manipulation, and cleaning.

NumPy: For numerical operations.

Statsmodels: For OLS regression, descriptive statistics, and heteroskedasticity tests.

Patsy: Used with dmatrices for flexible creation of design matrices with categorical variables.

Linearmodels: Essential for implementing Instrumental Variable regressions (IV2SLS, IVGMM) and robust covariance estimation.

Matplotlib: (If visualizations were part of the descriptive analysis, e.g., for country-specific averages).

🏃 How to Run the Project
Clone the repository:

git clone https://github.com/Sametcan99/Microeconometrics-Preventive-Behavior-COVID.git

Navigate to the project directory:

cd Microeconometrics-Preventive-Behavior-COVID

Ensure you have the dataset: Place the group1.csv file in the same directory as the Jupyter Notebook (Econometric Analysis Homework Group 1.ipynb).

Install necessary libraries:

pip install numpy pandas statsmodels patsy linearmodels matplotlib

Open and run the Jupyter Notebook:

jupyter notebook "Econometric Analysis Homework Group 1.ipynb"

Execute the cells sequentially to replicate the analysis and results.

📈 Key Findings & Insights
Confirmed the presence of heteroskedasticity, underscoring the importance of robust standard errors in microeconometric analysis.

Demonstrated that retirement status likely has a stronger positive causal effect on preventive behavior when endogeneity is addressed via IV.

Showcased the ability to diagnose and resolve complex econometric challenges (like endogeneity and heteroskedasticity) in real-world observational data.

Provided insights into how various socioeconomic and demographic factors influence health-related behaviors during a crisis.

📞 Contact
Feel free to connect with me for any questions or collaborations:

LinkedIn: https://www.linkedin.com/in/sametcan-kandemirt/

Email: kandemirsametcan99@gmail.com
