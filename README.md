# Electric Vehicle Type Predictor
Electric Vehicle Type Predictor is a machine learning model that classifies electric vehicles as either Battery Electric Vehicles (BEVs) or Plug-in Hybrid Electric Vehicles (PHEVs) using the Electric Vehicle Population dataset from Kaggle. It analyzes key features to improve EV categorization accuracy.

## Problem Statement
With the growing shift toward electric mobility, understanding and categorizing different types of electric vehicles has become essential for sustainable transportation planning, policy-making, and industry analysis. The goal of this project is to build an intelligent Electric Vehicle Type Predictor that classifies vehicles as either Battery Electric Vehicles (BEVs) or Plug-in Hybrid Electric Vehicles (PHEVs) based on their key attributes such as electric range, model, make, price and location. The dataset undergoes cleaning, preprocessing, and feature encoding to ensure consistency and accuracy.
A machine learning model is trained (using Logistic Regression) to predict the type of EV based on these attributes.

To make the model accessible, a Streamlit-based web interface is developed, allowing users to upload vehicle data and obtain instant predictions on EV type — making it a practical tool for data analysts, automobile researchers, and sustainability enthusiasts.

## Understanding the Dataset – Identifying Key Features and Target Variable
The dataset provides comprehensive information about electric and plug-in hybrid vehicles, including technical specifications and registration details. It captures multiple features such as vehicle make, model, electric range, and location, enabling classification between Battery Electric Vehicles (BEV) and Plug-in Hybrid Electric Vehicles (PHEV).


📂 Dataset Source: Download the dataset here [https://www.kaggle.com/datasets/gunapro/electric-vehicle-population-data]

## Dataset Overview
| Feature Name                                      | Description                                                            | Type                              |
| ------------------------------------------------- | ---------------------------------------------------------------------- | --------------------------------- |
| VIN (1-10)                                        | Unique vehicle identification number (partially masked)                | Categorical                       |
| County                                            | County where the vehicle is registered                                 | Categorical                       |
| City                                              | City of registration                                                   | Categorical                       |
| State                                             | State where the vehicle is registered                                  | Categorical                       |
| Postal Code                                       | Postal code of the vehicle’s registration area                         | Numerical                         |
| Model Year                                        | Manufacturing year of the vehicle                                      | Numerical                         |
| Make                                              | Brand or manufacturer (e.g., Tesla, Nissan, Toyota)                    | Categorical                       |
| Model                                             | Specific vehicle model (e.g., Model 3, Leaf, Prius Prime)              | Categorical                       |
| **Electric Vehicle Type**                         | **Indicates whether the vehicle is a BEV or PHEV**                     | **Categorical (Target Variable)** |
| Clean Alternative Fuel Vehicle (CAFV) Eligibility | Indicates if the vehicle qualifies as a clean alternative fuel vehicle | Categorical                       |
| Electric Range                                    | The distance (in miles) a vehicle can travel on electric power alone   | Numerical                         |
| Base MSRP                                         | Manufacturer’s Suggested Retail Price (in USD)                         | Numerical                         |
| Legislative District                              | District number associated with the registration area                  | Numerical                         |
| DOL Vehicle ID                                    | Unique identifier used by the Department of Licensing                  | Numerical                         |
| Vehicle Location                                  | Geographical coordinates of the vehicle’s registration area            | Categorical                       |
| Electric Utility                                  | Electric utility company serving the vehicle’s location                | Categorical                       |
| 2020 Census Tract                                 | Census tract identifier for the location                               | Numerical                         |

## Data Preprocessing
•	Loaded the Electric Vehicle Population dataset using pandas.

•	Handled missing values and removed irrelevant columns.

•	Encoded categorical features using LabelEncoder/OneHotEncoder.

•	Split the data into features (X) and target (y).

•	Scaled the features for better model performance.

## Target Variable

Electric Vehicle Type

Categories:

  a. Battery Electric Vehicle (BEV) ---- 0

  b. Plug-in Hybrid Electric Vehicle (PHEV) ---- 1

This is the output variable the model aims to predict.
## Frontend --> Streamlit
https://klara-homosporous-heavenly.ngrok-free.dev/
## Key Features Used for Prediction

After removing identifiers and redundant columns (like VIN, DOL Vehicle ID, Vehicle Location), the following 13 features were selected as inputs for model training:
•	County
•	City
•	State
•	Postal Code
•	Model Year
•	Make
•	Model
•	Clean Alternative Fuel Vehicle Eligibility
•	Electric Range
•	Base MSRP
•	Legislative District
•	Electric Utility
•	2020 Census Tract
These features collectively describe the technical, geographic, and eligibility aspects of the vehicle, making them strong predictors for determining the EV type.

## Project Workflow
1. Data Preprocessing

Feature Selection: Chose relevant features and removed redundant columns.

Handling Missing Values: Imputed missing numerical data using the median and categorical data using the mode.

Encoding: Applied Label Encoding for categorical variables and the target column.

Scaling: Standardized numerical features to improve SVM model performance.

2. Model Development

Algorithm: Used a Linear Support Vector Machine (SVM) classifier to predict vehicle type.

Train-Test Split: Divided the data into 80% training and 20% testing sets.

Evaluation Metrics: Measured performance using accuracy, confusion matrix, and classification report.

3. Visualizations

Confusion Matrix Heatmap: Displays correct vs. incorrect predictions.

Feature Importance Plot: Highlights key features influencing classification outcomes (based on SVM coefficients).

## Requirements
Jupyter Notebook / Google Colab

Streamlit	

Ngrok / LocalTunnel

Python 3.x

pandas

numpy

scikit-learn

joblib

streamlit

pyngrok

## Project Structure

Electric_Vehicle_Type_Predictor/

│
├── Electric_Vehicle_Population_Data.csv     
├── EV_type_predictor.ipynb                  
├── app.py                                   
├── ev_type_predictor_model.pkl              
├── feature_columns.pkl                      
└── README.md                                


## How to Run the Project
1.	Open the project in Google Colab.
2.	Upload the Electric Vehicle Population dataset (CSV file).
3.	Run all code cells in sequence.
4.	The model will be trained and tested automatically.
5.	View the classification results and accuracy score in the output.
