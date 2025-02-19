# COMP4462 Data Mining Project

## Project Title: Analysis of Estimation of Obesity Levels Based on Eating Habits and Physical Condition Dataset

---

## Project Overview
This project was conducted as part of the **COMP4462 Data Mining** course. The goal was to analyze and predict obesity levels based on dietary habits and physical conditions using machine learning techniques such as:
- **Association Rule Mining**
- **Clustering**
- **Classification**

We used the **Estimation of Obesity Levels Based on Eating Habits and Physical Condition dataset** from the **UCI ML repository**, which contains **2111 records** and **17 attributes**, including demographic, dietary, and lifestyle-related features.

---

## Dataset Description
The dataset consists of:
- **Demographic attributes:** Gender, Age, Height, Weight
- **Lifestyle habits:** Physical activity (FAF), Alcohol consumption (CALC), Smoking (SMOKE), Usage of electronic devices (TUE)
- **Dietary habits:** Frequency of vegetable consumption (FCVC), High caloric food consumption (FAVC), Number of meals per day (NCP), Eating between meals (CAEC)
- **Health-related attributes:** Family history with overweight, Water intake (CH2O), Monitoring calories (SCC)
- **Target Variable:** NObeyesdad (Obesity Level)

---

## Methodology

### 1. **Data Preprocessing**
- Checked for **missing values** (None found)
- Applied **label encoding** to categorical features
- Handled class imbalance using **SMOTE-NC**
- Performed **outlier detection** using box plots

### 2. **Association Rule Mining**
Used the **Apriori algorithm** to identify patterns and relationships within the dataset. Important metrics:
- **Support > 0.05**
- **Lift > 1.0**
- **Confidence > 0.8**

Example rule discovered:
> "If Age is high, Weight is high, and Family History is present, then NCP is high and CAEC is high."

### 3. **Clustering**
Applied **K-Means** and **Hierarchical Clustering**:
- Before feature selection: **Silhouette Score = 0.24**
- After feature selection (FCVC, CAEC, SCC, FAVC):
  - **K-Means: 0.610**
  - **Hierarchical: 0.721**
- Identified **10 meaningful clusters** reflecting lifestyle and obesity patterns.

### 4. **Classification**
Implemented and compared multiple classification models:
| Algorithm        | Accuracy | Precision | Recall | F1-Score |
|-----------------|----------|------------|--------|----------|
| k-NN            | 0.8028   | 0.7966     | 0.8028 | 0.7918   |
| ANN             | 0.9492   | 0.9497     | 0.9492 | 0.9494   |
| Decision Tree   | 0.9350   | 0.9361     | 0.9350 | 0.9345   |
| **Random Forest** | **0.9634** | **0.9642** | **0.9634** | **0.9636** |

- **Random Forest performed the best**, identifying weight, height, and age as the most significant features.

---

## Key Findings
- **Dietary habits (FCVC, NCP, CAEC) and physical activity (FAF) strongly impact obesity levels.**
- **Family history with overweight is a key factor in obesity prediction.**
- **Feature selection improved clustering accuracy significantly.**
- **Random Forest achieved the highest classification accuracy (96.34%).**

---

## Challenges & Solutions
### **1. Data Preprocessing:**
- Managed class imbalance using **SMOTE-NC**.
- Converted categorical data into numerical form using **label encoding**.

### **2. Association Rule Mining:**
- Selected only the most **relevant rules** with high support, confidence, and lift to reduce redundancy.

### **3. Feature Selection for Clustering:**
- Applied **feature selection techniques** to enhance clustering results.
- Focused on features related to eating habits (FCVC, CAEC, SCC, FAVC).

---

## Conclusion
Our study demonstrated the effectiveness of **machine learning** in analyzing obesity-related data. By using **association rule mining, clustering, and classification**, we successfully identified **key lifestyle factors** affecting obesity. The **Random Forest classifier achieved the highest accuracy**, making it the best model for obesity level prediction.

Future work may include:
- Incorporating additional **real-world data** for improved generalization.
- Exploring **deep learning techniques** for enhanced prediction accuracy.
- Analyzing **regional differences** in obesity trends among countries.

---

## References
- UCI ML Repository - **Obesity Levels Dataset**: [Link](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition)
- WHO - **Body Mass Index (BMI) Calculation**: [Link](https://www.who.int/data/gho/data/themes/topics/topic-details/GHO/body-mass-index)
- Scikit-learn - **Random Forest Classifier**: [Link](https://scikit-learn.org/1.5/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
- Imbalanced-learn - **SMOTE-NC**: [Link](https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.SMOTENC.html)

---

## How to Run the Code
1. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook COMP4462_project_group-7.ipynb
   ```
3. Run the notebook cells sequentially.

---


