Cancer Detection Clustering

By Yufei Quan

Introduction

This project explores the use of unsupervised learning techniques to analyze personal health data for early cancer detection. The approach involves clustering methods to identify outliers and anomalies in patient health records, with the hypothesis that deviations in health indicators may correlate with cancer diagnoses.

The framework integrates:
	•	Outlier detection
	•	Clustering techniques
	•	Dimensionality reduction (PCA)
	•	Validation using labeled data with a focus on minimizing false negatives, which are critical in cancer diagnosis.

Techniques Explored

Multiple clustering and outlier detection techniques were tested, with adjustments made to prioritize sensitivity (to avoid missing cancer cases) over absolute accuracy.

The methods implemented include:
	1.	Clustering Algorithms
	•	K-Means
	•	AGNES (Agglomerative Nesting - Hierarchical Clustering)
	•	DIANA (Divisive Analysis - Hierarchical Clustering)
	•	DBSCAN (Density-Based Clustering)
	2.	Outlier Detection
	•	K-Nearest Neighbors (KNN)
	•	Isolation Forest

Data Overview
	•	Dataset: 378 observations, 30 feature variables.
	•	Target Label: Binary outcome (1 = Cancer, 0 = No Cancer).
	•	Dimensionality Reduction: Principal Component Analysis (PCA) was applied to improve interpretability and enhance clustering performance.

Results and Model Comparisons

Key Findings

Each model was evaluated based on sensitivity, specificity, and precision, with a focus on reducing false negatives.

Model	Sensitivity	Specificity	Precision	Overall Score
K-Means	0.79	0.90	0.99	2.68
AGNES	0.95	0.71	0.98	2.64
DIANA	0.78	0.81	0.99	2.58
DBSCAN	0.75	1.00	1.00	2.75
KNN	0.87	0.81	0.98	2.67
Isolation Forest	0.80	0.95	0.99	2.74

Interpretation
	•	AGNES performed the best in terms of sensitivity (0.95), making it the best model for reducing false negatives.
	•	DBSCAN had perfect specificity (1.0), meaning it was highly effective in avoiding false positives.
	•	KNN and Isolation Forest balanced sensitivity and specificity, making them strong candidates for real-world application.

Conclusion
	•	AGNES was the most effective model for detecting cancer, given its high sensitivity (0.95).
	•	DBSCAN can be used to confirm positive cases, as it achieved the highest specificity (1.0).
	•	KNN and Isolation Forest provide balanced models that effectively classify both cancerous and non-cancerous cases.
	•	PCA visualization showed that cancer patients often appear as outliers, reinforcing the need for anomaly detection techniques.

Future Directions
	•	Increase dataset size to improve model reliability.
	•	Test hybrid models by combining clustering with supervised learning.
	•	Refine threshold tuning in outlier detection models for better precision.

Table of Contents
	•	Introduction
	•	Techniques Explored
	•	Data Overview
	•	Results and Model Comparisons
	•	Conclusion

This Markdown format can be used directly in GitHub, Jupyter Notebooks, or documentation files. Let me know if you need any refinements! 🚀
