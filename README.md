# ConnectTel-Churn-Prediction
## Customer Churn Prediction: Unlocking Retention Strategies with Data Science

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/Cover.png" alt="Displays" width="800" height="400"/>

### Introduction
In the highly competitive telecommunications industry, customer retention is crucial for sustaining revenue growth. Customer churn, the loss of subscribers to competitors is a pressing challenge. This report presents a data-driven approach to understanding and predicting customer churn using machine learning techniques. By leveraging real-world customer data, we uncover key insights that can help **ConnectTel Telecom Company** improve customer retention strategies.

### Table of Contents
- [Problem Definition](#problem-definition)
- [Understanding the Dataset](#understanding-the-dataset)
  - [Key Features in the Dataset](#key-features-in-the-dataset)
  - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Key Insights from Exploratory Data Analysis (EDA)](#key-insights-from-exploratory-data-analysis-eda)
  - [Correlation Analysis](#correlation-analysis)
- [Predictive Modeling](#predictive-modeling)
  - [Feature Engineering](#feature-engineering)
  - [Model Selection](#model-selection)
  - [Handling Class Imbalance](#handling-class-imbalance)
  - [Model Training and Validation](#model-training-and-validation)
  - [Model Evaluation](#model-evaluation)
- [Actionable Insights](#actionable-insights)
- [Business Implications & Recommendations](#business-implications-and-recommendations)
- [Conclusion](#conclusion)


### Problem Definition
- ConnectTel needed a solution to predict customer churn effectively to maintain its customer base.
- Develop a machine learning model that accurately identifies customers likely to churn, focusing on reducing false negatives.

### Understanding the Dataset
The dataset analyzed contains **7,043 customer records** with **20 key features**, including demographics, service subscriptions, billing information, and customer tenure. The primary objective is to predict whether a customer will churn based on these attributes.

#### Key Features in the Dataset:
- **Demographics:** Gender, Senior Citizen, Partner, Dependents.
- **Service-Related:** Phone Service, Internet Service (DSL/Fiber), Streaming Services, Tech Support.
- **Contractual:** Contract Type (Month-to-Month, One-Year, Two-Year), Payment Method, Paperless Billing.
- **Financial:** Monthly Charges, Total Charges.
- **Target Variable:** "Churn" (Yes/No) — indicating whether a customer has left the service.

#### Data Cleaning and Preparation
- I handled missing values using median value of the affected feature to replace the missing values, and ensured that features were well-prepared for analysis.
- The dataset was clean and ready for in-depth analysis and modelling.

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/Summary.png" alt="Displays" width="900" height="600"/>

### Key Insights from Exploratory Data Analysis (EDA)
  1. **Churn Rate Trends:**
     - Customers on **month-to-month contracts** show a significantly higher churn rate.
     - Long-term contracts (one-year, two-year) have lower churn rates, suggesting that contract stability plays a key role in retention.

  2. 	**Impact of Monthly Charges:**

     	- Customers with **higher monthly charges** tend to churn more often.
     	- The average monthly charge among churned customers is noticeably higher than retained customers, suggesting pricing sensitivity.

  3. **Senior Citizens & Churn:**
   
      - **16.2% of customers are senior citizens,** and they have a slightly higher churn rate.
      - This suggests that additional engagement strategies (such as tailored promotions or better customer support) might help retain senior customers.

  4. **Service & Feature Influence:**

      - **Tech Support & Online Security are critical factors in retention**.
      - Customers without these add-ons churn at a much higher rate, emphasizing the need to encourage customers to adopt these services.

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/EDA%201.png" alt="Displays" width="900" height="400"/>
<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/EDA%202.png" alt="Displays" width="800" height="250"/>

#### Correlation Analysis
A correlation matrix revealed that tenure and TotalCharges have a strong positive correlation, indicating that long-term customers tend to spend more. Conversely, MonthlyCharges showed a moderate positive correlation with churn, suggesting that higher monthly charges might be a factor in customer attrition.

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/Corr.png" alt="Displays" width="600" height="400"/>

### Predictive Modeling
#### Feature Engineering
- **Categorical Encoding:** Employed LabelEncoder to encode categorical variables, ensuring the numerical nature of features was preserved.
- **Feature Creation:** Developed new features to enhance the dataset.
- **Effectiveness:** The engineered features significantly improved the models' ability to learn from the data.

#### Model Selection
Eight (8) machine learning models were evaluated, including:
- **Logistic Regression Model**
- **Support Vector Classifier (SVC) Model**
- **XGBClassifier Model**
- **Naive Baye Classifier**
- **SGDClassifier Model**
- **KNeighborsClassifier Model**
- **DecisionTreeClassifier Model**
- **SVC Mode**

**Performance Metrics:**
- **Accuracy:** Measures overall correct predictions.
- **Recall:** Identifies how well we capture actual churned customers.
- **Precision:** Ensures that predicted churns are true positives.
- **F1-Score:** A balance of precision and recall.
The **best-performing model** provided a strong balance between precision and recall, making it suitable for business applications.

#### Handling Class Imbalance
To address the class imbalance, techniques such as SMOTE (Synthetic Minority Over-sampling Technique) and class weighting were employed.

#### Model Training and Validation
- **Initial Model Training:** Established a baseline for model performance.
- **Feature Scaling:** Applied standard scaling techniques to enhance model performance.
- **Class Imbalance:** Addressed class imbalance using techniques such as class weighting, with a focus on improving recall for the positive class (churn).
- **Hyperparameter Tuning:** Conducted hyperparameter tuning to achieve an optimal balance between precision and recall.

#### Model Evaluation
The models were evaluated using confusion matrices, precision, recall, and F1 score, with a focus on reducing false negatives. The Logistic Regression model stood out for its effectiveness in identifying churn cases, aligning well with ConnectTel’s objectives.
- **Accuracy:** 79.7%
- **Precision:** 85.0%
- **Recall:** 88.5%
- **F1-score:** 86.7%
- **AUC-ROC:** 70.9%

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/Score.png" alt="Displays" width="800" height="600"/>

### Actionable Insights
1.	**Retention Strategies for New Customers:** Given that customers with shorter tenures are more likely to churn, targeted retention strategies such as personalized offers and proactive customer support should be implemented for new customers.
2.	**Review Pricing Plans:** The positive correlation between MonthlyCharges and churn suggests that customers find higher monthly charges less appealing. Offering more flexible and competitive pricing plans could help reduce churn.
3.	**Encourage Long-term Contracts:** Customers with longer-term contracts are less likely to churn. Incentivizing customers to opt for annual or biennial contracts could enhance customer retention.
4.	**Enhance Service Offerings:** Features like OnlineSecurity, TechSupport, and StreamingTV showed varying impacts on churn. Enhancing these services and ensuring customer awareness could improve satisfaction and reduce churn.

### Business Implications and Recommendations

- **Encourage Long-Term Contracts:** Offer incentives like discounts or exclusive services to motivate customers to switch from month-to-month to annual contracts, enhancing customer retention.
- **Enhance Customer Support & Tech Services:** Provide free trials or bundle tech support and online security services into plans to reduce churn and improve customer satisfaction.
- **Implement Targeted Retention Campaigns:** Use predictive modeling to identify at-risk customers early and deploy personalized outreach programs (emails, calls, promotions) to boost loyalty and retention.

________________________________________
### Conclusion
Predicting customer churn is essential for telecom businesses to improve retention strategies. By leveraging data science and predictive modeling, **ConnectTel Telecom Company** can proactively identify at-risk customers and implement targeted strategies to enhance customer experience, reduce churn, and boost profitability. This project successfully developed a robust churn prediction model, providing valuable insights and laying a strong foundation for future customer retention efforts. The journey from raw data to actionable insights highlights the importance of data-driven decisions and the power of machine learning in real-world applications.🚀🚀🚀
________________________________________

<br>

### *Kindly share your feedback and I am happy to Connect 🌟*

<img src="https://github.com/jamesehiabhi/ConnectTel-Churn-Prediction/blob/main/Displays/My%20Card1.jpg" alt="Displays" width="600" height="150"/>
