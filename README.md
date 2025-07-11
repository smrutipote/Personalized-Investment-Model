Personalized Investment Recommendation System
📌 Project Objective
The goal of this project is to enhance customer satisfaction in the banking domain by providing personalized investment recommendations based on customer segmentation using machine learning techniques.

🗃️ Dataset Overview
The dataset includes financial and demographic attributes of bank customers:

Age

Gender

Marital Status

Education Level

Dependents

Location

Occupation

Credit Score

Monthly Average Balance

Number of Transactions Per Month

Average Transaction Value

Online Banking Usage

ATM Usage

Investment Horizon

Risk Tolerance

Feedback by Customer

Existing Bank Products

🧹 Data Preprocessing Steps
Dropped Irrelevant Columns: Removed Unnamed: 0 and CustomerID.

Identified Categorical and Numerical Columns.

Exploratory Data Analysis (EDA):

Used .info(), .describe(), and boxplots for data understanding and outlier detection.

Outlier Treatment:

Replaced extreme values in Age, CreditScore, MonthlyAverageBalance, NumberOfTransactionsPerMonth, and AverageTransactionValue using quantile-based capping or median replacement.

Missing Value Imputation:

Numerical columns → KNNImputer

Categorical columns → SimpleImputer (Most Frequent strategy)

Encoding Categorical Features:

Used OrdinalEncoder with a defined category order.

Feature Scaling:

Applied both MinMaxScaler and StandardScaler based on analysis stage (clustering or SHAP explanation).

📊 Clustering Methodology
Algorithm Used:
KMeans Clustering

Evaluation Metrics:
WCSS (Within-Cluster Sum of Squares)

Silhouette Score

Davies-Bouldin Index

Calinski-Harabasz Index

Cluster Range Tested:
From 2 to 14 clusters.

Optimal cluster count: 4, based on balanced evaluation metrics.

📌 Feature Importance (Using SHAP)
To interpret cluster characteristics, a RandomForestClassifier was trained on each scaled dataset (Standard/MinMax).

SHAP (SHapley Additive exPlanations) values were computed.

Most important features across clusters:

Occupation

Monthly Average Balance

Number of Transactions Per Month

Age

Marital Status

Existing Bank Products

SHAP Visualizations:
Summary plots were generated for each cluster to show influential features.

📈 Cluster Visualization
2D scatter plots were created for the most significant features:

Age vs Marital Status

Gender vs Age

Dependents vs Age

These visualizations help understand how clusters are formed around these attributes.

📦 Output
Final scaled dataset saved as Preprocessed_df.csv

Cluster predictions were added as check cluster and check cluster2 columns.

Cluster-wise product preference analysis revealed key investment product trends for each group.

✅ Conclusion
The project successfully segmented customers using KMeans clustering.

Applied SHAP for model interpretability to guide tailored product recommendations.

The approach equips financial institutions to offer personalized investment products based on key attributes like occupation, balance, and transaction behavior.

📁 Files
Encoded.csv: Original encoded features without scaling

Preprocessed_df.csv: Scaled dataset used for clustering

SHAP plots and cluster visualizations are generated dynamically during analysis
