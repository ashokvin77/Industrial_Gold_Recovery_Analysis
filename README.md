# Gold Recovery Prediction

## Overview

This project focuses on developing a machine learning model for Zyfra, a company specializing in solutions for the heavy industry sector. The goal is to estimate the amount of gold recovered from a gold mine to enhance gold yield by avoiding unprofitable parameter settings. The project involves analyzing data related to the gold extraction and purification process.

The project workflow includes:

- Preparing and cleaning the data
- Performing exploratory data analysis
- Training and evaluating machine learning models

## Objectives

- Inspect and validate the correctness of gold recovery calculations in the dataset
- Analyze changes in metal concentration (Au, Ag, Pb) across purification stages
- Analyze metal concentration trends across purification stages
- Compare particle size distributions between training and test datasets
- Develop a machine learning model to predict gold recovery efficiency
- Evaluate multiple models using cross-validation to select the best performer
- Calculate the final sMAPE metric to assess model accuracy

## Data Description

The project uses three datasets:

- `gold_recovery_train.csv`: training data with features and targets
- `gold_recovery_test.csv`: test data with only features (no targets)
- `gold_recovery_full.csv`: full dataset containing raw values
Data is indexed by date and time of acquisition, and parameters close in time are often similar. Some parameters are unavailable in the test set as they were measured or calculated later. The raw data requires preprocessing to ensure correctness.

## Purification Flowchart

The diagram below illustrates the overall flow of gold purification.
![Purification Process](Figures/purification_flowchart.png)

## Key Visualizations

### 1. Gold (Au) Concentration Across Purification Stages

This plot shows how gold concentration steadily increases from the input feed to the final concentrate.

![Gold Concentration](Figures/Au_concentration_across_purification_stages.png)

---

### 2. Silver (Ag) Concentration Across Purification Stages

This plot demonstrates how silver is successfully removed through the purification process.

![Silver Concentration](Figures/Ag_concentration_across_purification_stages.png)

---

### 3. Feed Particle Size Distribution

This plot compares the particle size distribution between the training and test datasets.

![Particle Size Distribution](Figures/Feed_particle_size_distribution.png)


## Key Insights

- Gold concentration increases consistently across purification stages, peaking at the final stage
- Silver concentration decreases with each stage, indicating effective impurity reduction
- Lead concentration shows no consistent pattern beyond the primary stage
- Particle size distributions in the test set are representative of the training set, ensuring valid   model evaluation
- Rows with zero total concentrations were removed as they are unrealistic in ore processing
- Random Forest Regression (sMAPE: 7.08) outperformed Linear Regression and Decision Trees, making it  the best model for predicting gold recovery efficiency


## Tools and Technologies

- Python       3.12.10
- Pandas       2.2.3
- NumPy        2.2.5
- Matplotlib   3.10.1 
- Seaborn      0.13.12
- Scikit-learn 1.6.1

