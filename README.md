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
[Analyis_Scripts](Analysis_Scripts) | data analysis scripts
[Data](Data) | contains the raw acoustic data and Echoview processing scripts
[ExploratoryAnalysis](ExploratoryAnalysis) | contains code to explore and filter the data
[ExploratoryAnalysis/FishTrack-EDA-Tool](ExploratoryAnalysis/FishTrack-EDA-Tool) | home folder for shiny app
[ProcessedData](ProcessedData) | contains data that has been generated from data in *Data*
[NonPingData](NonPingData) | contains fish bio data
[ExportedFigures](ExportedFigures) | Figures generated from analysis scripts
WritingSections | Report writing sections

## Usage
- Download all datasets 
- Run ExploratoryDataAnalysis.Rmd first to get fish_clean and freq_clean that will be used in the modeling stage
- Run Model.Rmd
  
## Contributors
- **Phyllis Sun** (Fengyi Sun) - University of Toronto

## Acknowledgments
Special thanks to the STA2453 professor for guidance and dataset provision.
