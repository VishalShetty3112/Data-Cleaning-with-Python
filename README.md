# Data-Cleaning-with-Python

## 👨🏼‍💻 Introduction
This project involves cleaning and preprocessing a real-world loan dataset to prepare it for meaningful analysis and future machine learning applications. The dataset is loaded into python pandas dataframe. Various Data cleaning and preprocessing operations are performed to ensure the dataset is ready for the analysis and visualization.

## 𝄜 Dataset Description
The loan dataset consists of 13 columns including 'UID', 'Marital_status', 'Dependents', 'Is_graduate', 'Income', 'Loan_amount', 'Term_months', 'Credit_score', 'Approval_status', 'Age', 'Sex', 'Purpose', and 'Hobby'.


![Screenshot (62)](https://github.com/user-attachments/assets/c9969035-a79d-40e3-944b-61f72116a267)


## ⚙️ Data Cleaning & Preprocessing
 ###  Dropping Duplicates

 ![Screenshot (65)](https://github.com/user-attachments/assets/acbaf569-2d65-473c-a2e2-bf45bf1e6860)

Duplicate rows are identified and removed from the dataset both based on the entire row.Dropped Duplicate UID’s on the 'UID' column.


### Handling Incorrect Records
Negative values in the 'Age' column are replaced with a Age>=0.
Since 1 row has found with ‘Age’ of -12. We dropped the rows having Age<0.

#### df =df[(df['Age'].isna()) | (df['Age']>=0)]


### Converting Data Types
The ‘Dependents’, ‘Income’ columns are converted to the float data type. Categorical data types are assigned to 'Marital_status' and 'Is_graduate' columns. Credit Column is converted to object data type.

![Screenshot (66)](https://github.com/user-attachments/assets/6e26c386-6f57-451b-bb06-6d527dddc0f6)


### Data Standardization
String values in the 'Marital_status' column are standardized by converting to Uppercase. In the 'Sex' column, 'M' and 'F' values are replaced with 'Male' and 'Female’ respectively.

#### df.loc[:,'Marital_status'] = df['Marital_status'].str.upper()
#### df['Marital_status'].value_counts()

#### df.loc[:,'Sex'] =df['Sex'].replace({'M' : 'Male', 'F' : 'Female'})
#### df['Sex'].value_counts()


### Handling Missing Values

![Screenshot (64)](https://github.com/user-attachments/assets/bd0cabe4-f477-4757-9398-b7db9ee9af8a)

'Marital_status', ‘Dependents’ column are filled with mode values.
Missing values in the 'Is_graduate' column are filled with 'Graduate'.
'Loan_amount', 'Term_months' and 'Age' columns are filled with their mean values.
Used np.random.choices with proportions of existing values to fill missing values in the ‘Credit_Score’, ‘Sex’ columns.

### Dropping Irrelevant Columns
The 'Hobby' column is dropped from the dataset since it is not important and not required for analysis.

## 🛠 Requirements
* Pandas
*	NumPy
*	Jupyter Notebook for scripting and analysis

## ✅ Conclusion
The loan dataset is successfully cleaned and prepared. The data preprocessing steps addressed key quality issues  includes removal of duplicate and invalid entries , correction of inconsistent formats, handling of missing values using mode, mean, and probabilistic imputation to preserve data integrity, conversion of data types and standardization of categorical values.
By resolving these issues, the dataset is now well-structured and reliable making it suitable for Exploratory Data Analysis and Visualization of trends

![Screenshot (63)](https://github.com/user-attachments/assets/330bb449-7e6b-4318-803b-183c3a46c5c2)


## 📊 Exploratory Data Analysis for Cleaned Dataset

![1](https://github.com/user-attachments/assets/55defb82-ccd8-4408-9aba-157dae9a3b52)

![2](https://github.com/user-attachments/assets/f1567e09-51f6-4770-be4d-c01c251ebf7a)

![3](https://github.com/user-attachments/assets/c8b3e6bc-0a78-4b9f-bb88-c18562002c19)

![4](https://github.com/user-attachments/assets/c7b4be2a-ba93-4f25-9307-0a0eef33ed2b)
