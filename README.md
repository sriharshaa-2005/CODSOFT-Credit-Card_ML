# CODSOFT-Credit-Card_ML

# Fraud Detection Using Machine Learning

## Project Overview
This project implements a machine learning-based fraud detection system using a dataset containing transaction records. The goal is to classify transactions as fraudulent or non-fraudulent based on features such as transaction category, amount, location, and user details.

## Dataset
The dataset consists of two CSV files:
- **Fraudtrain.csv** (Training Data)
- **Fraudtest.csv** (Test Data)

### Features:
- `cc_num`: Credit card number (masked)
- `category`: Type of transaction (e.g., groceries, travel, personal care)
- `amt`: Transaction amount
- `gender`: Gender of the cardholder
- `zip`: ZIP code of the transaction
- `lat`, `long`: Latitude and longitude of the transaction location
- `city_pop`: Population of the transaction city
- `unix_time`: Timestamp of the transaction
- `merch_lat`, `merch_long`: Latitude and longitude of the merchant
- `is_fraud`: Target variable (1 for fraudulent transactions, 0 for legitimate transactions)

## Data Preprocessing
- Checked for missing values and cleaned data.
- Encoded categorical variables (`category` and `gender`) using label encoding.
- Split data into training and validation sets.

## Machine Learning Models
The following models were implemented using **Scikit-learn**:
- **Logistic Regression**
- **Decision Tree Classifier**
- **Random Forest Classifier**
)



#### Best Model Performance (Random Forest Classifier):
- **Accuracy:** ~99.9%
- **Precision:** 0.86
- **Recall:** 0.70
- **F1-score:** 0.77

## Prediction on New Data
To predict fraud on new transactions:
```python
new_data = pd.DataFrame({'cc_num':[30400000000000], 'category':[6], 'amt':[43], 'gender':[2], 'zip':[28658], 'lat':[46.58], 'long':[-112], 'city_pop':[149],
       'unix_time':[1325376076], 'merch_lat':[43.150704], 'merch_long':[100]}, index=[0])

prediction = rf.predict(new_data)
print("Prediction:", prediction)
```

## Conclusion
This project successfully implements fraud detection using machine learning techniques. The **Random Forest Classifier** showed the best performance. Future improvements can include:
- Using deep learning techniques.
- Implementing anomaly detection methods.
- Handling class imbalance with SMOTE or other techniques.



