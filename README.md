# Project:   Automated Hemogram Analysis & Glycemic Classification

This project is a Python-based diagnostic tool designed to process longitudinal health data. It automates the classification of patient status—Normal, Prediabetic, or Diabetic—by analyzing fasting and post-prandial blood glucose levels across extensive datasets.

## Project Overview

The primary objective of this project is to bridge the gap between raw medical data and actionable clinical insights. By utilizing a backend script, the system evaluates monthly blood glucose logs to identify persistent patterns that meet established medical thresholds for diabetes screening.
This repository represents the culmination of a structured 5-task academic project, covering data ingestion, preprocessing, analytical logic, and reporting.

 ## Features

   Automated Data Cleaning: Removes non-essential columns (Date, Comments, Extra) and handles missing values to ensure analytical consistency.

   Dynamic Column Mapping: Uses string matching to identify "Before" and "After" meal columns regardless of minor naming variations.

   Multi-Marker Logic: Classifies patients based on the frequency of high readings (threshold of 3+ instances per day).

   Scalable Backend: Structured to eventually incorporate HbA1c, Fasting Blood Sugar (FBS), and Arterial Blood Gas (ABG) values like pH and HCO3-  

## Technologies Used

   Python 3.x

   Pandas: For data manipulation and CSV parsing.

   NumPy: For vectorized conditional logic and status selection.


## Dataset Structure

 The system processes a Data.csv file containing the following key parameters:

    Pre-prandial: "Before breakfast", "Before lunch", "Before dinner".

    Post-prandial: "2h after breakfast", "2h after lunch", "2h after dinner".

    Metadata: Optional fields for "Date", "Extra", and "Comment" 

## Clinical Logic

 The script applies the following thresholds for classification:

  Status	Fasting/Before Meal Threshold	Post-Prandial/After Meal Threshold

    Diabetic	> 126 mg/dL	> 200 mg/dL

    Prediabetic	> 99 mg/dL	> 140 mg/dL

    Normal	<= 99 mg/dL	<= 140 mg/dL

A "Diabetic" or "Prediabetic" status is triggered if 3 or more readings in a single day exceed these thresholds.


## 💻 Usage

  1.Ensure Data.csv is in the root directory.

  2.Install dependencies:
    pip install pandas numpy

  3.Run the analysis:
    python main.py 


## Future Scope

   ABG Integration: Adding logic to detect metabolic acidosis or alkalosis using pH and PaCO2 values.

    Visualization: Generating trend lines and glucose volatility graphs over time.

   HbA1c Correlation: Mapping daily glucose averages to estimated HbA1c percentages for better long-term diagnostic accuracy.
 

