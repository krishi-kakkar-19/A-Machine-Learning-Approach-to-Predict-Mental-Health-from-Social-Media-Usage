# A-Machine-Learning-Approach-to-Predict-Mental-Health-from-Social-Media-Usage
Online Activity, Offline Impact: A Machine Learning Approach to Predict Mental Health from Social Media Usage

# Social Media & Mental Health Risk Classifier

## Overview

This project analyzes the relationship between social media usage patterns and mental health outcomes, specifically focusing on depression risk. Using a synthetic but research-grounded dataset, the project builds a machine learning model to classify individuals at risk of depression based on behavioral and lifestyle features.

The objective is to demonstrate how data-driven systems can support early identification and intervention in mental health contexts.

---

## Dataset

The dataset contains user-level behavioral, lifestyle, and psychological indicators, including:

* Social media usage patterns
* Sleep behavior
* Content consumption habits
* User activity types
* PHQ-9–based depression classification

Files included:

* `social_media_mental_health.csv` (raw dataset)
* `social_media_mental_health_model_ready_dataset.csv` (processed dataset)

---

## Data Dictionary

### Core Features

| Column Name               | Type    | Range     | Description                                                          |
| ------------------------- | ------- | --------- | -------------------------------------------------------------------- |
| age                       | Integer | 18–22     | Age of participant                                                   |
| daily_screen_time_hours   | Float   | 0.5–11.3  | Daily hours spent on social media                                    |
| night_usage               | Integer | 0, 1      | 1 = uses social media late at night; 0 = does not                    |
| social_comparison_trigger | Integer | 0, 1      | 1 = experiences social comparison; 0 = does not                      |
| sleep_hours               | Float   | 3.0–11.6  | Average nightly sleep duration (hours)                               |
| screen_to_sleep_ratio     | Float   | 0.04–3.22 | Ratio of screen time to sleep hours                                  |
| phq_binary                | Integer | 0, 1      | Target variable: 1 = moderate-to-severe depression, 0 = none-to-mild |
| gender_Female             | Integer | 0, 1      | 1 = female                                                           |
| gender_Male               | Integer | 0, 1      | 1 = male                                                             |

### User Archetype (One-Hot Encoded)

| Column Name                       | Type    | Range | Description                |
| --------------------------------- | ------- | ----- | -------------------------- |
| user_archetype_Average_User       | Integer | 0, 1  | Average user               |
| user_archetype_Digital_Minimalist | Integer | 0, 1  | Low social media usage     |
| user_archetype_Hyper_Connected    | Integer | 0, 1  | Heavy, frequent usage      |
| user_archetype_Passive_Scroller   | Integer | 0, 1  | Primarily consumes content |

### Primary Platform (One-Hot Encoded)

| Column Name                | Type    | Range | Description |
| -------------------------- | ------- | ----- | ----------- |
| primary_platform_Facebook  | Integer | 0, 1  | Facebook    |
| primary_platform_Instagram | Integer | 0, 1  | Instagram   |
| primary_platform_LinkedIn  | Integer | 0, 1  | LinkedIn    |
| primary_platform_Snapchat  | Integer | 0, 1  | Snapchat    |
| primary_platform_TikTok    | Integer | 0, 1  | TikTok      |
| primary_platform_Twitter_X | Integer | 0, 1  | Twitter/X   |
| primary_platform_YouTube   | Integer | 0, 1  | YouTube     |

### Dominant Content Type (One-Hot Encoded)

| Column Name                                | Type    | Range | Description                 |
| ------------------------------------------ | ------- | ----- | --------------------------- |
| dominant_content_type_Educational_Tech     | Integer | 0, 1  | Educational or tech content |
| dominant_content_type_Entertainment_Comedy | Integer | 0, 1  | Entertainment/comedy        |
| dominant_content_type_Gaming               | Integer | 0, 1  | Gaming content              |
| dominant_content_type_Lifestyle_Fashion    | Integer | 0, 1  | Lifestyle/fashion           |
| dominant_content_type_News_Politics        | Integer | 0, 1  | News/politics               |
| dominant_content_type_Self_Help_Motivation | Integer | 0, 1  | Self-help/motivation        |

### Activity Type

| Column Name           | Type    | Range | Description                |
| --------------------- | ------- | ----- | -------------------------- |
| activity_type_Active  | Integer | 0, 1  | Actively posts/interacts   |
| activity_type_Passive | Integer | 0, 1  | Primarily consumes content |

Note: Categorical variables were one-hot encoded. For each category group, exactly one column should be 1 per observation.

---

## Feature Engineering

* **PHQ_Binary**
  Converted PHQ-9 scores into a binary classification target

* **Screen-to-Sleep Ratio**
  Captures imbalance between digital exposure and recovery (sleep)

* **One-Hot Encoding**
  Applied to categorical variables

* **Data Cleaning**

  * Removed inconsistencies
  * Handled missing values
  * Standardized formats

---

## Model

* **Algorithm:** Logistic Regression (scikit-learn)
* **Validation:** 5-fold cross-validation
* **Class Imbalance Handling:** Threshold tuning

### Performance

* **Recall:** 90.8%

High recall was prioritized to minimize false negatives and ensure at-risk individuals are identified.

---

## Workflow

1. Data loading and inspection
2. Data cleaning and preprocessing
3. Feature engineering
4. Train-test split
5. Model training
6. Cross-validation
7. Model evaluation
8. Result interpretation

---

## Technologies Used

* Python
* pandas
* NumPy
* scikit-learn
* Matplotlib

---

## Key Insights

* High screen time relative to sleep is strongly associated with increased depression risk
* Behavioral ratios provide stronger signals than raw metrics
* Logistic regression offers interpretable and effective classification
* Recall-focused models are more appropriate for health-related applications

---

## Limitations

* Dataset is synthetic (not real clinical data)
* Self-reported inputs may introduce bias
* Model does not account for external variables (environmental, genetic factors)
* Binary classification oversimplifies mental health conditions

---

## Future Work

* Use real-world clinical datasets
* Explore advanced models (Random Forest, XGBoost)
* Incorporate time-series behavioral data
* Build a real-time triage or recommendation system
* Improve interpretability (e.g., SHAP values)

---

## Files

* `I310D_Final_Project.ipynb` – Full analysis pipeline
* `social_media_mental_health.csv` – Raw dataset
* `social_media_mental_health_model_ready_dataset.csv` – Processed dataset

---

## Author

Krish Kakkar
Informatics (Human-Centered Data Science), The University of Texas at Austin 
