---
title: "Titanic Survival Analysis"
date: "2025-10-04"
categories: [Python, EDA]
tags: [Python, Pandas, Matplotlib, Seaborn, Machine Learning, Data Analysis]
excerpt: "Comprehensive exploratory data analysis of the Titanic dataset to identify factors influencing passenger survival rates using Python and statistical visualization."
---

## Project Overview
Conducted an in-depth exploratory data analysis of the famous Titanic dataset to uncover patterns and relationships in passenger survival rates. This project demonstrates strong data analysis skills and the ability to derive meaningful insights from historical data through systematic EDA methodology.

## Business Objectives
- Identify key demographic and socio-economic factors influencing passenger survival rates
- Analyze patterns among survivors vs. non-survivors using statistical methods
- Create comprehensive visualizations to communicate findings effectively
- Build foundation for predictive modeling by identifying significant features

## Methodology & Approach

### Data Exploration & Cleaning
**Libraries Used:**
- Pandas - Data manipulation and analysis
- NumPy - Mathematical operations
- Matplotlib - Static visualizations
- Seaborn - Advanced statistical visualizations

**Initial Data Discovery:**
- Dataset: 891 rows × 12 columns
- Identified missing values in "Age", "Cabin", and "Embarked" columns
- Detected right-skewed distributions in "Age" and "Fare" columns
- No duplicate records found

**Data Cleaning Steps:**
- Filled missing "Age" values with median (due to right skew)
- Filled missing "Embarked" values with mode (categorical data)
- Dropped "Cabin" column (excessive missing values)
- Removed "PassengerId" and "Name" columns (non-predictive features)

## Analytical Approach

### Univariate Analysis
**Numerical Variables:**
- Histograms with KDE plots for distribution analysis
- Boxplots for outlier detection and distribution visualization

**Categorical Variables:**
- Count plots for frequency analysis
- Pie charts for proportional representation

**Key Findings:**
- Majority of passengers were young adults (20-30 years)
- Right-skewed age distribution with older passenger outliers
- 61% non-survival rate overall
- Male passengers dominated the dataset (65%)
- Most passengers traveled in 3rd class

### Bivariate Analysis
**Categorical-Categorical Analysis:**
- Grouped bar plots for Survival vs. Gender
- Strong relationship: Female passengers had significantly higher survival rates

**Numerical-Numerical Analysis:**
- Scatter plots with trendlines for Age vs. Fare
- No significant correlation between age and fare prices

**Numerical-Categorical Analysis:**
- Violin plots for Age distribution by Survival status
- Higher survival rates among children and younger passengers

### Multivariate Analysis
**Advanced Techniques:**
- Pair plots with survival hue for multi-variable relationships
- Correlation heatmaps with encoded categorical variables
- Cat plots for complex categorical relationships

**Key Insights:**
- Strong relationship between passenger class and survival rates
- Females in first class had highest survival probability
- Significant correlation between fare amount and survival likelihood

## Technical Implementation

### Outlier Detection & Handling
**Detection Methods:**
- Boxplot visualization for small to medium datasets
- Interquartile Range (IQR) calculation for skewed distributions

**Outlier Handling Strategies:**
- Log transformation applied to "Fare" column to address right skew
- Age grouping into bins for better analysis
- Created "Family" feature from SibSp and Parch columns
- Preserved valid outliers representing genuine data patterns

### Target Variable Analysis
**Survival Rate Analysis:**
- 61% non-survival rate indicating dataset imbalance
- Stacked bar plots for categorical variable relationships
- Kernel Density Estimation (KDE) plots for numerical variable distributions

**Key Predictive Factors Identified:**
1. **Gender**: Females had significantly higher survival rates
2. **Passenger Class**: First-class passengers had better survival chances
3. **Age**: Children and younger passengers prioritized
4. **Fare**: Higher fare correlated with better survival rates

## Key Findings & Business Impact

### Critical Insights
- **Survival was not random**: Strong socio-economic and demographic patterns emerged
- **"Women and children first" policy**: Clearly evident in the data
- **Class discrimination**: First-class passengers received priority in rescue efforts
- **Family size impact**: Moderate family sizes had better survival rates

### Predictive Feature Importance
**High Impact Features:**
- Sex (most significant predictor)
- Pclass (strong socio-economic indicator)
- Age (children prioritized)
- Fare (proxy for wealth and class)

**Supplementary Features:**
- Embarked location
- Family size
- SibSp/Parch relationships

## Technologies & Tools
- **Python 3.x** - Primary programming language
- **Pandas** - Data manipulation and cleaning
- **NumPy** - Numerical computations
- **Matplotlib** - Basic visualizations and plots
- **Seaborn** - Advanced statistical visualizations
- **Jupyter Notebook** - Interactive development environment

## Conclusion
This comprehensive EDA revealed that survival on the Titanic was strongly influenced by socio-economic status, gender, and age. The analysis provides a solid foundation for building predictive machine learning models, highlighting Sex, Pclass, and Age as the most powerful predictors. The methodology demonstrates rigorous data analysis skills and the ability to derive actionable insights from complex datasets.

## Code Repository
[View Complete Analysis on Kaggle](https://www.kaggle.com/code/andreawacug/andrea-wacu-eda)
