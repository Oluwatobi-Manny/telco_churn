*An analysis of customer churn rate for Vertex Telco.*

# Use Case: Customer Churn Rate Analysis
---

**Overview:**
---
This project aims to analyze and predict customer churn rate using Python. By leveraging data analytics and machine learning techniques, we can identify the key factors contributing to churn and develop strategies to improve customer retention.

**Objective:**
---
The primary objective of this analysis is to understand the reasons behind customer churn and predict which customers are likely to leave. This will help the company take proactive measures to retain customers and enhance overall satisfaction.

**Dataset**
---
<table>
  <thead>
    <tr>
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>customerID</td>
      <td>Unique identifier for each customer</td>
    </tr>
    <tr>
      <td>gender</td>
      <td>Gender of the customer (Male/Female)</td>
    </tr>
    <tr>
      <td>SeniorCitizen</td>
      <td>Indicates if the customer is a senior citizen (0: No, 1: Yes)</td>
    </tr>
    <tr>
      <td>Partner</td>
      <td>Indicates if the customer has a partner (Yes/No)</td>
    </tr>
    <tr>
      <td>Dependents</td>
      <td>Indicates if the customer has dependents (Yes/No)</td>
    </tr>
    <tr>
      <td>tenure</td>
      <td>Number of months the customer has been with the company</td>
    </tr>
    <tr>
      <td>PhoneService</td>
      <td>Indicates if the customer has phone service (Yes/No)</td>
    </tr>
    <tr>
      <td>MultipleLines</td>
      <td>Indicates if the customer has multiple lines (Yes/No/No phone service)</td>
    </tr>
    <tr>
      <td>InternetService</td>
      <td>Type of internet service (DSL/Fiber optic/No)</td>
    </tr>
    <tr>
      <td>OnlineSecurity</td>
      <td>Indicates if the customer has online security service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>OnlineBackup</td>
      <td>Indicates if the customer has online backup service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>DeviceProtection</td>
      <td>Indicates if the customer has device protection service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>TechSupport</td>
      <td>Indicates if the customer has tech support service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>StreamingTV</td>
      <td>Indicates if the customer has streaming TV service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>StreamingMovies</td>
      <td>Indicates if the customer has streaming movies service (Yes/No/No internet service)</td>
    </tr>
    <tr>
      <td>Contract</td>
      <td>Type of contract (Month-to-month/One year/Two year)</td>
    </tr>
    <tr>
      <td>PaperlessBilling</td>
      <td>Indicates if the customer has paperless billing (Yes/No)</td>
    </tr>
    <tr>
      <td>PaymentMethod</td>
      <td>Payment method (Electronic check/Mailed check/Bank transfer/Credit card)</td>
    </tr>
    <tr>
      <td>MonthlyCharges</td>
      <td>Monthly charges for the customer</td>
    </tr>
    <tr>
      <td>TotalCharges</td>
      <td>Total charges for the customer</td>
    </tr>
    <tr>
      <td>Churn</td>
      <td>Indicates if the customer has churned (Yes/No)</td>
    </tr>
  </tbody>
</table>

**Key Questions:**
The churn analysis will address the following key questions:

   * What is the overall churn rate?
   * Which customer demographics are most correlated with churn?
   * How do service usage patterns differ between churned and retained customers?
   * What contract types and billing amounts are associated with higher churn rates?

**Method:**
The analysis involves the following steps:

1. **EDA and Data Cleaning:**
    * Replaced empty strings
    ```
    # Replace empty strings with NaN
    data['TotalCharges'] = data['TotalCharges'].replace(' ', np.nan)

    # Fill NaN values with 0 and convert to float
    data['TotalCharges'] = data['TotalCharges'].fillna(0).astype(float)
    ```
    * Churn distribution

![Churn distribution](<Images/Screenshot (252).png>)


2. **Sales Analysis:**
    * Customer demographics

    ![Customer Demographics](<Images/Screenshot (234).png>)

    * Service Usage and Preferences

    ![Service usage](<Images/Screenshot (237).png>)

    * Contract and billing

    ![Contract and billing](<Images/Screenshot (240).png>)

    * Customer segmentation

    ![Customer segmentation](<Images/Screenshot (241).png>)

3. **Analysis:**
    * Data distribution 

    ![Data distribution](<Images/Screenshot (243).png>)

4. **Data Preprocessing:**
    * Create new feature
    ```
    # Monthly charge ratio

    data['ChargesRatio'] = data['MonthlyCharges'] / data['TotalCharges']
    ```
    * One-Hot Encoding for categorical features

    ![Hot encoding](<Images/Screenshot (245).png>)

5. **Model Building:**
    * Choosing a model

    ![Model selection](<Images/Screenshot (247).png>)

    * Determine most important features

    ![Important feature](<Images/Screenshot (253).png>)

**Expected Outcomes:**
By the end of this analysis, we expect to:

- Understand the main factors driving customer churn.
- Develop accurate predictive models for customer churn.
- Provide actionable insights to reduce churn rates and enhance customer retention strategies.

**LIBRARIES AND VERSION**
---
- numpy: 1.26.4
- pandas: 2.2.2
- matplotlib: 3.9.1.post1
- seaborn: 0.13.2
- sklearn: 1.4.2
- scipy: 1.13.1
- statsmodels: 0.14.2