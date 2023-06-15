![alt text](Resources\crash-guard-low-resolution-color-logo_720.png?raw=true "title")
# CrashGuard-Pro
This repository contains a Python script that predicts the severity of road traffic accidents based on various features. The script uses a random forest classifier as the machine learning model and performs data preprocessing, feature selection, handling imbalanced datasets, model evaluation, and model saving.

## Data
The data used for this project is a subset of the Road Traffic Accidents (RTA) dataset that contains information about road traffic accidents in Singapore from 2015 to 2018. The features include:

- Service_year_of_vehicle: The number of years the vehicle has been in service
- Types_of_Junction: The type of junction where the accident occurred
- Area_accident_occured: The area where the accident occurred
- Driving_experience: The driving experience of the driver in years
- Type_of_vehicle: The type of vehicle involved in the accident
- Vehicle_driver_relation: The relation between the vehicle and the driver
- Educational_level: The educational level of the driver
- Type_of_collision: The type of collision that occurred
- Accident_severity: The severity of the accident (target variable)
The target variable has three classes: Fatal, Severe Injury and Slight Injury.

## Steps
1. Data cleaning: Fill in missing values with ‘Unknown’ for some columns
2. Data encoding: Use one-hot encoding for input features and label encoding for target variable
Feature selection: 
3. Use SelectKBest with chi2 scoring function to select 50 best features
4. Handling imbalanced dataset: Use SMOTENC to balance the dataset by creating synthetic samples for minority classes
5. Model building: Split the data into training and test sets and train a random forest classifier
6. Model evaluation: Use classification report and f1-score to evaluate the model performance on the test set
7. Model saving: Save the model and the ordinal encoder object to files using joblib.dump()

## Libraries
The script rta_model.py uses the following libraries:

- pandas: For data manipulation and analysis
- numpy: For numerical computing and array operations
- sklearn: For machine learning tasks such as data preprocessing, feature selection, model building, model evaluation, and model saving
- imblearn: For handling imbalanced datasets using oversampling techniques such as SMOTENC
- joblib: For saving and loading Python objects such as models and encoders

# How to Run
To run the script, you need to have Python 3 installed on your system. You also need to install the required libraries using pip or conda. You can download or clone this repository and navigate to the folder where the script is located. Then you can run the following command in your terminal:

- python rta_model.py

The script will print the classification report and the f1-score on the test set. It will also save two files in your current directory:

- ordinal_encoder2.joblib: The ordinal encoder object used for encoding some categorical features
- rta_model_deploy3.joblib: The trained random forest classifier