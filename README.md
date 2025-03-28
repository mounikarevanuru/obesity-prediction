# Obesity Type Prediction

## Introduction
This project addresses the critical challenge of obesity classification by predicting obesity levels using machine learning. Obesity is a global public health issue that significantly increases the risk of chronic diseases such as diabetes, cardiovascular conditions, and certain cancers. Early prediction of obesity levels can facilitate timely interventions and promote healthier lifestyles, ultimately reducing the burden on healthcare systems.
The dataset comprises a variety of demographic and lifestyle features including gender, age, height, weight, family history of overweight, dietary habits, physical activity, and more. By leveraging these features, the project aims to accurately classify individuals into different obesity categories.
To achieve this, we will implement and compare several classification algorithms:
- **Logistic Regression**
- **Support Vector Machines (SVM)**
- **Decision Trees**
- **Random Forests**

These models provide a robust framework to evaluate different aspects of the classification task and to determine the best performing approach.
### Why is this Project Important?
- **Addressing a Major Health Concern:** Obesity is a leading contributor to several life-threatening diseases. Understanding its determinants is key to developing preventive strategies.
- **Data-Driven Decision Making:** The insights gained from this analysis can assist healthcare professionals and policymakers in designing targeted interventions and personalized treatment plans.
- **Advancement of Predictive Analytics in Health:** By comparing multiple machine learning models, this project contributes to the growing body of research on applying predictive analytics to real-world health data.
The repository includes comprehensive data exploration, preprocessing steps (handling missing values, outlier detection, and feature engineering), and model evaluation using standard performance metrics. This work not only enhances our understanding of obesity factors but also demonstrates practical applications of classification algorithms in solving a real-world problem.

## Dataset
The dataset contains 2,111 records and 17 attributes. Each record represents an individual’s data point and includes features related to their lifestyle, eating habits, and physical conditions.
- **Target Variable:**  
  The target variable is **NObesity (Obesity Level)**. It classifies individuals into one of seven categories:
  - Insufficient Weight
  - Normal Weight
  - Overweight Level I
  - Overweight Level II
  - Obesity Type I
  - Obesity Type II
  - Obesity Type III
- **Data Sources:**  
  - **Synthetic Data (77%):**  
    A significant portion of the data has been synthetically generated using the Weka tool along with the SMOTE filter to create a balanced dataset. This approach is typically used to address class imbalance issues.
  - **Real-World Data (23%):**  
    The remaining data was directly collected from users through a web platform, offering authentic real-world observations.
    
## Potential Biases Impacting Model Performance
- **Synthetic Data Generation:**  
  While SMOTE helps balance the classes, the synthetic data might not capture all the nuances of real-world interactions between features. There is a risk that the synthetic data could introduce artifacts or exaggerate certain patterns that do not fully represent natural variability.
- **Sampling Bias:**  
  The real-world portion is collected via a web platform, which may lead to self-selection bias. Individuals who choose to provide their data might not be representative of the overall population.
- **Geographical Bias:**  
  The dataset is limited to individuals from Mexico, Peru, and Colombia. As a result, conclusions or models built using this data may not generalize well to populations in other regions.

  ## Data Preprocessing
   - Checked for and handled missing values in both numerical and categorical columns.
   - Checked for outliers - there are none in the dataset.
   - Renamed abstract columns names to meaningful ones.  
   - Removed duplicate records to ensure data integrity.
   - Converted values (for example, rounding the Weight and Age column to a precision of 1 digit).
   - Replaced numeric codes with descriptive string labels for features such as "Frequency of consumption of vegetables," "Number of main meals," "Daily water intake," "Physical activity frequency," and "Time using technology devices."
   - Checked for correlated features. Weight and Height have moderate positive correlation but no other significantly correlated features.
 
  ## Feature Engineering
- **Target Transformation:**  
  The obesity level target is converted into numerical labels using LabelEncoder.

- **Feature Scaling:**  
  StandardScaler is applied to features like Age, Height, and Weight to ensure consistent ranges and prevent any single feature from dominating the model.

- **Ordinal Encoding:**  
  For ordinal features (e.g., responses such as 'never', 'sometimes', 'always'), OrdinalEncoder is used to maintain their inherent order.

- **One-Hot Encoding:**  
  Non-ordinal categorical features are transformed with OneHotEncoder to avoid implying any order among the categories.

