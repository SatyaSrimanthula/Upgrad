**What is Credit Card Fraud?**

Credit card fraud occurs when an individual uses someone else’s credit card or account information without permission to make unauthorized purchases or withdraw funds through cash advances. It can happen both online and in physical stores. As a business owner, you can protect yourself from potential headaches and negative publicity by being vigilant and identifying instances of fraudulent credit card usage in your payment system.

**Three challenges surrounding Credit Card Fraud**

It’s not always easy to agree on the ground truth of what “fraud” means.
Regardless of how you define ground truth, the vast majority of charges are not fraudulent.
Most merchants aren’t experts at evaluating the business impact of fraud.
Problem Statement:
The objective of Credit Card Fraud Detection is to accurately identify fraudulent transactions from a large pool of credit card transactions by building a predictive model based on past transaction data. The aim is to detect all fraudulent transactions with minimum false alarms.

**Observations**

The dataset is highly imbalanced, with only 0.172% of observations being fraudulent.
The dataset consists of 28 transformed features (V1 to V28) and two untransformed features (Time and Amount).
There is no missing data in the dataset, and no information about the original features is provided.
Why does class imbalance affect model performance?
In general, we want to maximize the recall while capping FPR (False Positive Rate), but you can classify a lot of charges wrong and still maintain a low FPR because you have a large number of true negatives.
This is conducive to picking a relatively low threshold, which results in a high recall but extremely low precision.
What is the catch?
Training a model on a balanced dataset optimizes performance on validation data.
However, the goal is to optimize performance on the imbalanced production dataset. You ultimately need to find a balance that works best in production.
One solution to this problem is: Use all fraudulent transactions but subsample non-fraudulent transactions as needed to hit our target rate.
Business questions to brainstorm:
Since all features are anonymous, we will focus our analysis on non-anonymized features: Time, Amount

How different is the amount of money used in different transaction classes?
Do fraudulent transactions occur more often during certain frames?
