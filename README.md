# Crime-Analysis
Author: Lucjan Szulim
This project analyzes crime patterns in Montgomery County by combining multiple public datasets to better understand how short-term arrest activity relates to broader crime trends and police dispatch behavior.
# Project Overview
The goal of this project is to explore relationships between reported crimes, police dispatch incidents, and recent arrest data. By applying statistical analysis and data visualization techniques, this project aims to identify patterns in when, where, and how criminal activity occurs—and whether short-term arrest trends reflect larger crime dynamics.
# Datasets
This project uses three datasets from the Montgomery County Data Portal:
Crime Data (2016–Present):
Contains all reported crimes under UCR standards, including offense type, location, and time.
Limitations: Preliminary classifications, multiple offenses per incident, evolving investigations.
Daily Arrest Data (Last 30 Days):
Includes booking records such as age, arrest date, and most serious charge. Updated frequently.
Limitations: Limited time range, redacted personal data, charges may change.
Police Dispatch Incidents:
Records of calls for service, including incident type, time, and location.
Limitations: Possible duplicate records, categories may not align directly with crime data.
# Methods
Data cleaning and preprocessing using Python (pandas, NumPy)
Exploratory Data Analysis (EDA) with visualizations (Matplotlib, Seaborn)
Time-series analysis and trend comparison
Correlation analysis between datasets
Hypothesis testing (t-tests, chi-square)
Basic linear regression modeling
Dashboard and map visualizations using Tableau
