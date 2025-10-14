---
title: "Netflix Data Wrangling & Cleaning"
categories: [Python, Data Cleaning]
tags: [Python, Pandas, Data Wrangling, Data Quality, Kaggle]
excerpt: "Comprehensive data cleaning and transformation of Netflix shows dataset, addressing data quality issues and preparing it for analysis."
---

## Project Overview
Executed a complete data wrangling pipeline on the Netflix shows dataset, demonstrating strong data cleaning skills and systematic approach to data quality improvement.

## Business Objectives
- Transform messy, inconsistent dataset into reliable analysis-ready data
- Address comprehensive data quality issues including missing values and inconsistencies
- Implement reproducible data cleaning pipeline
- Prepare dataset for exploratory analysis and business intelligence

## Dataset Source
- **Kaggle Dataset:** https://www.kaggle.com/datasets/shivamb/netflix-shows
- **Records:** 8,807 rows × 12 columns
- **Scope:** Global Netflix content catalog

## Data Wrangling Pipeline

### 1. Data Collection & Inspection
**Initial Assessment:**
- Loaded dataset from CSV into Pandas DataFrame
- Comprehensive data profiling using `df.info()`, `df.shape`, `df.describe()`
- Missing value analysis with `df.isnull().sum()`
- Data type validation and unique value analysis

**Key Issues Identified:**
- Missing values in director, cast, country, date_added, rating, and duration columns
- Inconsistent data types (date_added as strings instead of datetime)
- Data contamination (duration values in rating column)
- Inconsistent spellings in country column
- Formatting inconsistencies across multiple columns

### 2. Data Cleaning Process
**Standardization & Normalization:**
- Standardized all column formats and data types
- Normalized country column by removing whitespace and correcting spelling errors
- Cleaned rating column by removing duration entries
- Formatted date_added column to proper datetime format
- Handled missing values appropriately (replaced with 'N/A' where suitable)

### 3. Data Transformation
**Feature Engineering:**
- Created new 'year' column extracted from date_added
- Normalized all text columns to lowercase for consistency
- Split duration column into 'duration_value' and 'duration_unit' for better analysis
- Created 'main_genre' column for categorical analysis
- Alphabetically arranged genres by title for standardization

### 4. Data Validation
**Quality Assurance:**
- Verified no critical fields (title, type, release_year) contained missing values
- Confirmed elimination of duplicate records
- Validated correct data types across all columns
- Dropped redundant 'duration' column after feature extraction
- Ensured logical consistency and data integrity

### 5. Data Export
- Saved cleaned and transformed dataset to CSV format
- Ensured data is analysis-ready for visualization and machine learning

## Technical Implementation

### Tools & Technologies
- **Python** - Primary programming language
- **Pandas** - Data manipulation and cleaning
- **NumPy** - Numerical operations support
- **Kaggle** - Platform for dataset and code hosting

## Key Functions & Methods
### Data Inspection
df.info(), df.shape, df.isnull().sum(), df.nunique()
df.duplicated().sum(), df.describe()

### Data Cleaning
df.fillna(), df.astype(), str.strip(), str.lower()

### Data Transformation
pd.to_datetime(), str.split(), str.extract()

## Business Impact
Enabled reliable analysis of Netflix content trends

Provided clean dataset for business intelligence dashboards

Established reproducible data cleaning framework

Improved data quality for decision-making processes

[View Complete Implementation on Kaggle](https://www.kaggle.com/code/andreawacug/andrea-wacu-cs-da02-25024)
