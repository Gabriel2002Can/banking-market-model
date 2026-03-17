# Banking Market Model

A Machine Learning Approach to Predict Customer Response in Banking Campaigns

## Project Overview

This project focuses on building a predictive machine learning model to identify potential customers who are most likely to subscribe to a term deposit.

The goal is to help financial institutions optimize marketing strategies, reduce unnecessary outreach costs, and improve campaign efficiency through data-driven decision-making.

## Key Objectives

- Analyze customer demographic and behavioral data

- Identify patterns influencing campaign success

- Build and evaluate predictive models

- Provide actionable insights for targeted marketing

## Problem Statement

Marketing campaigns in the banking sector often involve contacting a large number of customers with relatively low conversion rates.

This project aims to answer:

***“Which customers are most likely to respond positively to a banking campaign?”***

## Dataset Description

### Dataset Preview

Below is a snapshot of the dataset showing the first few records:

| age | job           | marital | education | default | balance | housing | loan | contact | day | month | duration | campaign | y  |
|-----|--------------|---------|-----------|---------|---------|---------|------|---------|-----|-------|----------|----------|----|
| 58  | management    | married | tertiary  | no      | 2143    | yes     | no   | unknown | 5   | may   | 261      | 1        | no |
| 44  | technician    | single  | secondary | no      | 29      | yes     | no   | unknown | 5   | may   | 151      | 1        | no |
| 33  | entrepreneur  | married | secondary | no      | 2       | yes     | yes  | unknown | 5   | may   | 76       | 1        | no |
| 47  | blue-collar   | married | unknown   | no      | 1506    | yes     | no   | unknown | 5   | may   | 92       | 1        | no |
| 33  | unknown       | single  | unknown   | no      | 1       | no      | no   | unknown | 5   | may   | 198      | 1        | no |

The dataset contains information about:

- Customer demographics (age, job, marital status, etc.)

- Financial attributes (balance, loans, etc.)

- Campaign-related details (contact type, duration, previous interactions)

### Customer Distribution

The dataset presents a **highly imbalanced distribution** between subscribed and non-subscribed clients.

- Approximately 92.8% of customers did not subscribe to the banking product

- Only 7.2% of customers subscribed

<img width="468" height="406" alt="Screenshot_1" src="https://github.com/user-attachments/assets/eb72035e-1ffa-41bb-b7e6-bdddabf25e5d" />

This imbalance highlights a common challenge in marketing datasets, where positive responses are relatively rare.

From a machine learning perspective, this has important implications:

- Models may become biased toward predicting the majority class (non-subscribers)

- Accuracy alone is not a reliable metric for evaluation

- Metrics such as precision, recall, and F1-score become more relevant

- Techniques like resampling, class weighting, or threshold tuning may be necessary

Overall, this distribution reinforces the importance of building a model that can effectively identify the minority class (potential subscribers), which is the key objective of this project.

## Project Workflow

### 1. Data Collection

- Imported dataset from a structured CSV source

- Loaded data using pandas

### 2. Data Preprocessing

- Encoded categorical variables

- Normalized/standardized numerical features

### 3. Model Development

Implemented and compared multiple machine learning models:

- Random Forest

- **Gradient Boosting / XGBoost (Choosen Model)**

### 4. Model Evaluation

Models were evaluated using:

- Accuracy

- **Precision & Recall**

- F1 Score

- **Confusion Matrix**

<img width="511" height="447" alt="Screenshot_2" src="https://github.com/user-attachments/assets/97d2c688-e952-4201-9e25-81219c33392a" />

**Key observations:**

- The model correctly classified `8,532` **non-subscribers** and `565` **subscribers**.
- `152` **actual subscribers were incorrectly classified as non-subscribers**, representing missed opportunities to identify potential customers.
- `751` **non-subscribers were predicted as subscribers**, producing false positives.

Overall, the confusion matrix suggests that the model generalizes well, maintaining similar prediction patterns between training and test sets while still prioritizing the detection of potential subscribers.

### 5. Model Optimization

- Cross-validation

- **Feature importance analysis**

<img width="1250" height="1173" alt="Screenshot_3" src="https://github.com/user-attachments/assets/a7ef1756-56cc-4bb6-9f97-fffbdb660c45" />

### 6. Final Model Selection

- Selected the best-performing model based on evaluation metrics

- Ensured generalization on unseen data

## Results & Insights

- Identified key factors influencing customer decisions

- Improved prediction accuracy compared to baseline

- Demonstrated how **targeted marketing** can significantly increase efficiency

## Tech Stack

- **Programming Language:** Python

- Libraries:

    - pandas

    - scikit-learn

    - matplotlib / seaborn

- **Environment:** Jupyter Notebook

## How to Run the Project

1. Clone the repository:

```
git clone https://github.com/Gabriel2002Can/banking-market-model.git
```

2. Navigate to the project directory:

```
cd banking-market-model
```

3. Install dependencies:

```
pip install -r requirements.txt
```

4. Run the notebook or script:

```
jupyter notebook
```

## Key Learnings

- Trade-offs between model complexity and interpretability

- The trade-off between accuracy and recall

- The impact of imbalanced datasets on performance metrics

- Real-world applicability of machine learning in finance

## Challenges Faced

- Handling imbalanced data

- Balancing model performance with interpretability

## Conclusion

This project demonstrates the practical application of machine learning in solving real-world business problems in the banking sector.

By leveraging predictive modeling, this solution enables:

- More efficient marketing campaigns

- Better customer targeting

- Increased return on investment (ROI)

## Author

**Gabriel Portella** - *Software Developer*

Passionate about Machine Learning & Data Science

## Final Note for Recruiters

This project demonstrates my ability to:

- Design and implement an end-to-end machine learning pipeline

- Work with real-world, imbalanced datasets and apply appropriate evaluation strategies

- Extract meaningful insights to support business decision-making

- Write clean, modular, and maintainable code

The primary focus of this project was not only model performance, but also understanding the problem context and delivering practical value through data.
