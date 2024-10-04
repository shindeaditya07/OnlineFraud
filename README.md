# Online Payment Fraud Detection

In this project, I built a model that detects fraudulent transactions in online payment systems. Fraudulent transactions are a major concern for financial institutions, and this project aims to tackle the problem using a **Decision Tree Classifier**. The model is trained on data with transaction types, amounts, and account balances to predict the likelihood of fraud.

## Dataset

The dataset used in this project (`onlinefraud.csv`) contains the following key columns:
- **type**: The type of transaction (e.g., PAYMENT, TRANSFER).
- **amount**: The amount of the transaction.
- **oldbalanceOrg**: The sender's balance before the transaction.
- **newbalanceOrig**: The sender's balance after the transaction.
- **isFraud**: A binary indicator (1 = fraud, 0 = not fraud).

## Project Workflow

### Step 1: Data Loading and Exploration
I used `pandas` to load and explore the dataset. I checked for missing values and examined the distribution of the `type` column.

### Step 2: Data Visualization
To visualize the distribution of transaction types, I created a pie chart using `plotly.express`.


### Step 3: Data Preparation
I converted the categorical `type` column into numerical values using `pd.get_dummies()` to make the dataset compatible with machine learning models. Then, I dropped non-numeric columns like IDs.

### Step 4: Correlation Analysis
To better understand the features, I calculated the correlation matrix to check the relationship between the features and the target variable `isFraud`.

### Step 5: Building the Decision Tree Model
I built a **Decision Tree Classifier** using `scikit-learn`. First, I selected relevant features such as `type`, `amount`, `oldbalanceOrg`, and `newbalanceOrig` for the prediction task. I split the data into training and testing sets using an 80-20 ratio. I then trained the Decision Tree Classifier on the training set:

### Step 6: Testing the Model
After training the model, I evaluated its performance on the testing set using the `.score()` function.

### Step 7: Making Predictions
I tested the model on a sample feature set to see if it could correctly predict whether a transaction is fraudulent.

## Model
I used a **Decision Tree Classifier** for this project. The features used for prediction include:
- **type**: The type of transaction (encoded numerically).
- **amount**: Transaction amount.
- **oldbalanceOrg**: Sender's balance before the transaction.
- **newbalanceOrig**: Sender's balance after the transaction.

## Results
The model was able to achieve an accuracy of approximately **99.97%** (depending on dataset and splits). The Decision Tree Classifier was effective in identifying fraudulent transactions based on the given features.
