# IDRA Day 12 - Used Car Data Preprocessing

## Assignment

Used Car Data Preprocessing using Python, Pandas, NumPy and Scikit-learn.

## Organization

India Data Research Academy (IDRA)

## Description

This project focuses on preprocessing a Used Car Resale Dataset for further machine learning analysis.

The dataset was inspected for missing values, duplicate records, outliers, categorical variables and numerical features. Different preprocessing techniques were applied to prepare the data for machine learning.

## Dataset

The dataset contains information about used cars, including:

- Brand
- Year
- Mileage
- Engine capacity
- Power
- Fuel type
- Transmission
- City
- Seller type
- Condition
- Previous owners
- Accidents reported
- Service score
- Resale price

The target variable is:

`Resale_Price_Lakh`

## Data Preprocessing Steps

The following preprocessing steps were performed:

1. Loaded the dataset using Pandas.
2. Checked the shape and structure of the dataset.
3. Examined the data types of all columns.
4. Checked for missing values.
5. Checked for duplicate records.
6. Removed `Car_ID` because it is an identifier and not a useful predictive feature.
7. Identified numerical and categorical features.
8. Detected outliers using the IQR method.
9. Handled extreme numerical values using IQR-based capping.
10. Separated the features and target variable.
11. Split the dataset into training and testing sets using an 80:20 ratio.
12. Encoded categorical variables using One-Hot Encoding.
13. Scaled numerical features using StandardScaler.
14. Fitted the encoder and scaler only on the training data.
15. Applied the fitted transformations to the testing data.
16. Verified the processed datasets.
17. Exported the processed training and testing datasets as CSV files.

## Outlier Handling

The Interquartile Range (IQR) method was used to identify extreme values in numerical columns.

The IQR method uses the first quartile (Q1) and third quartile (Q3) to determine the acceptable range.

Extreme values were capped using the calculated IQR limits instead of removing large numbers of records.

## Encoding

Categorical variables were converted into numerical values using One-Hot Encoding.

One-Hot Encoding was selected because the categorical variables such as Brand, Fuel_Type, Transmission, City and Seller_Type are nominal categories.

`handle_unknown='ignore'` was used so that unseen categories in the test data do not cause errors.

## Feature Scaling

StandardScaler was used for numerical features.

The scaler was fitted only on the training dataset and then used to transform both the training and testing datasets.

This helps prevent data leakage.

## Train-Test Split

The dataset was divided into:

- 80% Training Data
- 20% Testing Data

`random_state=42` was used to make the split reproducible.

## Target Variable

The target variable is:

`Resale_Price_Lakh`

The remaining relevant columns were used as input features.

## Data Leakage Prevention

To avoid data leakage:

- The encoder was fitted only on training data.
- The scaler was fitted only on training data.
- The fitted encoder and scaler were then applied to the test data.

This ensures that information from the testing dataset is not used during the training preprocessing stage.

## Verification

After preprocessing, the following checks were performed:

- Shape of training and testing datasets
- Missing values
- Duplicate values
- Data types
- Scaled numerical features
- Target variable
- Final processed data

## Files

- `IDRA_Day12_Used_Car_Data_Preprocessing.ipynb`
- `Day12_Used_Car_Preprocessing_Dataset.csv`
- `Day12_Preprocessed_Used_Car_Train.csv`
- `Day12_Preprocessed_Used_Car_Test.csv`
- `README.md`

## Libraries Used

- Pandas
- NumPy
- Scikit-learn

## Conclusion

The Used Car Resale Dataset was successfully preprocessed using Python.

Outliers were identified and handled using the IQR method. Categorical variables were encoded using One-Hot Encoding, and numerical variables were standardized using StandardScaler.

The data was divided into training and testing sets, and preprocessing transformations were fitted only on the training data to prevent data leakage.

The final processed training and testing datasets were exported as CSV files and are ready for further machine learning tasks.
