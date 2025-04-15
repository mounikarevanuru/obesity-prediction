# Obesity Type Classification

## Introduction
This project addresses the critical challenge of obesity classification by predicting obesity levels using machine learning. Obesity is a global public health issue that significantly increases the risk of chronic diseases such as diabetes, cardiovascular conditions, and certain cancers. Early prediction of obesity levels can facilitate timely interventions and promote healthier lifestyles, ultimately reducing the burden on healthcare systems.
The dataset comprises a variety of demographic and lifestyle features including gender, age, height, weight, family history of overweight, dietary habits, physical activity, and more. By leveraging these features, the project aims to accurately classify individuals into different obesity categories.
To achieve this, we will implement and compare three classification algorithms:
- **Logistic Regression**
- **Support Vector Machines (SVM)**
- **Decision Trees**

These models provide a robust framework to evaluate different aspects of the classification task and to determine the best performing approach.
### Why is this Project Important?
- **Addressing a Major Health Concern:** Obesity is a leading contributor to several life-threatening diseases. Understanding its determinants is key to developing preventive strategies.
- **Data-Driven Decision Making:** The insights gained from this analysis can assist healthcare professionals and policymakers in designing targeted interventions and personalized treatment plans.
- **Advancement of Predictive Analytics in Health:** By comparing multiple machine learning models, this project contributes to the growing body of research on applying predictive analytics to real-world health data.
The repository includes comprehensive data exploration, preprocessing steps (handling missing values, outlier detection, and feature engineering), and model evaluation using standard performance metrics. This work not only enhances our understanding of obesity factors but also demonstrates practical applications of classification algorithms in solving a real-world problem.

## Dataset
The dataset contains 2,111 records and 17 attributes. Each record represents an individual’s data point and includes features related to their lifestyle, eating habits, and physical conditions.
https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition

## Original Column Names

The table below shows the original columns as named in the raw dataset, their role (feature vs. target), data type, and a short description of what each represents.

| **Variable Name**                 | **Role**   | **Type**        | **Description**                                                                                                                         |
|-----------------------------------|-----------|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| **Gender**                        | Feature   | Categorical     | Individual’s gender.                                                                                                                    |
| **Age**                           | Feature   | Continuous      | Age of the individual in years.                                                                                                         |
| **Height**                        | Feature   | Continuous      | Height of the individual (in meters or centimeters, depending on the original measurement).                                             |
| **Weight**                        | Feature   | Continuous      | Weight of the individual in kilograms.                                                                                                  |
| **family_history_with_overweight**| Feature   | Binary          | Has a family member suffered or suffers from overweight?                                                                                |
| **FAVC**                          | Feature   | Binary          | Do you eat high caloric food frequently?                                                                                                |
| **FCVC**                          | Feature   | Integer         | Do you usually eat vegetables in your meals?                                                                                            |
| **NCP**                           | Feature   | Continuous      | How many main meals do you have daily?                                                                                                  |
| **CAEC**                          | Feature   | Categorical     | Do you eat any food between meals?                                                                                                      |
| **SMOKE**                         | Feature   | Binary          | Do you smoke?                                                                                                                           |
| **CH2O**                          | Feature   | Continuous      | How much water do you drink daily?                                                                                                      |
| **SCC**                           | Feature   | Binary          | Do you monitor the calories you eat daily?                                                                                             |
| **FAF**                           | Feature   | Continuous      | How often do you have physical activity?                                                                                                |
| **TUE**                           | Feature   | Integer         | How much time do you use technological devices (e.g., cell phone, videogames, television, computer)?                                    |
| **CALC**                          | Feature   | Categorical     | How often do you drink alcohol?                                                                                                         |
| **MTRANS**                        | Feature   | Categorical     | Which transportation do you usually use?                                                                                                        

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

## Features

The Obesity dataset consists of 17 attributes. Below is a table summarizing each feature along with its data type and a brief description of what it represents.

| **Feature Name**                               | **Data Type**                       | **Description**                                                                                              |
|------------------------------------------------|-------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Gender**                                     | Categorical (Nominal)               | Indicates the gender of the individual (e.g., Male, Female).                                                 |
| **Age**                                        | Numeric (Continuous - float)        | Age of the individual in years.                                                                              |
| **Height (cms)**                               | Numeric (Continuous - float)        | Height measured in centimeters (converted from meters and rounded to one decimal place).                       |
| **Weight (kgs)**                               | Numeric (Continuous - float)        | Weight measured in kilograms (rounded to one decimal place).                                                 |
| **Family History with Overweight**             | Categorical (Binary/Nominal)        | Indicates whether there is a family history of overweight.     |
| **Frequent consumption of high caloric food**  | Categorical (Nominal/Binary)        | Reflects the frequency of consuming high-calorie foods.|
| **Frequency of consumption of vegetables**     | Categorical (Ordinal)               | Describes how often vegetables are consumed. |
| **Number of main meals**                       | Categorical (Ordinal)               | Indicates the number of main meals per day.|
| **Consumption of food between meals**          | Categorical (Nominal)               | Indicates whether food is consumed between main meals. |
| **Smoke**                                      | Categorical (Binary/Nominal)        | Indicates the smoking status of the individual. Often stored as Yes/No.                                         |
| **Daily water intake**                         | Categorical (Ordinal)               | Describes daily water consumption. Mapped from codes (e.g., 1: "Less than a liter", 2: "Between 1 and 2 L", 3: "More than 2 L"). |
| **Monitor calories consumption**               | Categorical (Binary/Nominal)        | Indicates whether the individual monitors calorie consumption.                                               |
| **Physical activity frequency**                | Categorical (Ordinal)               | Describes the frequency of physical activity. Mapped from codes such as (0: "I do not have", 1: "1 or 2 days", etc.). |
| **Time using technology devices**              | Categorical (Ordinal)               | Indicates the daily time spent on technology devices. Mapped from codes (e.g., 0: "0–2 hours", 1: "3–5 hours", 2: "More than 5 hours"). |
| **Frequency of alcohol consumption**           | Categorical (Ordinal/Nominal)       | Reflects the frequency of alcohol consumption.   |
| **Transportation used**                        | Categorical (Nominal)               | Describes the mode of transportation used. Underscores are removed for readability and one-hot encoded.         |
| **Obesity (Target Variable)**                  | Categorical (Nominal)               | Represents the obesity level classification across seven categories (e.g., Normal Weight, Obesity Type I, etc.). |


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

- **Ordinal Encoding:**  
  For ordinal features (e.g., responses such as 'never', 'sometimes', 'always'), OrdinalEncoder is used to maintain their inherent order.

- **One-Hot Encoding:**  
  Non-ordinal categorical features are transformed with OneHotEncoder to avoid implying any order among the categories.

## Pipeline Setup and Experimentation
The project leverages scikit-learn's pipeline and ColumnTransformer to streamline preprocessing and model training. The key components of the pipeline setup are as follows:
- **Pipeline Components:**
    - **Preprocessor:**
      - **Numeric Pipeline**
          - Imputer: Handles missing values using the median strategy.
       - **Categorical Pipeline:**
          - Imputer: Fills missing values using the constant strategy, i.e. 'missing'.
          - Encoder: Uses OneHotEncoder for nominal categorical variables, and OrdinalEncoder for ordinal variables.
    - **Model Intergrations:**
      Logistic Regression, SVM (RBF kernel), Decision Trees are embedded into the pipeline to ensure consistent preprocessing across models.

## Experimental Results

Below is a table summarizing the experiments, with model accuracies expressed as percentages:

| **Experiment**                                                    | **Logistic Regression** | **SVM**   | **Decision Tree** |
|-------------------------------------------------------------------|-------------------------|-----------|-------------------|
| **Baseline**                                                      | 92.7%                   | 74.7%     | 94.1%             |
| **Experiment 1 – Feature Engineering: Scaling Features**          | 86.5%                   | 90.5%     | 94.8%             |
| **Experiment 2 – Polynomial Features**                            | 93.4%                   | 86.3%     | 92.4%             |
| **Experiment 2 – Polynomial Features + Derived Column (BMI)**     | 96.0%                   | 89.6%     | 97.2%             |
| **Experiment 3 – PCA for Dimensionality Reduction**               | 91.3%                   | 91.0%     | 90.3%             |
| **Experiment 4 – Adding Synthetic Noise**                         | 92.8%                   | 80.0%     | 100.0%            |

## Results Overview

- **Baseline:**  
  - **Logistic Regression** and **Decision Trees** show strong initial performance, suggesting these models can effectively capture the underlying patterns in the dataset.  
  - The **SVM** performed relatively lower (74.7%), possibly due to sensitivity to feature scaling issues in the unscaled baseline data.

- **Scaling Features (Experiment 1):**  
  - **SVM** demonstrated a substantial performance boost, increasing from 74.7% to 90.5%.  
    - *Reason:* SVMs are highly sensitive to the scale of the input data, and scaling helped to better define the decision boundary.  
  - **Decision Tree** performance increased marginally from 94.1% to 94.8%, as tree-based models are relatively invariant to scaling.  
  - **Logistic Regression** experienced a slight drop to 86.5%, which could be due to overfitting on the scaled data.

- **Polynomial Features (Experiment 2):**  
  - **Logistic Regression** improved to 93.4%, suggesting that adding non-linear feature interactions helped capture more complex patterns.  
  - **SVM** dropped to 86.3%, indicating that the addition of polynomial features without proper tuning may have introduced noise that affected its performance.  
  - **Decision Tree** slightly decreased to 92.4%, likely due to the increased complexity from additional polynomial features.

- **Polynomial Features + Derived BMI (Experiment 2 Extension):**  
  - **Logistic Regression** accuracy further improved to 96.0% with the inclusion of BMI, a critical health indicator.  
  - **SVM** also improved to 89.6%, benefiting from the additional informative feature despite the complexities introduced by polynomial terms.  
  - **Decision Tree** reached 97.2%, demonstrating that the derived BMI feature complemented the data well and enhanced the tree’s ability to effectively split the data.

- **PCA for Dimensionality Reduction (Experiment 3):**  
  - **Logistic Regression** dropped to 91.3% and **Decision Tree** to 90.3%, with **SVM** around 91.0%.  
    - *Reason:* PCA reduced the number of features, which led to a small loss of discriminative information that is crucial for the models, resulting in a minor decline in performance.

- **Adding Synthetic Noise (Experiment 4):**  
  - **SVM** improved to 93.8% and **Logistic Regression** maintained 91.3%, indicating that these models can remain robust when slight perturbations are introduced.  
  - **Decision Tree** achieved 100% accuracy under synthetic noise.

## Best Model and Rationale

Based on the experimental results, the **Decision Tree** model emerged as the overall best-performing model. Below are the reasons why:

- **Consistent High Performance:**  
  - The Decision Tree achieved high accuracy across all experiments, consistently outperforming or matching the other models.
  
- **Robustness to Feature Engineering:**  
  - With the inclusion of polynomial features and the derived BMI column, the Decision Tree’s accuracy increased to 97.2%, highlighting its ability to benefit from enhanced feature representations.
  
- **Flexibility Without Extensive Scaling Requirements:**  
  - Unlike models such as SVM, which require careful feature scaling, Decision Trees inherently handle varying feature scales effectively, making them more robust for this dataset.
 
- ## Future Work

To further improve model performance and ensure its robustness and generalizability, several avenues of future work will be pursued:

- **Model Ensembling:**  
  - *Random Forests & Boosting Methods:* While the current experiments include Decision Trees, ensemble methods such as Random Forests, Gradient Boosting, and AdaBoost are promising for reducing overfitting and improving overall accuracy by aggregating predictions from multiple models.
  - *Stacking Models:* Explore techniques for stacking or blending predictions from the best-performing models to build a more robust meta-model.

- **Advanced Feature Engineering and Selection:**  
  - *Additional Derived Features:* Identify and create new domain-specific features, such as metabolic rate estimates or interaction terms between lifestyle attributes, to further enhance model performance.

## Conclusion

This project demonstrates the practical application of various data preprocessing techniques and machine learning algorithms in solving a critical health-related classification problem. The combination of comprehensive feature engineering, a robust pipeline setup, and extensive experimentation has led to valuable insights into the performance of different models. Ultimately, careful tuning of data transformations and model selection is key to leveraging predictive analytics effectively in real-world applications.
