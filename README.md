# FishClassificationWithSnoar

# Fish Classification Project

## Overview
This repository contains the code and data analysis for a fish classification project conducted as part of the STA2453 course. The goal of this project is to classify fish species (Lake Trout and Smallmouth Bass) based on their frequency response curves using supervised learning techniques. The dataset consists of sonar frequency response measurements and biological features collected from fish placed underwater.

## Dataset
The dataset, referred to as `fish_clean`, is derived from raw sonar readings and biological measurements of fish. Key details include:
- Two species: **Lake Trout (LT)** and **Smallmouth Bass (SMB)**
- **Biological Features**: Length, weight, girth, airbladder measurements, and sex.
- **Frequency Response Data**: Sonar frequency responses across multiple frequency bands.
- **Preprocessing Steps**: Missing value handling, PCA for dimensionality reduction, and selection of relevant biological and frequency features.

## Project Objectives
- Perform **Exploratory Data Analysis (EDA)** to understand frequency response patterns for each species.
- Evaluate the impact of **biological features** on classification accuracy.
- Use **Principal Component Analysis (PCA)** to identify key frequency features.
- Apply machine learning models via **SuperLearner** to classify species based on different feature sets.

## Data Preprocessing
- **Handling Missing Data**: Columns with excessive missing values are removed manually due to inconsistencies across species.
- **Feature Selection**: Biological and frequency response features are selected based on domain knowledge.
- **Dataset Variants for Modeling**:
  1. All biological features + All frequency
  2. Species-specific biological features
  3. PCA-selected frequency range + All biological features
  4. PCA-selected frequency range + species-specific biological features
  5. Frequency response only
  6. PCA-selected frequency range only

## Modeling Approach
- **SuperLearner Framework**: Combines multiple machine learning models to find the best classifier.
- **Base Learners**: 
  - Elastic Net (`SL.glmnet`)
  - Random Forest (`SL.randomForest`, `SL.ranger`)
  - XGBoost (`SL.xgboost`)
  - Neural Network (`SL.nnet`)

## Key Findings
- PCA alone does not effectively separate species due to overlapping frequency responses.
- The frequencies are correlated so Bonferroni correction cannot be applied

## Contributors
- **Phyllis Sun** (Fengyi Sun) - University of Toronto

## Acknowledgments
Special thanks to the STA2453 professor for guidance and dataset provision.
