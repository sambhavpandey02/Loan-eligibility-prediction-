# Loan Eligibility Prediction: A Classification Model Analysis

## Project Overview
This project is an IBM SPSS Modeler analysis designed to assess preliminary bank loan applications for approval or rejection. By analyzing historical data to uncover financial and demographic patterns in previous applications, the project yields a classification model capable of predicting `Loan_Status` as either 'Y' or 'N'. 

## Data & Preparation
* **Dataset:** The raw data contains 13 fields encompassing various applicant details and financial metrics.
* **Data Audit:** An initial data audit revealed missing values within the `Credit_History` and `Self_Employed` fields.
* **Data Cleaning:** To ensure model integrity, incomplete records were filtered out using a Select node configured with the condition `not(@NULL(Credit_History))`.

## Project Workflow
The SPSS Modeler stream follows a six-step process:
1. Import data via the Var. File node.
2. Clean missing values using the Select node.
3. Define the Target status in the Type node.
4. Split data partitions using the Partition node.
5. Train the classification model.
6. Evaluate the predictions via Analysis nodes.

## Data Partitioning & Modeling
The dataset was divided to ensure accurate evaluation:
* **Training Set (80%):** 268 records were utilized to teach the model the underlying applicant patterns.
* **Testing Set (20%):** 83 records were held back to evaluate the model's predictive accuracy.

**Algorithm Details:**
The project utilizes a CHAID Decision Tree, which builds decision rules using Chi-squared Automatic Interaction Detection. The model identified `Credit_History` as the primary key driver (predictor) for loan approval, while `CoapplicantIncome` and `Property_Area` serve as influential secondary factors.

## Results & Performance
* **Training Performance:** The model achieved an 82.46% accuracy rate on the training data (221 correct out of 268 records).
* **Testing Performance:** The model achieved a 90.36% accuracy rate on unseen testing data (75 correct out of 83 records).
* **Error Rate:** The final testing error rate was 9.64%, with only 8 incorrect predictions.

## Conclusion
The generated confusion matrix confirms precise model performance across both 'Y' and 'N' target classes. The CHAID workflow successfully generates highly accurate loan eligibility predictions. Ultimately, this model is deployable to fast-track reliable applications, supporting—rather than replacing—human financial judgment.
