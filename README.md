
# Vehicle Insurance Fraud Detection Using Machine Learning

## Introduction

This project focuses on detecting fraudulent vehicle insurance claims using multiple machine learning algorithms. Insurance fraud causes significant financial losses for companies, making automated fraud detection systems essential.
The aim of this project is to analyze insurance claim data and build predictive models that can classify whether a claim is fraudulent or legitimate. Several machine learning techniques are implemented and compared to determine which model performs best in identifying suspicious claims.

---

## Dataset Description

The dataset used in this project was sourced from Kaggle and contains **15,421 insurance claim records**. Each record represents a claim submitted by a policyholder and includes different types of information related to the claim, the vehicle, and the policyholder.

### Key Data Categories

**Claim Details**

* Month and day when the claim was reported
* Timing information related to the incident

**Vehicle Details**

* Vehicle manufacturer
* Vehicle category
* Vehicle price range
* Age of the vehicle

**Policy Information**

* Type of insurance policy
* Policy number
* Deductible amount
* Driver rating

**Customer Information**

* Gender of the policyholder
* Marital status
* Age of the policyholder

**Historical Claim Information**

* Number of previous claims
* Past accident history

**Legal and Investigation Factors**

* Police report availability
* Witness presence
* Insurance agent involvement

The **target variable** is **FraudFound_P**, which indicates whether a claim is fraudulent (`1`) or legitimate (`0`).

---

## Project Methodology

### 1. Data Collection

The dataset was obtained from Kaggle and loaded into the Python environment using the Pandas library.

### 2. Data Cleaning

The dataset was inspected for inconsistencies, missing values, and anomalies.
Outliers were identified and treated using the **Interquartile Range (IQR)** method. No missing values were detected in the dataset.

### 3. Data Transformation

Since machine learning algorithms require numerical inputs, categorical features were converted into numeric values using:

* **Label Encoding**
* **One-Hot Encoding**

This transformation allows the algorithms to process categorical information effectively.

### 4. Handling Imbalanced Data

Insurance fraud datasets are typically highly imbalanced because fraudulent claims occur far less frequently than legitimate ones.

To address this issue, the **Synthetic Minority Over-sampling Technique (SMOTE)** was applied.
SMOTE generates synthetic samples for the minority class (fraud cases), helping models learn patterns related to fraud more effectively.

### 5. Train-Test Data Split

The dataset was divided into two parts:

* **Training Data (80%)** – Used for building the models
* **Testing Data (20%)** – Used for evaluating model performance

---

## Machine Learning Models Implemented

Several classification algorithms were trained and evaluated to determine their effectiveness in detecting fraudulent claims.

### Logistic Regression

A statistical model that predicts the probability of fraud.
It performs well in identifying legitimate claims but struggles with detecting fraudulent ones due to class imbalance.

### Decision Tree

A rule-based model that splits data into branches based on feature values.
While easy to interpret, it tends to generate a high number of false positives when predicting fraud.

### Random Forest

An ensemble learning technique that combines multiple decision trees to improve prediction accuracy.
It achieves strong overall accuracy but may still overlook some fraudulent cases.

### Support Vector Machine (SVM)

A classification algorithm that separates classes using optimal decision boundaries.
It provides a balanced performance between precision and recall.

### Gradient Boosting

An advanced ensemble technique that builds models sequentially to correct previous errors.
This model achieves strong fraud detection capability but may classify some legitimate claims as fraudulent.

---

## Model Performance

The performance of each model was evaluated using **Accuracy, Precision, and Recall** metrics.

| Model                  | Accuracy | Precision (Fraud) | Recall (Fraud) |
| ---------------------- | -------- | ----------------- | -------------- |
| Logistic Regression    | 0.755    | 0.146             | 0.584          |
| Decision Tree          | 0.858    | 0.076             | 0.084          |
| Random Forest          | 0.894    | 0.187             | 0.381          |
| Support Vector Machine | 0.827    | 0.154             | 0.381          |
| Gradient Boosting      | 0.803    | 0.242             | 0.492          |

---

## Practical Implications

**Logistic Regression**

* Useful for initial claim screening
* May require additional verification steps for fraud detection

**Decision Tree**

* Highly interpretable
* Limited effectiveness in identifying fraudulent claims

**Random Forest**

* Strong performance in identifying legitimate claims
* Moderate success in detecting fraud

**Support Vector Machine**

* Provides balanced detection performance
* May produce some false positives

**Gradient Boosting**

* Best at identifying fraudulent claims
* May increase the number of false alerts

---

## Final Conclusion

Machine learning techniques can significantly improve the detection of fraudulent insurance claims.
However, choosing the most suitable model depends on the operational priorities of the insurance company.

If the goal is to **minimize missed fraud cases**, models with higher recall such as **Gradient Boosting** are preferable.
If the priority is **reducing false alarms**, models with higher precision may be more appropriate.

Balancing these trade-offs is essential for building an efficient fraud detection system that protects companies from financial loss while maintaining customer trust.

---

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Imbalanced-learn (SMOTE)
* Matplotlib
* Seaborn

---

## Future Improvements

* Hyperparameter tuning for better model performance
* Feature selection and feature engineering
* Use of deep learning models
* Deployment of the model as a real-time fraud detection system
