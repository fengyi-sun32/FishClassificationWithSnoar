# Fish Classification Project

## Overview
This repository contains the code and data analysis for a fish classification project conducted as part of the STA2453 course. The goal of this project is to classify fish species (Lake Trout and Smallmouth Bass) based on their frequency response curves using supervised learning techniques. The dataset consists of sonar frequency response measurements and biological features collected from fish placed underwater.

## Dataset
The dataset, referred to as `fish_clean`, is derived from raw sonar readings and biological measurements of fish. Key details include:
- Two species: **Lake Trout (LT)** and **Smallmouth Bass (SMB)**
- **Biological Features**: Length, weight, girth, air bladder measurements, and sex.
- **Frequency Response Data**: Sonar frequency responses across multiple frequency bands.
- **Preprocessing Steps**: Missing value handling, PCA for dimensionality reduction, and selection of relevant biological and frequency features.

## Folder Structure
Folder | Description
---------- | --------------------------------------------------
[AnalyisScripts](AnalysisScripts) | data analysis scripts
[Data](Data) | contains the raw acoustic data and Echoview processing scripts
[ExploratoryAnalysis](ExploratoryAnalysis) | contains code to explore and filter the data
[ExploratoryAnalysis/FishTrack-EDA-Tool](ExploratoryAnalysis/FishTrack-EDA-Tool) | home folder for shiny app
[ProcessedData](ProcessedData) | contains data that has been generated from data in *Data*
[NonPingData](NonPingData) | contains fish bio data
[ExportedFigures](ExportedFigures) | Figures generated from analysis scripts
[Report](Report) | Report writing sections, including result table

## R Markdown Files

File | Purpose
------|--------
`ExploratoryDataAnalysis.Rmd` | Cleans data, explores frequency patterns, performs PCA  
`Model.Rmd` | Runs SuperLearner with multiple dataset variations

## Usage Instructions

To replicate the workflow locally:

### 1. Set Up the Environment
- Clone the repository to your machine
- Open the `.Rproj` file in **RStudio**
- Make sure required folders (Blue Folder expect Report) and 2 Rmd.files are installed:
  - ExploratoryDataAnalysis.Rmd
  - Model.Rmd

### 2. Run Exploratory Analysis
- Open and **run `ExploratoryDataAnalysis.Rmd`**
- This script will:
  - Clean the data
  - Create the cleaned datasets: `fish_clean` and `freq_clean`
  - Generate multiple processed dataset variants for modeling

### 3. Run Modeling
- Open and **run `Model.Rmd`**
- This script will:
  - Train models on multiple dataset variants
  - Use **SuperLearner** with **5-fold cross-validation**
  - Optimize ensemble weights based on **AUC**
  - Evaluate performance using:
    - **Balanced Accuracy**
    - **AUC-ROC**
    - **F1 Score**
    - **Confusion Matrix**

>️ **Note**: Running all SuperLearner variants may take time  
> To save time, run only the **final selected data variant and selected model(s)**  
> Best performance came from **PCA-reduced frequencies + species-specific biological features**

---

## Project Summary

The goal of this project is to classify fish species using non-invasive sonar techniques. Six dataset variants were created by combining:

- Raw and PCA-reduced frequency features
- Species-specific and full biological feature sets

**SuperLearner** was used to ensemble five models:

- `SL.glmnet`
- `SL.randomForest`
- `SL.xgboost`
- `SL.nnet`
- `SL.ranger`

### Best Result:
- **Dataset**: PCA-reduced frequencies + species-specific biological features  
- **Balanced Accuracy**: ~100%  
- **Evaluation Metrics**: Balanced Accuracy, AUC-ROC, F1 Score, Confusion Matrix

---

## Contributors
- **Phyllis Sun** (Fengyi Sun) - University of Toronto

## Acknowledgments
Special thanks to the STA2453 professor Dr. Vianey Leos Barajas for guidance and dataset provision.
