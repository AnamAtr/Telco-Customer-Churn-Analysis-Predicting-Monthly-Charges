#  Telco Customer Monthly Charges Prediction

This project uses Linear Regression to predict how much a telecom customer pays monthly, based on behavioral and service-related factors such as contract type, internet service, payment method, and tenure.

---

##  Dataset

- Source: [Telco Customer Churn Dataset (Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- File used: `Telco_cleaned_data.csv`
- Size: ~7,000 records

---

##  Problem Statement

Telecom companies want to **predict how much customers spend monthly** using basic customer information, in order to:

- Understand key revenue-driving segments
- Target discounts and offers to the right audience
- Improve retention and profit forecasting

---

##  Project Workflow

### **Step 1: Import and Preprocess the Dataset**
- Loaded the dataset using `pandas`
- Selected features: `Tenure`, `Contract`, `InternetService`, `PaymentMethod`
- Target variable: `MonthlyCharges`
- Used OneHotEncoding for categorical features

### **Step 2: Split Data**
- Split dataset into **80% training** and **20% testing** using `train_test_split`

### **Step 3: Train Linear Regression Model**
- Built a pipeline using `sklearn.pipeline.Pipeline`
- Model trained using `LinearRegression()` from `sklearn.linear_model`

####  Results:
-**MAE**:  8.76

-**MSE**:120.33

-**R² Score**: 0.86


### **Step 4: Plot & Interpret Results**
- Visualized Actual vs Predicted Charges
- Extracted and explained feature coefficients

---

###  Feature Coefficient Insights

| Feature                                     | Coefficient | Interpretation                                                  |
|--------------------------------------------|-------------|-----------------------------------------------------------------|
| `Contract_One year`                        | +4.48       | One-year contracts slightly increase monthly charges            |
| `Contract_Two year`                        | +6.08       | Two-year contracts increase monthly charges more than One-year  |
| `Internetservice_Fiber optic`              | +34.79      | Fiber optic users pay significantly more                       |
| `Internetservice_No`                       | -37.33      | No internet service leads to lower monthly charges              |
| `Paymentmethod_Credit card (automatic)`    | +0.03       | Minimal effect on monthly charges                               |
| `Paymentmethod_Electronic check`           | -0.37       | Slightly lower charges with electronic check                    |
| `Paymentmethod_Mailed check`               | -0.20       | Slightly lower charges with mailed check                        |
| `Tenure`                                   | +0.19       | Each additional month increases charges by ~₹0.19               |


---

## Visual Output

- Scatter plot of actual vs predicted MonthlyCharges  
- Red line represents perfect prediction — most points are close to this line  
- Shows model is fairly accurate for real-world use

---

##  Conclusion

This project demonstrates how Linear Regression can be used to effectively predict customer spending behavior in the telecom industry. By analyzing service usage and contract features, we predicted the **Monthly Charges** with a reasonable accuracy of **R² = 0.86**.

- **Tenure** has a positive influence on charges — the longer a customer stays, the more they tend to spend.
- Customers using **Fiber Optic Internet** pay **significantly more**, making them a high-revenue segment.
- Surprisingly, **Contract types (One/Two year)** increased monthly charges slightly — possibly due to bundled services.
- **No Internet service** drastically lowers the monthly charge, which is expected.
- **Payment method** has minimal influence, though users paying by **credit card** showed marginally higher charges.

This model serves as a foundation for further enhancement using advanced algorithms, feature engineering, or classification tasks like predicting churn.

---

##  Tools & Libraries Used

- Python (pandas, numpy, matplotlib, seaborn)
- Scikit-learn (LinearRegression, Pipeline, OneHotEncoder)

---
