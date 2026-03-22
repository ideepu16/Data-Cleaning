# Data-Cleaning
**Project Overview:**
This project demonstrates how to clean a raw dataset using Python in Google Colab.
The Titanic dataset contains missing values, unnecessary columns, and categorical data that need preprocessing before analysis or machine learning.

**Objective**
The main objective of this project is to:
Identify missing values
Remove unnecessary columns
Fill null values
Convert categorical data into numeric format
Remove duplicate records
Save the cleaned dataset

**Dataset Used**
Titanic Dataset (train.csv)

**Tools and Technologies**
Python
Pandas
Google Colab

**Steps Performed:**
1. Import Library
import pandas as pd
2. Load Dataset
df = pd.read_csv('train.csv')
3. Check Dataset Information
df.info()
4. Find Missing Values
df.isnull().sum()
5. Remove Unnecessary Columns
df = df.drop(['Cabin','Ticket','Name'], axis=1)
6. Fill Missing Age Values
df['Age'] = df['Age'].fillna(df['Age'].mean())
7. Fill Missing Embarked Values
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])
8. Convert Gender Column into Numeric Form
df['Sex'] = df['Sex'].map({'male':0, 'female':1})
9. Remove Duplicate Records
df = df.drop_duplicates()
10. Save Cleaned Dataset
df.to_csv('cleaned_titanic.csv', index=False)

**Output**
A cleaned dataset named cleaned_titanic.csv is generated after preprocessing.

**Learning Outcome**
By completing this project, you will understand:
Data cleaning process
Handling missing values
Data preprocessing techniques
Basic dataset preparation for machine learning

**Conclusion:**
Data cleaning is an essential step before analysis because raw data often contains errors, missing values, and inconsistent formatting.
