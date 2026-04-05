# Customer_Behaviour_Intelligence_System

## Project Overview
This project focuses on predicting **customer churn** using machine learning. The goal is to identify customers likely to leave a service and provide insights to improve retention strategies.  

The project uses the **IBM Telco Customer Churn Dataset** from Kaggle and applies both unsupervised and supervised learning methods.

---

## Dataset
- Source: [IBM Telco Customer Churn Dataset - Kaggle](https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset)  
- Features include: customer demographics, account information, services subscribed, and payment methods.  
- Target variable: `Churn` (Yes/No)  

**Key preprocessing steps:**
- Dropped irrelevant features: `State`, `Country`, `City`, `Zip code`, `Churn Reason`, `CLTV`, `Churn Score`  
- Handled missing values and converted categorical features into numeric encodings.  

---

## Unsupervised Learning
- Initially explored the data using clustering to understand customer segments.  
- Used clustering algorithms to observe patterns in customer behavior.  

---

## Supervised Learning

### Models Applied
1. **Logistic Regression**  
2. **Decision Tree**  
3. **Random Forest**  
4. **Support Vector Machine (SVM)**  

### Hyperparameter Tuning
- Random Forest: tuned `max_depth` and `n_estimators` to find optimal performance.  
- SVM: tested different kernels (`linear`, `rbf`, `poly`, `sigmoid`) and selected the best based on F1-score.  

### Model Evaluation Metrics
- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-score**  
- **Confusion Matrix**  


> **SVM was selected as the final predictive model** due to the highest F1-score. However, Random Forest was used for Feature importance and interpretation.  

---

## Confusion Matrix (SVM)

|               | Predicted No | Predicted Yes |
|---------------|-------------|---------------|
| Actual No     | 1371        | 154           |
| Actual Yes    | 247         | 341           |

- **True Positives (TP):** 341 → Correctly predicted churn  
- **False Negatives (FN):** 247 → Missed churn (critical)  
- **True Negatives (TN):** 1371 → Correctly predicted non-churn  
- **False Positives (FP):** 154 → Predicted churn incorrectly  

> Focus on reducing **false negatives** to improve customer retention.

---

## Feature Importance (Random Forest)

Top features influencing churn:

 ### Feature                       

1.Tenure Months                          
2.Internet Service – Fiber Optic          
3.Dependents                             
4.Total Charges                          
5.Payment Method – Electronic Check

### Business Insights
1. **Tenure Months:** New customers are more likely to churn → improve onboarding.  
2. **Internet Service – Fiber Optic:** Fiber users churn more → improve service quality.  
3. **Dependents:** Customers with dependents are less likely to churn → family-focused plans.  
4. **Total Charges:** Higher charges increase churn → flexible pricing/discounts.  
5. **Payment Method – Electronic Check:** Certain payment methods increase churn → encourage auto-pay.  

> Random Forest was used here for interpretability and deriving actionable insights, while SVM was used for prediction.

---

## Conclusion
- **SVM** is the best model for predicting customer churn due to highest F1-score.  
- **Random Forest** provided important insights into the features affecting churn.  
- Business strategies can be derived from these insights, such as:
  - Improving onboarding for new customers  
  - Offering family-oriented plans  
  - Adjusting pricing strategies  
  - Promoting convenient payment methods  

This system helps businesses **proactively identify churn risks** and make data-driven decisions to improve customer retention.

---

## Future Enhancements
- Improve recall to reduce false negatives  
- Combine SVM with ensemble methods for even better performance  
- Include additional behavioral features for more detailed insights  

---

## References
- [IBM Telco Customer Churn Dataset - Kaggle](https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset)
- Scikit-learn documentation: https://scikit-learn.org/  

---

## Author
PRINCY JAIN
