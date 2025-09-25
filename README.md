# Customer Churn Prediction for a Telecom Provider Using XGBoost Classifier
##  Objective  
The goal of this project is to build a predictive model to identify customers likely to churn, enabling proactive retention strategies for a telecom provider.

---

##  Methodology

- **Initial Model**  
  Started with *Logistic Regression* as a baseline. After evaluating its performance, it was found to be insufficient for capturing complex churn patterns.

- **Final Model**  
  Implemented *XGBoost Classifier*, a powerful gradient boosting algorithm known for handling structured data and imbalanced classes effectively.

- **Hyperparameter Tuning**  
  Used `GridSearchCV` to optimize key parameters such as `max_depth`, `learning_rate`, `n_estimators`, and `subsample`, resulting in improved model accuracy.


##  Model Performance

- **Best Cross-Validated Accuracy**: `75.00%`  
- **Test Set Accuracy**: `68.33%`
- the Model Does Well at predicting churn on Customer Category 2.0 (E-Service) and 3.0 (Plus Service): The   predicted churn distribution closely matches the actual churn
- the Model Struggles : Customer Category 1.0 (Basic Service): The model seems to overpredict churn—it       shows more churned customers than actually exist. This could mean it's too sensitive to features common    in this group, when in reality these customers are more loyal.


##  Churn Insights by Customer Category

- **Category 1.0 (Basic Service)**  
  High predicted churn, aligned with actual data. Customers in this group have short tenure and limited service usage—churn is expected.

- **Category 3.0 (Plus Service)**  
  Balanced predictions and low churn rates. These customers appear more loyal and satisfied with their service level.

- **Category 4.0 (Total Service)**  
  Surprisingly high churn despite being premium users. Analysis revealed limited service usage and short tenure, suggesting dissatisfaction with service quality.

 ## diagnostically
 - Unexpectedly, Customer Category 4.0 (Total Service)– has limited use of services (longmon, tollmon,loglong , etc.), which is not expected
   given the high category segmentation and the presence of internet, e-bill, and equipment
   features among these customers. They might be leaving due to problems with the service
   or dissatisfaction with its quality. Their short tenure (number of months the customer
   has been with the company) could support this.
 - In the same context, Category 1.0 (Basic Service):– has limited use of services, but this is totally normal and expected based on the short
   subscription period (tenure) and the lower usage of services compared to the other three
   classifications

   
###  Business Actions
-  Investigate Category 4.0 Churn Causes These are high-value customers with unexpectedly low usage. Consider surveying them or analyzing service complaints, tenure, and satisfaction scores.

- Reinforce loyalty for Category 3.0 Since Plus Service customers show loyalty, reinforce it with targeted retention offers or upsell strategies.

- Monitor Category 1.0 Behavior Closely Basic Service users churn frequently, but that’s expected. Focus on onboarding and early engagement to extend tenure and reduce early exits
