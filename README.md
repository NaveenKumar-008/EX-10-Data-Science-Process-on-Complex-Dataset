# Ex-10-Data-Science-Process-on-Complex-Dataset

## AIM:-
To Perform Data Science Process on a complex dataset and save the data to a file. 

# ALGORITHM:-
### STEP 1
Read the given Data.
### STEP 2
Clean the Data Set using Data Cleaning Process.
### STEP 3
Apply Feature Generation/Feature Selection Techniques on the data set.
### STEP 4
Apply EDA /Data visualization techniques to all the features of the data set

# DATA PREPROCESSING:-
```
import pandas as pd
import numpy as np
import seaborn as sns
from google.colab import files
uploaded = files.upload()
df = pd.read_csv("annual_balance.csv")
df
df.head()
```
![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/8e5c1126-b0ea-4d38-a37c-bacdf24ab2ca)

![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/7e805629-25de-4f8a-830f-210b241369e8)

# DATA CLEANING:-
# Missing Value:
```
df.isnull().sum()
```
![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/f40d8e28-59fe-4e51-87e0-bab1e1184b05)
# Duplication:
```
df.dropna()
data = df.drop_duplicates()
data
```
![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/9fbe703a-a190-4625-9a71-4b362145c13d)
# FEATURE GENERATION:-
```
from sklearn.preprocessing import OrdinalEncoder
encoder = OrdinalEncoder()
categorical_features = ['Period', 'Values', 'Inst_sector_code']
encoder.fit(df[categorical_features])
encoded_features = encoder.transform(df[categorical_features])
df[categorical_features] = encoded_features
print(df.head())
```
![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/1bc47393-e1cd-448c-8cba-18e43b84a422)
# DATA VIRTUALIZATION:-
# Pair Plot:
```
import matplotlib.pyplot as plt
sns.pairplot(df[numeric_features])
plt.title('Pairplot of Numerical Features')
plt.show()
```
![image](https://github.com/NaveenKumar-008/EX-10-Data-Science-Process-on-Complex-Dataset/assets/128135244/af26c0db-5e63-4329-942d-e55855e2ec02)

# Bar Plot:
```
column_to_visualize = 'Period'
plt.figure(figsize=(8, 6))
df[column_to_visualize].value_counts().plot(kind='bar')
plt.title(f'Bar Plot of {column_to_visualize}')
plt.xlabel(column_to_visualize)
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()
```
![image](https://github.com/ManiKandan228/Ex-10-Data-Science-Process-on-Complex-Dataset/assets/119160414/67d80bae-47bd-4184-81b9-655a72530485)

# Histogram:
```
plt.figure(figsize=(8, 6))
plt.hist(df[column_to_visualize], bins=10, edgecolor='black')
plt.title(f'Histogram of {column_to_visualize}')
plt.xlabel(column_to_visualize)
plt.ylabel('Frequency')
plt.show()
```
![image](https://github.com/ManiKandan228/Ex-10-Data-Science-Process-on-Complex-Dataset/assets/119160414/56e43c01-ae5d-4025-b42b-ca109e603d57)

# Heat Map:
```
correlation_matrix = df.corr()
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```
![image](https://github.com/ManiKandan228/Ex-10-Data-Science-Process-on-Complex-Dataset/assets/119160414/c55419db-167c-44c9-9dde-ca6efdcb3883)

# RESULT:-
 Data Science Process on Complex Dataset has been applied successfully.
