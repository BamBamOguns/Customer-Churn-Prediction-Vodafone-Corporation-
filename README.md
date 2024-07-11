# **Customer-Churn-Prediction-Vodafone-Corporation**
A machine learning predictor to determine the likelihood of a customer churning or not.

### **Introduction**

In today's competitive market, comprehending the dynamics of customer churn is essential for businesses aiming to enhance retention and mitigate losses. One pivotal factor influencing churn rates is the type of contract a customer holds. In this blog post, we will delve into the statistical relationship between churn rates and contract terms using a Chi-Square test, followed by the development and implementation of machine learning models to predict which customers are likely to leave the network. These models will utilize features such as contract type, tenure, phone service, internet service, paperless billing, and the ratio of monthly charges to total charges, among others. Notably, these features have demonstrated high predictive importance in logistic regression models for churn prediction.

### **Business Understanding**

##### **Problem Statement**

Vodafone, a leading telecommunications provider, is struggling with customer retention in an increasingly competitive market. To maintain its market position and improve customer loyalty, Vodafone needs to understand why customers leave and predict potential churners. The company plans to leverage historical data and analytics to develop a predictive model that identifies at-risk customers and informs effective retention strategies.

##### **Project Goal**

The goal of this project is to develop a predictive model using historical customer data and advanced analytics techniques to accurately identify customers at risk of churning. By doing so, the company aims to gain actionable insights into the factors driving customer churn and implement targeted retention strategies to enhance customer loyalty and reduce churn rates.

##### **Stakeholders**

    - Executive Leadership
    - Business Team
    - Data Science & Analytics Team
    - Customer Service Team
    - Sales Team

##### **Key Metrics and Success Criteria**

    - Accuracy: An accuracy rate of at least 85% indicates the model is reliably identifying churn and non-churn customers.

    - Precision: A precision rate of at least 80% ensures that most customers identified as churners are indeed at risk, minimizing false positives.

    - Recall: A recall rate of at least 75% indicates that the model is effectively capturing a significant portion of actual churners, minimizing false negatives.

    - F1 Score: An F1 score of at least 80% ensures a good balance between precision and recall.

    - ROC-AUC: An ROC-AUC score of at least 0.8 indicates strong discriminatory power.

##### **Data and Features**

The dataset includes features such as customerID, gender, SeniorCitizen, Partner, Dependents, tenure, PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, Contract, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges, and Churn.

##### **Hypothesis Testing**

    - Null Hypothesis (H0): There is no significant relationship between customer churn and contract type, tenure, and monthly charges.

    - Alternative Hypothesis (H1): There is a significant relationship between customer churn and contract type, tenure, and monthly charges.

##### **Models Used**

    - Logistic Regression Classifier (LR)
    - Random Forest Classifier (RF)
    - Support Vector Machine Classifier (SVC)
    - Gradient Boosting Classifier (GB)
    - Ada Boost Classifier (ADA)

##### **Analytical Questions**

1. How does the distribution of contract types (month-to-month, one year, two years) affect the overall churn rate?

2. Is there a pattern in churn rate based on customer tenure? Are there specific points in the customer lifecycle where churn is more likely?

3. Do customers with higher monthly charges tend to churn more often? Are there any specific thresholds where churn increases significantly?

4. Does the preferred payment method influence churn rate? Are certain payment methods associated with higher churn?

5. Are there demographic factors (like senior citizen status, gender, having a partner, or having dependents) that correlate with higher churn rates?

### **Data Cleaning**

1. Standardized column names for consistency.

2. Addressed missing values in multiple fields.

3. Ensured consistent datatypes and value formats across datasets.

4. Replaced missing values in relevant fields with "No phone service" or "No internet service".

5. Confirmed no duplicated values in the merged dataset.

### **Analysis and Insights**

##### **Univariate Analysis on Categorical Variables**

    - Gender: Nearly evenly split, indicating gender-specific targeting may not be necessary.

    - Senior Citizen: 16.2% of customers are senior citizens, a niche market for specific services.

    - Partner and Dependents: A slight majority do not have partners or dependents, indicating a significant demographic of single, independent individuals.

    - Phone Service: 90% of customers have phone service, indicating saturation.

    - Multiple Lines: 53% do not have multiple lines, showing varied communication needs.

    - Internet Service: Fiber optic is most common, suggesting a demand for high-speed internet.

    - Additional Services (Online Security, Online Backup, etc.): Most customers do not subscribe, indicating potential areas for increasing service uptake.

    - Streaming Services: Preference for movie streaming, indicating a trend.

    - Contract: More than half are on month-to-month contracts, a critical area for retention strategies.

    - Paperless Billing: 59% use paperless billing, indicating a shift towards digital solutions.

    - Payment Method: Electronic check is most common, possibly correlating with churn.

##### **Univariate Analysis on Numerical Variables**

    - Tenure: Average of 32.5 months, with longer tenure correlating with lower churn.

    - Monthly Charges: Average of $65.09, indicating diverse service plans.

    - Total Charges: Varies widely, indicating different levels of customer engagement.

##### **Bivariate Analysis**

    - Churn by Contract Type: Higher churn rates for month-to-month contracts.

    - Churn by Payment Method: Higher churn for electronic checks.

    - Churn by Internet Service: Higher churn for fiber optic services.

    - Churn by Streaming TV: Slightly higher churn for streaming TV subscribers.

    - Churn by Multiple Lines: No stark difference.

    - Churn by Online Security: Higher churn without online security.

##### **Analytical Questions Insights**

    - Churn Rate by Contract Type: Month-to-month contracts have a 43% churn rate.

    - Churn Rate by Tenure: Higher churn within the first 19 months.

    - Churn Rate by Monthly Charges: Higher churn for charges between $78.55 - $98.60.

    - Churn Rate by Payment Method: 45% churn rate for electronic checks.

    - Churn Rate by Demographic Factors: Gender, senior citizen status, partnership, and dependent status influence churn rates.

##### **Hypothesis Testing Results**

    - Categorical Value vs. Categorical Value: Significant relationship between contract type and churn (Cramér's V 0.418).

    - Numerical Values vs. Categorical Values: Significant differences in Monthly Charges and Tenure between churn and non-churn groups (Mann-Whitney U test, p-values of 1.188e-42 and 1.86e-148, respectively).

### **Modelling Insights**

##### **Metrics Breakdown on Balanced Dataset**

    - Accuracy: Random Forest 85.7%, Gradient Boosting 84.8%.

    - Precision: Random Forest 84.6%.

    - Recall: Random Forest and AdaBoost 87.3%.

    - AUC: Gradient Boosting 92.9%, Random Forest 92.6%.

##### **Best 2 Models after Hyperparameter Tuning**

1. **Gradient Boosting Classifier**
    - Accuracy: 84.8%

    - Precision: 83.2%

    - Recall: 87.3%

    - F1 Score: 85.2%

    - AUC: 92.9%

2. **Random Forest Classifier**
    - Accuracy: 85.7%

    - Precision: 84.6%

    - Recall: 87.3%

    - F1 Score: 85.9%

    - AUC: 92.6%

### Conclusion

The Gradient Boosting and Random Forest classifiers were the best-performing models after hyperparameter tuning. Both models provide strong metrics, with Gradient Boosting having a slightly higher AUC. These models can help Vodafone effectively predict and reduce customer churn by informing targeted retention strategies.
