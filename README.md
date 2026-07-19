
 # 🛡️ Financial Fraud Detection Using Machine Learning


# 📖 Project Overview

Financial fraud continues to be one of the biggest challenges faced by banks and financial institutions. Traditional rule-based systems often struggle to detect increasingly sophisticated fraud patterns while maintaining low false positive rates.

This project consists in performing a data analysis with the focus to identify which AI driven technique is the most effective in detecting financial fraud .The 5 pedictive machine learning models chosen to analyse the effectiveness of predictive analytics techniques in detecting  and preventing fraud 

within financial institutions were: Random Forest, XG Boost, Logistic Regression, Neutral Network and Gradient Boosting.

The analysis and evaluation of the project was developed in **Phython (Google Colab)** , including data preprocessing, feature engineering, class balancing with SMOTE, model training, evaluation, and feature importance analysis.



# 🎯 Project Objectives

- Analyse the effectiveness of predictive analytics techniques in detecting 
- Evaluate the measurable impact of predictive analytics on the overall business performance.
- Address severe class imbalance using SMOTE.
- Compare the performance of multiple machine learning models.
- Evaluate models using Accuracy, Precision, Recall and F1-Score.
- Identify the most influential predictors of fraudulent transactions.
- Translate technical findings into practical business recommendations.



# 📂 Table of Contents

- [Project Overview](#-project-overview)
- [Business Problem](#-business-problem)
- [Dataset](#-dataset)
- [Data Preparation](#-data-preparation)
- [Machine Learning Models](#-machine-learning-models)
- [Model Evaluation](#-model-evaluation)
- [Feature Importance](#-feature-importance)
- [Results](#-results)
- [Business Insights](#-business-insights)
- [Project Structure](#-project-structure)
- [Technologies Used](#-technologies-used)


- # 💼 Business Problem

Financial fraud remains one of the most significant challenges for banks, insurance companies, and financial institutions worldwide. As digital transactions continue to increase, fraudsters are constantly developing more sophisticated techniques, making traditional rule-based detection systems less effective.

This project investigates how different machine learning algorithms perform when detecting fraudulent financial applications. Rather than focusing solely on overall accuracy, the project evaluates each model's ability to identify fraudulent cases while balancing precision, recall, interpretability, and business value.





# 📊 Dataset

The analysis was performed using a publicly available synthetic financial fraud dataset from Kaggle, representing loan and credit applications submitted within the UK.

| Attribute | Description |
|-----------|-------------|
| Source | Kaggle |
| Records | More than **1,000,000** |
| Target Variable | `fraud_bool` |
| Fraud Rate | **1.1%** |
| Features | 30+ demographic, behavioural and transactional variables |
| Problem Type | Binary Classification |

https://www.kaggle.com/datasets/petermushemi/uk-credit-card-fraud-dataset

### Key Features

Some of the variables used during model training include:

- Customer Age
- Income
- Credit Risk Score
- Housing Status
- Employment Status
- Payment Type
- Device Operating System
- Session Length
- Number of Previous Addresses
- Phone Validation
- Email Similarity Score
- Proposed Credit Limit



# ⚙️ Data Preparation

Several preprocessing techniques were applied to improve data quality and prepare the dataset for machine learning.

### Data Cleaning

- Reviewed descriptive statistics
- Investigated outliers
- Created an `age_extreme` feature for unrealistic ages
- Preserved all observations to avoid unnecessary information loss

### Feature Engineering

- Label encoded categorical variables
- Standardised numerical features where appropriate
- Selected relevant predictors for model training

### Handling Class Imbalance

The dataset contained only **1.1% fraudulent observations**, making fraud detection particularly challenging.

To address this issue, the **Synthetic Minority Oversampling Technique (SMOTE)** was applied exclusively to the training dataset, generating synthetic fraud cases while preventing data leakage.



# 🤖 Model Development

Four supervised machine learning algorithms were implemented and compared to evaluate their effectiveness in detecting fraudulent financial applications. Each model offers different strengths in terms of predictive performance, interpretability, and computational complexity.

| Model | Purpose |
|--------|---------|
| **Logistic Regression** | Baseline classification model with high interpretability and fast training. |
| **Random Forest** | Ensemble learning algorithm capable of capturing complex, non-linear relationships while reducing overfitting. |
| **XGBoost** | Gradient boosting algorithm designed for high predictive performance and efficient handling of structured datasets. |
| **Neural Network** | Deep learning model capable of learning complex fraud patterns through multiple hidden layers. |

All models were trained using the SMOTE-balanced training dataset and evaluated on the same unseen test dataset to ensure a fair comparison.


# 📊 Model Evaluation

The performance of each machine learning model was assessed using four standard classification metrics.

| Metric | Description |
|--------|-------------|
| **Accuracy** | Percentage of correctly classified observations. |
| **Precision** | Measures how many predicted fraud cases were actually fraudulent. |
| **Recall** | Measures how many actual fraud cases were successfully detected. |
| **F1-Score** | Harmonic mean of Precision and Recall, providing a balanced evaluation. |


# 🤖 Machine Learning Models

## Logistic Regression

Logistic Regression was selected as the baseline classification model due to its simplicity, transparency, and ease of interpretation. Despite its lower overall accuracy, it achieved the highest fraud recall among all evaluated models, making it effective at identifying fraudulent applications.

### Classification Report

<img width="468" height="199" alt="image" src="https://github.com/user-attachments/assets/398b0284-6af4-4932-9f04-0b7f29d7e3d2" />


### Confusion Matrix

<img width="546" height="455" alt="image" src="https://github.com/user-attachments/assets/ce771990-e4b2-4618-a7cd-62b42ccaa45c" />



### Key Takeaways

✅ Highest fraud detection rate (Recall)

✅ Highly interpretable model

❌ Generated a large number of false positives

💼 Best suited for environments where detecting fraud is prioritised over reducing manual investigations.


# 🌲 Random Forest

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve prediction accuracy while reducing overfitting. The model demonstrated excellent performance in recognising legitimate applications but struggled to identify the minority fraud class despite the application of SMOTE.

### Classification Report

<img width="422" height="191" alt="image" src="https://github.com/user-attachments/assets/439d6686-3758-47ed-b6ae-afd9639ebe5f" />

### Confusion Matrix

<img width="546" height="455" alt="image" src="https://github.com/user-attachments/assets/105e5617-274e-4926-8269-7373e65e1997" />



### Key Takeaways

✅ Excellent performance on legitimate applications

✅ Robust ensemble model with low risk of overfitting

✅ Provides feature importance for model interpretation

❌ Low fraud detection rate (Recall)

💼 Best suited for scenarios where minimising false positives is important, although additional techniques are required to improve fraud detection.



# ⚡ XGBoost

XGBoost is a gradient boosting algorithm designed for high predictive performance and efficiency. It achieved one of the highest overall accuracies in this project and performed exceptionally well when classifying legitimate applications. However, similar to Random Forest, the model found it challenging to detect fraudulent cases due to the severe class imbalance.

### Classification Report

<img width="435" height="190" alt="image" src="https://github.com/user-attachments/assets/96ec2c2b-d23e-4dd9-979d-25df101cd80a" />


### Confusion Matrix

<img width="533" height="455" alt="image" src="https://github.com/user-attachments/assets/3fef8814-0d8e-4cd0-b77a-361d6142a5ac" />



### Key Takeaways

✅ Highest overall predictive accuracy

✅ Efficient algorithm for large structured datasets

✅ Strong feature importance interpretation

❌ Missed a significant proportion of fraudulent applications

💼 Well suited for large-scale financial datasets where speed and predictive performance are essential, but additional optimisation is required for fraud detection.



# 🧠 Neural Network

The Neural Network model was implemented to capture complex non-linear relationships within the data. Although it achieved high overall accuracy, its greatest strength was improving fraud detection compared to the tree-based models while maintaining strong performance on legitimate applications.

### Classification Report


<img width="432" height="193" alt="image" src="https://github.com/user-attachments/assets/75708822-f443-48c8-8551-92aae8e03920" />


### Confusion Matrix

<img width="533" height="455" alt="image" src="https://github.com/user-attachments/assets/fcc11e5d-c831-4140-b83d-0bfd1669de1c" />


### Key Takeaways

✅ Better fraud detection than Random Forest and XGBoost

✅ Learns complex non-linear fraud patterns

✅ Strong performance on legitimate applications

❌ Lower interpretability compared to traditional machine learning models

💼 Suitable for organisations prioritising fraud detection capability, provided explainability and governance requirements are also considered.




# 🏆 Model Comparison

The four machine learning models demonstrated different strengths depending on the evaluation metric. While Random Forest and XGBoost achieved the highest overall accuracy, Logistic Regression provided the highest fraud recall, making it the most effective model for identifying fraudulent applications. The Neural Network offered a balance between predictive performance and fraud detection capability.

<img width="578" height="215" alt="image" src="https://github.com/user-attachments/assets/5007c4d1-bb2d-40b8-baec-be7e67c71a66" />

<p align="center">
<img src="images/model_comparison.png" width="850">
</p>


# 🔍 Feature Importance

Understanding which variables influence fraud predictions is essential for both model interpretability and business decision-making.

Feature importance analysis was performed to identify the variables that contributed most to each machine learning model.

## Logistic Regression

<img width="962" height="547" alt="image" src="https://github.com/user-attachments/assets/74fe94df-beca-48aa-817e-052e2768a34d" />



## Random Forest

<img width="1041" height="547" alt="image" src="https://github.com/user-attachments/assets/68d8c75b-0cf9-45da-8788-08ba4d7d399c" />




## XGBoost

<img width="955" height="547" alt="image" src="https://github.com/user-attachments/assets/7877d902-dbb9-42f8-955d-4fb889267bf8" />



# 🏆 Overall Findings\ Results

This project demonstrates that Artificial Intelligence and predictive analytics can significantly enhance fraud detection within financial institutions. However, the findings also highlight that no single model is universally optimal, and model selection should be guided by the organisation's strategic objectives.

Key findings include:

- 🥇 **Logistic Regression** achieved the highest Recall, making it the most effective model for identifying fraudulent applications where minimising undetected fraud is the primary objective.
- 🌲 **Random Forest** delivered the best balance between predictive accuracy and operational efficiency, providing strong business value while maintaining low false positive rates.
- ⚡ **XGBoost** achieved high predictive accuracy and demonstrated its suitability for large-scale structured financial datasets.
- 🧠 **Neural Networks** improved fraud detection compared to some traditional models but offered lower interpretability, making governance and regulatory compliance more challenging.



# 💼 Business Insights

This project demonstrates that Artificial Intelligence and predictive analytics can significantly strengthen fraud detection within financial institutions. However, the findings show that no single machine learning model is universally superior, and model selection should depend on an organisation's operational priorities, available resources, and regulatory requirements.

### Key Insights

- 🤖 **Artificial Intelligence improves fraud detection** by identifying complex patterns that traditional rule-based systems may fail to detect, supporting faster and more informed decision-making.

- 📊 **Evaluation metrics should extend beyond Accuracy.** In highly imbalanced fraud datasets, Recall, Precision, and F1-Score provide a more meaningful assessment of model performance than Accuracy alone.

- 🛡️ **Logistic Regression achieved the highest Recall**, making it the most effective model for identifying fraudulent applications. Its simplicity, transparency, and low computational requirements also make it an attractive solution for organisations with limited technical resources or strict explainability requirements.

- 🌲 **Random Forest provided the strongest balance between predictive accuracy and operational efficiency.** Although its fraud detection capability was limited, its interpretability through feature importance makes it valuable for supporting business decision-making.

- ⚡ **XGBoost demonstrated excellent predictive performance** on legitimate applications and is well suited to analysing large structured datasets. However, further optimisation is required to improve its ability to detect minority fraud cases.

- 🧠 **Neural Networks captured complex fraud patterns** but presented lower interpretability and greater implementation complexity. These characteristics may limit adoption in highly regulated financial environments where transparency is essential.

- ⚖️ **Successful AI adoption requires balancing predictive performance with interpretability, operational costs, and regulatory compliance.** Financial institutions should select models that align with their fraud prevention strategy rather than relying on a single performance metric.



# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow
- XGBoost
- Imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn
- Google Colab
- Git & GitHub








