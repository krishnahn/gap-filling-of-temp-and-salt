# gap-filling-of-temp-and-salt
A PyTorch-based pipeline for filling missing values in oceanographic time series using a 3-layer bidirectional LSTM with enhanced feature engineering. Includes automatic gap detection, model-based imputation, accuracy reports, and clear visualisations. Perfect for scientific data cleaning.

<img width="1191" height="790" alt="image" src="https://github.com/user-attachments/assets/7fa0a7ed-df08-429c-850f-d9a5962d16c1" />

# LSTM Gap Filling for Oceanographic Time Series Data
This repository contains a PyTorch-based solution for imputing missing values in multi-variate time series data (specifically, oceanographic datasets) using an enhanced 3-layer bidirectional LSTM model and rich feature engineering.


# Features: 

Automatic missing value detection and imputation for each column

# Enhanced feature engineering:

Temporal encoding (hour, day-of-year)

 -->Rolling statistics (mean, std)
 
 -->Lag and difference features
 
 -->Exponential moving averages
 
-->Physical gradients (temperature and salinity profiles)

Multiple visualisation utilities: Analyse gap filling and compare before/after filling with plots and heatmaps

Accuracy evaluation: Reports fill rates and imputation accuracy

# Installation: 

Clone this repository

Install the required packages:

bash

"pip install pandas numpy matplotlib scikit-learn torch"
Prepare your data:

Ensure your Excel file matches the expected format.

Update the path in your script to point to your data location.

Usage
Main Imputation Script

The primary script performs:

Data loading

Feature engineering

Model training and gap filling for each target column with missing data

Saving the filled dataset to Excel

Comprehensive visualizations

# Running the Code:

Place your script in the repository directory and ensure you adjust paths as necessary.

python
# Example (adjust path as needed):
df = pd.read_excel(r"path_to_your_data/TS_Ssp.xlsx",
                   sheet_name='Actuals', usecols='A,E:M,Q:Y')
# Then run:

bash
"python your_script.py"
The output will include:

Console logs of process details, fill rates, and model accuracy

A filled Excel file: enhanced_lstm_oceanographic_filled.xlsx

Multiple pop-up plots for visual analysis

# Project Structure: 

EnhancedLSTMImputer: Handles all preprocessing, training, and gap filling.

TimeSeriesDataset: Custom PyTorch dataset for efficient minibatch creation.

EnhancedLSTM: Model class with three LSTM layers and dense layers.

# Visualisation Utilities:

visualize_gap_filling

visualize_before_after_comparison

plot_missing_data_heatmap

# Main Section:

Reports initial/final missing values

Runs imputation and accuracy assessment

Call visualisation utilities

# Visualization Samples:

<img width="1785" height="985" alt="image" src="https://github.com/user-attachments/assets/5ee4cefa-cf43-47aa-99a0-8bd876e6dec4" />

Before/after scatterplots to directly compare raw and imputed data.

<img width="1589" height="790" alt="image" src="https://github.com/user-attachments/assets/6ed11a6e-f528-49a6-9dc5-cd507ccc1ea6" />

Heatmaps showing the spatial distribution of missing values before and after filling.

# Customization:

Sequence Length & LSTM Units: Tune parameters like sequence_length and lstm_units according to your dataset's characteristics.

Features: Add/remove derived features in the create_enhanced_features function to suit your domain specifics.


# Tips:

GPU acceleration is supported if CUDA is available.

Progress messages and early stopping help ensure efficient training.

Data columns should have clear naming conventions (e.g., Temp_, Salt_) for gradient features to generate correctly.


# Output:

Filled Data: Saved as enhanced_lstm_oceanographic_filled.xlsx

Accuracy Report: Printed to the console, showing per-column fill rate and "imputation accuracy" (relative mean).

# License:

This project is provided for research and educational purposes.

Feel free to fork, extend, and adapt for your own time series imputation needs!
