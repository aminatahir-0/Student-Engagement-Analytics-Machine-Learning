# Student Engagement Analytics & Machine Learning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Fn9VFa7NODGYPoa5ZGJNUy2WBJEobbay#scrollTo=1B-V1heDLxVy) 

## 📊 Project Overview
This repository contains an end-to-end data science workflow that bridges **Exploratory Data Analysis (EDA)** with **Predictive Machine Learning Modeling**. The project evaluates student online learning data to analyze behavioral habits, track completion risks, and build an early-warning classification pipeline.

---

## 🔍 Workflow Phases

### Phase 1: Exploratory Data Analysis (EDA)
Before jumping into machine learning, the dataset is thoroughly explored to uncover hidden patterns and understand feature relationships:
* **Data Cleaning & Inspection:** Checked for missing values, handled data types, and standardized feature columns.
* **Behavioral Distribution:** Analyzed student metrics such as login frequency, study hours, and engagement levels.
* **Correlation & Insights:** Investigated how individual habits relate to student outcomes, revealing that isolated behavioral metrics alone cannot cleanly separate dropped-out students from completers without progression context.

### Phase 2: Predictive Machine Learning Modeling
Building upon the insights from EDA, a supervised classification pipeline is constructed:
* **Train-Test Split:** Separated input variables (`X`) and target outputs (`y`), splitting the data to train on historical outcomes and test on unseen samples.
* **Model Training:** Initialized and trained a `RandomForestClassifier` with a controlled `random_state` for reproducible results.
* **Feature Importance Analysis:** Extracted `model.feature_importances_` and paired them with `X.columns` to quantify which columns drove the model's decisions.
* **Ablation Experiment:** Tested model reliance by removing the dominant "course progress" feature, observing accuracy plummet from a high baseline to **53.57%**, proving the critical necessity of tracking active milestones for effective intervention.

---

## 🛠️ Tech Stack & Libraries
* **Python**
* **Pandas & NumPy** (Data manipulation and transformation)
* **Scikit-Learn** (Random Forest modeling, evaluation metrics, and feature importances)
* **Matplotlib & Seaborn** (Visualizing distributions, correlations, and performance)
* **Google Colab & GitHub** (Development environment and version control)

### 📋 Key Conclusions & Takeaways

* **EDA Validation:** Exploratory data analysis showed that student success cannot be predicted by simple, isolated habits alone, which prompted the need for predictive modeling.
* **The Role of Course Progress:** The initial machine learning model proved that cumulative "course progress" is the strongest factor for predicting whether a student completes or drops out.
* **Ablation Study Insights:** Removing course progress caused model accuracy to drop sharply to **53.57%**, confirming that basic behavioral data on its own is not enough to accurately predict student outcomes.
* **Future Improvements:** Future projects will benefit from advanced feature engineering—such as monitoring weekly consistency trends and engagement ratios—to catch at-risk students earlier.
