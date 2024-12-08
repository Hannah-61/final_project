# Personal Loan Prediction Model

## 📋 **Project Overview**

This project analyzes data from a personal loan campaign and builds predictive models to determine the likelihood of customers purchasing personal loans. The goal is to use machine learning to identify key factors influencing loan acceptance and improve the campaign's effectiveness by targeting high-potential customers.

## 🧰 **Technologies and Tools Used**

* **Programming Language:** Python
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
* **Algorithms Used:**
  * Logistic Regression
  * Decision Tree Classifier (with Pre-Pruning, Hyperparameter Tuning, and Post-Pruning)
* **Visualization Tools:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook

## 🎯 **Project Objectives**

1. Analyze the dataset to identify factors influencing personal loan acceptance.
2. Build and evaluate models to predict customer likelihood of accepting loans.
3. Optimize the models to achieve high recall and accuracy to minimize false negatives.
4. Provide actionable insights and recommendations to improve marketing strategies.

---

## 📊 **Data Exploration and Preparation**

### **Dataset Overview**

The dataset contains customer demographic, financial, and behavioral data:

* **Target Variable:** `PersonalLoan` (1 if customer accepted the loan, 0 otherwise)
* **Features:** Income, Education, Age, Family Size, Average Spending (CCAvg), Mortgage, etc.

### **Exploratory Data Analysis (EDA)**

1. Identified key features correlated with loan acceptance:
   * **Income** : Higher income increases loan acceptance likelihood.
   * **Education Level** : Customers with graduate/advanced degrees are more likely to accept loans.
   * **Family Size** : Customers with 3-4 family members are more likely to accept loans.
2. Handled data imbalances and outliers effectively.

---

## 🏗️ **Model Building**

### **Approach**

1. **Logistic Regression** :

* Baseline model to identify important features and assess performance.
* Tuned using optimal threshold based on ROC-AUC curve to improve recall.

1. **Decision Tree Classifier** :

* Built models with pre-pruning, hyperparameter tuning, and post-pruning.
* Post-pruned Decision Tree provided the best performance with:
  * 96% **Recall** on test data.
  * Reduced false negatives.

### **Model Comparison**

| Model                                   | Train Accuracy | Test Accuracy  | Train Recall   | Test Recall    |
| --------------------------------------- | -------------- | -------------- | -------------- | -------------- |
| Logistic Regression (Optimal Threshold) | 0.92           | 0.91           | 0.90           | 0.88           |
| Initial Decision Tree Model             | 1.00           | 0.98           | 1.00           | 0.86           |
| Decision Tree (Hyperparameter Tuning)   | 0.99           | 0.98           | 0.92           | 0.84           |
| **Decision Tree (Post-Pruning)**  | **0.98** | **0.97** | **0.98** | **0.96** |

---

## 📌 **Key Insights**

1. **Important Features** :

* Income.
* Graduate and Advanced Education.
* Family Size (3-4 members).
* Average Spending (CCAvg).

1. **Misclassification Analysis** :

* **False Negatives** : Customers with lower income and undergraduate education were occasionally misclassified as non-acceptors.
* **False Positives** : Some customers with advanced education were misclassified as acceptors.

---

## 📈 **Performance Metrics**

### **Confusion Matrix (Post-Pruning Decision Tree)**

* **Test Data** :
* True Positives: 138
* False Positives: 31
* True Negatives: 1325
* False Negatives: 6

| Metric    | Train | Test |
| --------- | ----- | ---- |
| Accuracy  | 0.98  | 0.97 |
| Recall    | 0.98  | 0.96 |
| Precision | 0.82  | 0.82 |
| F1-Score  | 0.88  | 0.88 |

---

## 📊 **Feature Importances**

From the Decision Tree, the most important features were:

1. **Income** (strongest predictor).
2. **Graduate Education** .
3. **Family Size (3 and 4 members)** .
4. **CCAvg (Credit Card Average Spending)** .
5. **Advanced Education** .

---

## 📋 **Conclusions**

1. The **post-pruned Decision Tree model** is the best for predicting loan acceptance, with high recall and reduced false negatives.
2. Customers with higher income, graduate/advanced education, and medium to large family sizes are the most likely to accept loans.

---

## 🔎 **Recommendations**

1. **Target High-Profile Customers** :

* Income > $98,000.
* Graduate/Advanced education level.
* Family size of 3-4 members.
* High average spending.

1. **Introduce Customer Segmentation** :

* **High Profile** : Personalized offers and relationship managers.
* **Medium Profile** : Competitive loan rates with flexible terms.
* **Low Profile** : Prequalification campaigns to assess interest.

1. **Data-Driven Marketing** :

* Focus campaigns on high-income customers in graduate/advanced education categories.
* Highlight competitive interest rates and personalized loan options.

---

## 🛠️ **How to Use This Project**

1. Clone the repository:
   <pre class="!overflow-visible"><div class="contain-inline-size rounded-md border-[0.5px] border-token-border-medium relative bg-token-sidebar-surface-primary dark:bg-gray-950"><div class="flex items-center text-token-text-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md h-9 bg-token-sidebar-surface-primary dark:bg-token-main-surface-secondary select-none">bash</div><div class="sticky top-9 md:top-[5.75rem]"><div class="absolute bottom-0 right-2 flex h-9 items-center"><div class="flex items-center rounded bg-token-sidebar-surface-primary px-2 font-sans text-xs text-token-text-secondary dark:bg-token-main-surface-secondary"><span class="" data-state="closed"><button class="flex gap-1 items-center select-none py-1"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm"><path fill-rule="evenodd" clip-rule="evenodd" d="M7 5C7 3.34315 8.34315 2 10 2H19C20.6569 2 22 3.34315 22 5V14C22 15.6569 20.6569 17 19 17H17V19C17 20.6569 15.6569 22 14 22H5C3.34315 22 2 20.6569 2 19V10C2 8.34315 3.34315 7 5 7H7V5ZM9 7H14C15.6569 7 17 8.34315 17 10V15H19C19.5523 15 20 14.5523 20 14V5C20 4.44772 19.5523 4 19 4H10C9.44772 4 9 4.44772 9 5V7ZM5 9C4.44772 9 4 9.44772 4 10V19C4 19.5523 4.44772 20 5 20H14C14.5523 20 15 19.5523 15 19V10C15 9.44772 14.5523 9 14 9H5Z" fill="currentColor"></path></svg>Copy code</button></span></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-bash">git clone <repository_url>
   </code></div></div></pre>
2. Install the required Python libraries:
   <pre class="!overflow-visible"><div class="contain-inline-size rounded-md border-[0.5px] border-token-border-medium relative bg-token-sidebar-surface-primary dark:bg-gray-950"><div class="flex items-center text-token-text-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md h-9 bg-token-sidebar-surface-primary dark:bg-token-main-surface-secondary select-none">bash</div><div class="sticky top-9 md:top-[5.75rem]"><div class="absolute bottom-0 right-2 flex h-9 items-center"><div class="flex items-center rounded bg-token-sidebar-surface-primary px-2 font-sans text-xs text-token-text-secondary dark:bg-token-main-surface-secondary"><span class="" data-state="closed"><button class="flex gap-1 items-center select-none py-1"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm"><path fill-rule="evenodd" clip-rule="evenodd" d="M7 5C7 3.34315 8.34315 2 10 2H19C20.6569 2 22 3.34315 22 5V14C22 15.6569 20.6569 17 19 17H17V19C17 20.6569 15.6569 22 14 22H5C3.34315 22 2 20.6569 2 19V10C2 8.34315 3.34315 7 5 7H7V5ZM9 7H14C15.6569 7 17 8.34315 17 10V15H19C19.5523 15 20 14.5523 20 14V5C20 4.44772 19.5523 4 19 4H10C9.44772 4 9 4.44772 9 5V7ZM5 9C4.44772 9 4 9.44772 4 10V19C4 19.5523 4.44772 20 5 20H14C14.5523 20 15 19.5523 15 19V10C15 9.44772 14.5523 9 14 9H5Z" fill="currentColor"></path></svg>Copy code</button></span></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-bash">pip install -r requirements.txt
   </code></div></div></pre>
3. Run the Jupyter Notebook to explore the analysis and models.

---

## 🏆 **Future Work**

1. Experiment with ensemble models (e.g., Random Forest, Gradient Boosting) to improve performance.
2. Expand dataset with additional demographic and behavioral data for enhanced prediction.
3. Build an interactive dashboard for real-time loan acceptance predictions.
