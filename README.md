# **INTEGRATED RETAIL ANALYTICS FOR STORE OPTIMIZATION AND DEMAND FORECASTING**
---

## **PROJECT OVERVIEW**
---

This project focuses on analyzing retail sales data to understand sales trends, segment stores, identify unusual sales patterns, and predict future weekly sales using machine learning.

The project integrates sales, store information, and external features to generate insights that can support inventory planning, demand forecasting, and data-driven retail decisions.

## **PROBLEM STATEMENT**
---

Retail businesses need to understand how sales vary across stores, departments, seasons, holidays, and external economic conditions. Without effective analysis and forecasting, businesses may face inventory shortages, overstocking, and inefficient promotional strategies.

This project uses data analytics and machine learning to explore these challenges and identify opportunities for improving retail operations.

## **OBJECTIVES**
---

- Analyze weekly sales patterns across stores and departments.
- Perform data cleaning and exploratory data analysis.
- Investigate missing values and unusual sales observations.
- Analyze relationships between sales and store or external features.
- Build machine learning models to predict weekly sales.
- Segment stores using K-Means clustering.
- Derive business insights for inventory planning and store optimization.

## **DATASETS**
---

The project uses three datasets:

**1. Sales Dataset**

Contains weekly sales information for different stores and departments.

**2. Features Dataset**

Contains additional information such as temperature, fuel prices, consumer price index (CPI), unemployment, markdowns, and holiday indicators.

**3. Stores Dataset**

Contains store-level information, including store type and size.

The datasets are combined using appropriate keys, including `Store` and `Date`, to create an integrated dataset for analysis.

## **TECHNOLOGIES USED**
---

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Random Forest Regression
- K-Means Clustering
- Google Colab
- GitHub

## **PROJECT WORKFLOW**
---

### **1. DATA LOADING AND EXPLORATION**

- Loaded the sales, features, and stores datasets.
- Examined dataset dimensions, column names, and data types.
- Checked missing values and duplicate records.
- Explored the structure and quality of the data.

### **2. DATA CLEANING AND PREPROCESSING**

- Converted date columns into datetime format.
- Investigated missing values and unusual sales observations.
- Filled missing markdown values with zero under the assumption that they represented no recorded markdown activity.
- Used median imputation for other numeric missing values.
- Created time-based features such as year, month, week, and day.
- Merged the datasets using the appropriate keys.

### **3. EXPLORATORY DATA ANALYSIS (EDA)**

- Analyzed weekly sales distributions and trends.
- Compared sales across stores and departments.
- Investigated holiday-related sales patterns.
- Examined correlations between weekly sales and available numerical features.
- Identified unusually high sales observations for further investigation.

### **4. DEMAND FORECASTING**

A Random Forest Regressor was used to predict weekly sales.

The baseline model used the following features:

- Store
- Department
- Year
- Month
- Week

A second model incorporated additional external features to examine whether they improved prediction performance.

The data was sorted chronologically and divided into training and testing sets to evaluate predictions on later observations.

### **5. STORE SEGMENTATION**

K-Means clustering was applied to group stores according to sales-related characteristics.

The analysis explored differences between clusters based on average sales, total sales, and sales variation. These segments can help identify different store profiles and inform store-specific business strategies.

### **6. MODEL EVALUATION**

The forecasting models were evaluated using:

- **Mean Absolute Error (MAE):** Measures the average absolute difference between actual and predicted sales.
- **Root Mean Squared Error (RMSE):** Measures prediction error while penalizing larger errors more heavily.
- **R² Score:** Measures how much variation in the target is explained by the model.

The clustering results were evaluated using the silhouette score.

## **MODEL RESULTS**
---

### **Random Forest Regression**

| Model | MAE | RMSE |
|---|---:|---:|
| Baseline model | 1,763.74 | 3,806.16 |
| Model with external features | 2,523.79 | 5,728.20 |

The baseline model performed better on the recorded evaluation results because it achieved lower MAE and RMSE values. Adding external features did not improve performance in this experiment.

### **K-Means Clustering**

- Number of clusters: 3
- Recorded silhouette score: approximately 0.55

The clustering analysis suggests that the stores can be grouped into three segments based on the selected sales characteristics.

*Note: Use the final values produced by the notebook you submit if they differ from these recorded results.*

## **KEY FINDINGS AND BUSINESS INSIGHTS**
---

### **1. ANOMALY DETECTION**

The weekly sales analysis identified unusually high sales observations. These may be associated with holidays, promotional activities, or other business events. Such records should be investigated before being treated as errors.

### **2. STORE SEGMENTATION**

The K-Means model grouped stores into three clusters. Understanding the characteristics of each cluster can help businesses tailor inventory and marketing strategies to different store profiles.

### **3. DEMAND FORECASTING**

The baseline Random Forest model achieved better recorded test results than the model incorporating external features. Further feature engineering, model tuning, and validation may help improve forecasting performance.

### **4. CORRELATION ANALYSIS**

Store size showed the highest observed correlation with weekly sales among the features examined, with a correlation coefficient of 0.244. This indicates a positive but relatively weak relationship and suggests that multiple factors may influence sales.

## **BUSINESS RECOMMENDATIONS**
---

- Use historical sales trends and forecasting results to support weekly inventory planning.
- Investigate unusual sales observations before removing them from the dataset.
- Develop inventory and marketing strategies tailored to the characteristics of each store segment.
- Evaluate forecasting models using consistent chronological test periods.
- Further investigate the potential influence of markdowns, holidays, seasonality, and economic indicators on sales.
- Continue improving model performance through feature engineering and hyperparameter tuning.

## **CONCLUSION**
---

This project demonstrates how retail data analytics and machine learning can support sales forecasting, store segmentation, and data-driven business decisions.

By combining sales, store, and external-feature data, the project explores sales trends, evaluates forecasting models, and identifies store segments that may benefit from tailored strategies.

The results also highlight the importance of careful data preprocessing, fair model evaluation, and evidence-based interpretation when using machine learning to support retail operations.
