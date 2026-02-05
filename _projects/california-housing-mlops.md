---
title: "California Housing Price Prediction with MLOps Pipeline"
date: 2025-11-14
categories: [Machine Learning, MLOps, Python]
tags: [Regression, Scikit-learn, MLOps, Pipeline, GridSearchCV, Hyperparameter Tuning, Model Serialization]
excerpt: "End-to-end MLOps pipeline implementing reproducible workflows for California housing price prediction, achieving 60% variance explanation with optimized KNN regression."
---

## Project Overview
Designed and implemented a complete MLOps pipeline to predict median house prices in California using the California Housing dataset. This project demonstrates production-ready machine learning practices including pipeline construction, hyperparameter optimization, cross-validation, and model serialization. The workflow ensures reproducibility and prevents data leakage while systematically identifying the optimal model configuration.

## Business Objectives
- Develop a reliable regression model for California housing price prediction
- Implement MLOps best practices for scalable and reproducible machine learning
- Create a deployable model pipeline suitable for real-world applications
- Enable model reuse and easy updates through proper serialization

## Technical Implementation

### Dataset & Features
- **Dataset**: California Housing dataset (20,640 samples, 8 features, continuous target)
- **Target**: MedHouseVal (median house value in $100,000 units)
- **Features**: MedInc (median income), HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude
- **Data Quality**: No missing values or duplicates detected

### MLOps Pipeline Components
1. **Data Exploration**: Comprehensive analysis of feature distributions and relationships
2. **Data Splitting**: 80-20 train-test split with random state for reproducibility
3. **Preprocessing Pipeline**: StandardScaler integrated via ColumnTransformer
4. **Model Integration**: KNeighborsRegressor embedded in scikit-learn pipeline
5. **Hyperparameter Tuning**: GridSearchCV with 5-fold cross-validation
6. **Model Persistence**: Pickle serialization for deployment and reuse

### Methodology
1. **Data Loading & Validation**: Complete EDA with missing value and duplicate analysis
2. **Pipeline Construction**: Integrated preprocessing and modeling steps to prevent data leakage
3. **Hyperparameter Optimization**: Systematic search over neighbor count, weighting, and distance metrics
4. **Model Evaluation**: R² score and RMSE metrics with cross-validation
5. **Model Serialization**: Production-ready model saving for deployment

## Model Performance Results

### Hyperparameter Search Results
- **Best Model Configuration**:
  - Number of Neighbors: 9
  - Weighting Method: Distance-based
  - Distance Metric: Manhattan (p=1)
- **Cross-Validation R² Score**: 0.6034
- **Test Set R² Score**: 0.6034
- **Test RMSE**: 0.693 (in $100,000 units)

### Performance Interpretation
- **Model Accuracy**: Explains approximately 60% of variance in housing prices
- **Consistency**: Cross-validation and test scores show minimal overfitting
- **Error Margin**: Average prediction error of approximately $69,300

## Feature Analysis & Insights

### Key Predictive Features
1. **Median Income (MedInc)** - Strongest predictor of house prices
2. **House Age** - Moderate correlation with property value
3. **Location Coordinates** - Geographical patterns in pricing
4. **Average Occupancy** - Density-related pricing effects

### Pipeline Benefits
- **Data Leakage Prevention**: Integrated preprocessing ensures no test data contamination
- **Reproducibility**: Fixed random states and serialized pipelines guarantee consistent results
- **Scalability**: Pipeline structure supports easy model updates and feature additions

## Technical Implementation Details

### MLOps Architecture
- **ColumnTransformer**: Unifies preprocessing steps for all numerical features
- **Pipeline Integration**: Combines scaling and modeling in single workflow
- **GridSearchCV**: Exhaustive hyperparameter search with cross-validation
- **Model Serialization**: Pickle format for easy deployment

### Hyperparameter Grid
- **n_neighbors**: [3, 5, 7, 9] - Varying neighborhood sizes
- **weights**: ['uniform', 'distance'] - Voting and distance weighting
- **p**: [1, 2] - Manhattan and Euclidean distance metrics

### Evaluation Framework
- **Primary Metric**: R² score for variance explanation
- **Error Metrics**: RMSE for absolute error interpretation
- **Validation Strategy**: 5-fold cross-validation for robust performance estimates
- **Comparison**: Training vs. test performance for overfitting detection

## Key Findings & Business Impact

### Algorithm Performance
- **KNN Strengths**: Non-parametric nature handles non-linear relationships well
- **Distance Sensitivity**: Manhattan distance outperformed Euclidean for this dataset
- **Weighting Impact**: Distance-based weighting improved model accuracy

### MLOps Advantages
- **Production Readiness**: Pipeline structure enables easy deployment
- **Maintainability**: Clear separation of preprocessing and modeling steps
- **Experiment Tracking**: GridSearchCV records all tested configurations
- **Model Versioning**: Serialization supports multiple model versions

## Tools & Technologies
- **Python** with Scikit-learn for machine learning implementation
- **Pandas & NumPy** for data manipulation and numerical operations
- **GridSearchCV** for systematic hyperparameter optimization
- **Pickle** for model serialization and persistence
- **Google Colab** for development and execution environment

## Skills Demonstrated
- End-to-end MLOps pipeline development
- Hyperparameter tuning with cross-validation
- Pipeline construction for reproducible workflows
- Model evaluation and performance interpretation
- Production model serialization and deployment
- Data preprocessing and feature engineering

## Business Applications
- **Real Estate Valuation**: Automated price estimation for California properties
- **Mortgage Lending**: Risk assessment and property valuation support
- **Urban Planning**: Understanding housing price drivers and patterns
- **Investment Analysis**: Market trend identification and prediction

## Limitations & Future Enhancements
- **Model Complexity**: KNN can be computationally expensive for large datasets
- **Feature Engineering**: Additional features could improve predictive power
- **Algorithm Diversity**: Testing other regression algorithms (GBM, Neural Networks)
- **Hyperparameter Expansion**: Broader search space for optimization
- **Deployment Interface**: Web application or API for real-time predictions

## Code Repository
[View Complete Implementation on Google Colab](https://colab.research.google.com/drive/1OoROLF4NFhyJRiqC7ZtKvz2h1wkJCoQi)

---

*This MLOps project demonstrates professional machine learning practices with a focus on reproducibility, scalability, and deployment readiness, showcasing the ability to build production-grade predictive models with proper validation and persistence.*
