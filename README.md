# Interaction-Based Ligand Design for Targeted Drug Discovery

This project leverages machine learning techniques to predict the inhibitory concentration (IC50) values of ligands, which are key to evaluating the bioactivity of potential drug candidates. Using the ChEMBL database for data collection and a Random Forest Regressor model, this project aims to streamline the drug discovery process by accurately predicting ligand bioactivity. The project also includes a user-friendly Streamlit web application that allows for easy prediction of ligand bioactivity.


![Image Description](app)

## Project Overview

The goal of this project is to predict the bioactivity of ligands using machine learning models, focusing on the IC50 and pIC50 values, which are used to measure the effectiveness of a compound in inhibiting a target protein. The Random Forest Regressor is used for making predictions based on molecular descriptors calculated from the ligand structures.

### Key Features:
- **Data Collection**: Data sourced from the ChEMBL database, which includes ligand structures (SMILES, SDF files), target protein structures (PDB files, sequence data), and bioactivity data (IC50, pIC50).
- **Descriptor Calculation**: Calculation of molecular descriptors using Lipinski’s Rule of Five and PaDEL descriptor.
- **Machine Learning Model**: Training a Random Forest Regressor to predict pIC50 values from the calculated descriptors.
- **Web Application**: A Streamlit app that allows users to easily input ligand data and get predictions on bioactivity.

## Workflow Steps

### 1. Data Collection
Data is collected from the **ChEMBL** database, including:
- Ligand structures (SMILES and SDF files)
- Target protein structures (PDB files, sequence data)
- Bioactivity data (IC50, pIC50 values)

### 2. Data Preprocessing
- **Cleaning**: Remove duplicates and irrelevant entries.
- **Normalization**: Scale the data to maintain consistency.
- **Handling Missing Values**: Use imputation methods to fill gaps in the data.

### 3. Descriptor Calculation
- **Lipinski's Rule of Five**: Key descriptors such as Molecular Weight (MW), LogP, NumHDonors, and NumHAcceptors are calculated to assess drug-like properties.
- **PaDEL Descriptors**: Additional molecular descriptors and fingerprints are calculated for further analysis.

### 4. Exploratory Data Analysis (EDA)
- Perform distribution analysis, identify outliers, and visualize data using histograms, scatter plots, and Kernel Density Estimate (KDE) plots.

### 5. Bioactivity Classification
- Classify compounds based on their IC50 values:
  - **Active**: IC50 < 1000 nM
  - **Inactive**: IC50 > 10,000 nM
  - **Intermediate**: IC50 between 1000 nM and 10,000 nM

### 6. Model Building
- **Random Forest Regressor** is trained to predict pIC50 values based on molecular descriptors. The data is split into training (80%) and testing (20%) sets for model validation.

### 7. Model Evaluation
- Evaluate the model using metrics such as **Mean Squared Error (MSE)** and **R²**.
- Visualize results with scatter plots comparing experimental vs predicted pIC50 values.

### 8. App Development Using Streamlit
- **Streamlit App**: A user-friendly web application built using Streamlit, where users can input ligand data and receive predictions on bioactivity. The app allows for easy and interactive use of the trained model.
- **Features**:
  - Input fields for entering ligand data (e.g., SMILES notation).
  - Real-time prediction of pIC50 values using the trained Random Forest model.

### 9. Results
- **R² Value**: The Random Forest model achieved an R² value of **0.82**, indicating good predictive power.
- **Mean Squared Error (MSE)**: The model demonstrated a **low MSE**, suggesting accurate predictions for pIC50 values.
- **Scatter Plot**: A scatter plot comparing experimental vs predicted pIC50 values showed a strong correlation, confirming the model's accuracy. The points were closely aligned along the diagonal line, indicating minimal discrepancy between predicted and actual values.

---
