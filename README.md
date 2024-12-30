# Survival Analysis Using Cox Proportional Hazard Regression and Survival Support Vector Machine in Case of Financial Distress in the Consumer Goods Industry Sector
A financial crisis poses significant challenges for companies, especially during global economic disruptions like the Covid-19 pandemic. The consumer goods sector has been particularly affected due to decreased demand and sales. If not managed properly, this can lead to financial distress, a condition where a company faces severe financial difficulty, potentially leading to bankruptcy.

## Overview
- Cox Proportional Hazard (Cox PH) Regression: This method is used to determine which factors significantly affect the risk of financial distress. Key factors analyzed include Debt-to-Asset Ratio (DAR), Current Ratio (CR), company age, size, Gross Profit Margin (GPM), Net Profit Margin (NPM), and Cash Ratio.
- Survival SVM: This model is employed to find the best kernel for classifying companies into high risk and low risk categories based on their survival probability over time.

Key Steps in the Analysis
1. Data Preprocessing:
   - Data normalization and scaling were applied to important financial indicators.
   - The data was examined for missing values and cleaned before being analyzed.
2. Kaplan-Meier Estimator:
   - Kaplan-Meier curves were plotted to visualize survival probabilities based on different financial ratios like DAR, CR, GPM, etc.
   - Log-rank tests were performed to check for significant differences between groups.
3. Cox PH Regression:
   - A Cox Proportional Hazards model was fit to the data to identify which financial indicators significantly impact the likelihood of financial distress.
   - Proportional hazards assumption was tested using Schoenfeld residuals.
4. Survival SVM:
   - Different SVM models (linear, additive, and RBF kernels) were applied to classify companies based on their financial distress risk.
   - Hyperparameter tuning was done using grid search to optimize kernel parameters.

## Key Libraries Used
Python: pandas, matplotlib, lifelines, sklearn
R: survival, survivalsvm, mlr3verse

## Key Findings
1. From the observation of 59 companies in the consumer goods industry sector, 30.5% (18 companies) did not experience financial distress, while 69.5% (41 companies) experienced financial distress during the period from the first quarter of 2020 to the third quarter of 2023.
2. The Cox Proportional Hazard Regression model obtained is:
   h(x)=h_0 (t)  exp⁡(0.289X_1-0.385X_5-0.271X_6 )
   with corresponding hazard ratios of 1.335, 0.680, and 0.762, respectively. Here, X_1  represents the Debt to Asset Ratio (DAR), X_5 represents company age, and X_6 represents the Net Profit Margin (NPM).
3. In grouping financial distress using the Survival Support Vector Machine method, the best kernel identified was the RBF kernel, with a concordance index (c-index) value of 0.99393.
4. Based on the calculated c-index values, the Survival Support Vector Machine model achieved a c-index of 99.393%, which outperformed the Cox Proportional Hazard model’s c-index of 78.4%.
