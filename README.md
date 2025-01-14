# Cancer Detection Clustering

## Author: Yufei Quan

## Introduction
This project aims to utilize personal health data as a diagnostic tool for early cancer detection. By implementing **unsupervised learning techniques**, the analysis seeks to identify **outliers and clusters** in patient health data, hypothesizing that such deviations may correlate with cancer diagnoses.

The project focuses on **reducing false negatives** and overall false diagnoses to prioritize patient safety. Various **clustering and outlier detection techniques** are explored to achieve this goal.

---

## Methods
The following clustering techniques were explored:

- **K-Means**
- **Agnes (Agglomerative Nesting)**
- **Diana (Divisive Analysis Clustering)**
- **DBSCAN (Density-Based Spatial Clustering)**
- **K-Nearest Neighbors (KNN)**
- **Isolation Forest (Anomaly Detection)**

The dataset consists of **378 observations**, with **30 feature columns** and **1 binary outcome variable** (1 for cancer, 0 for non-cancer). **Dimensionality reduction** using **Principal Component Analysis (PCA)** was applied to improve visualization and enhance clustering effectiveness.

---

## Key Findings

### **1. K-Means Clustering**
- Identified clusters based on similarity.
- Achieved **78.99% sensitivity** and **99.30% precision**.
- Some cancer patients were still misclassified.

### **2. Agnes (Agglomerative Clustering)**
- Best linkage method: **Ward’s Method**.
- Achieved **94.68% sensitivity**, making it highly effective in detecting cancer cases.
- Balanced specificity and precision.

### **3. Diana (Divisive Clustering)**
- Hierarchical method that progressively splits data.
- Achieved **78.43% sensitivity** and **98.59% precision**.
- Struggled slightly with specificity.

### **4. DBSCAN (Density-Based Clustering)**
- **Perfect specificity (100%)** – all non-cancer patients correctly classified.
- **No false negatives**, but **many false positives** (low sensitivity of 74.79%).

### **5. K-Nearest Neighbors (KNN) Outlier Detection**
- Optimal **K = 2** selected via cross-validation.
- **87.39% sensitivity** and **98.73% precision**.
- Balanced approach but had a lower negative predictive value.

### **6. Isolation Forest**
- Anomaly detection technique to isolate outliers.
- **79.83% sensitivity**, **95.24% specificity**, **99.65% precision**.
- Well-balanced but slightly lower sensitivity compared to Agnes.

---

## **Comparison of Models**
| Model              | Sensitivity | Specificity | Precision | Sum Score |
|--------------------|------------|------------|-----------|-----------|
| **K-Means**       | 78.99%      | 90.48%     | 99.30%    | 2.69      |
| **Agnes**         | 94.68%      | 71.43%     | 98.26%    | **2.64**  |
| **Diana**         | 78.43%      | 80.95%     | 98.59%    | 2.58      |
| **DBSCAN**        | 74.79%      | **100%**   | **100%**  | 2.75      |
| **KNN**           | **87.39%**  | 80.95%     | 98.73%    | **2.67**  |
| **Isolation Forest** | 79.83%  | **95.24%** | **99.65%** | **2.87**  |

- **Agnes had the highest sensitivity**, making it the best at detecting cancer cases.
- **DBSCAN had the best specificity and precision** but sacrificed sensitivity.
- **KNN and Isolation Forest provided the most balanced trade-offs**.

---

## **Conclusion**
- **Agnes is the most suitable model for early cancer detection**, as it minimizes false negatives.
- **DBSCAN and Isolation Forest can be used as complementary models**, ensuring high specificity and reducing unnecessary testing.
- **A hybrid approach leveraging both clustering and anomaly detection** methods could improve overall diagnostic accuracy.
- The **small sample size** limits the model's generalizability; more data is needed for validation.

### **Final Takeaway**
This project demonstrates that **unsupervised learning techniques can effectively identify cancer cases**, reducing false negatives while maintaining accuracy. Future improvements should focus on **refining feature selection, parameter tuning, and integrating multiple models** for better diagnostic precision.
