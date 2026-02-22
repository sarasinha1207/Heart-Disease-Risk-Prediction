# Heart Disease Risk Prediction using ML
## **Motivation**

Heart disease is the leading cause of death worldwide. Early detection can save lives by allowing timely intervention. Machine Learning can help predict the risk of heart disease using patient data such as age, blood pressure, cholesterol, and lifestyle factors.

This project demonstrates how classical machine learning techniques can be used to estimate heart disease risk from routine clinical parameters.


##  **Dataset Description**

*   Source: UCI Heart Disease Dataset
*   Total Features: 13
    (Clinical and demographic attributes such as age, sex, cholesterol levels, resting blood pressure, and ECG results.)
*   Target Variable: target
    *   1 → Heart Disease Present
    *   0 → No Heart Disease
##  **Methodology Overview**

This project follows a standard supervised machine learning pipeline:

1.   Data loading and preprocessing of clinical features
2.   Train–test split to assess model generalization
3.   Feature scaling for magnitude-sensitive models
4.   Training and comparison of multiple classification algorithms
5.   Model evaluation using performance metrics and interpretability


<p align="center">
  <img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3d828f19-8117-41b4-a714-e9e898db16fa" />
</p>
<p align="center"><em>Figure 1: Key Factors Influencing Heart Disease</em></p>

### **Interpretation of Visualizations**

*   Age Distribution: Most patients fall in the middle-aged to older category, indicating that the risk of heart disease increases with age.
*   Gender vs Heart Disease: Males show a higher incidence of heart disease compared to females in the dataset.
*   Chest Pain Type vs Heart Disease: Certain chest pain types are strongly associated with the presence of heart disease, making it a critical predictive feature.**bold text**
*   Exercise Induced Angina: Patients experiencing exercise-induced angina have a significantly higher likelihood of heart disease.

<p align="center">
<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/28eb8f6c-6d0d-468e-a5c0-70a50d111cc1" />

</p>
<p align="center"><em>Figure 2: The correlation heatmap shows that features such as chest pain type (cp, r = 0.43), maximum heart rate (thalach, r = 0.42), exercise-induced angina (exang, r = −0.44), and ST depression (oldpeak, 
r = −0.43) have the strongest relationships with heart disease, highlighting the key factors influencing risk prediction.</em></p>

<p align="center">
<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/e5e86643-1f4b-4ee4-b993-a1db0260318a" />

</p>
<p align="center"><em>Figure 3: The pairplot reveals clear separation between classes, showing that patients with heart disease generally have lower maximum heart rate (thalach ≈ 120–150) and higher ST depression (oldpeak ≈ 1–3) compared to healthy individuals.</em></p>

## Models Evaluated

The following models were trained and evaluated on the test set:

| Model                   | Accuracy | Precision | Recall | F1-Score | False Negatives |
|-------------------------|----------|-----------|--------|----------|----------------|
| Logistic Regression     | 0.85249     | 0.87096    | 0.84375 | 0.85714   | 5              |
| Decision Tree (depth=5) | 0.75409    | 0.84000    | 0.65625  | 0.73684    | 11              |
| **KNN (k = 9)**         | **0.91803**| **0.93548** | **0.90625** | **0.92063** | **3** ← Final |

<p align="center">
<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/2350f483-2001-442f-87ac-b9788d69cf9f" />

</p>
<p align="center"><em>Figure 4: The confusion matrices show that KNN performs best, with the highest correct predictions (27 TN, 29 TP) and the fewest errors. Logistic Regression performs moderately, while Decision Tree has the most false negatives, making KNN the most reliable model for heart disease prediction.</em></p>

## Final Model: K-Nearest Neighbors (KNN)

After preprocessing, feature scaling, and hyperparameter tuning, **K-Nearest Neighbors (k = 9)** was selected as the final model.

Although Logistic Regression achieved competitive accuracy, **KNN produced the highest accuracy, the highest recall, and the lowest number of false negatives**, which is especially important in a medical context where missing a positive case can have serious consequences.

- **Model:** K-Nearest Neighbors (k = 9)
- **Accuracy:** 0.9180327868852459 
- **Precision:** 0.9354838709677419  
- **Recall:** 0.90625 
- **F1-Score:** 0.9206349206349206 
- **False Negatives:** 3

These results indicate that KNN is more effective at correctly identifying patients with heart disease compared to the other evaluated models.

## Tools and Libraries
- Python  
- NumPy  
- Pandas  
- Scikit-learn  
- Matplotlib  
- Seaborn  

## **Model Interpretability**

To improve transparency, Logistic Regression coefficients are analyzed to understand feature influence.

This helps identify key clinical factors that contribute most strongly to heart disease risk and enhances trust in the model’s predictions.


## **Key Results & Takeaways**
*  Classical machine learning models can effectively predict heart disease risk using clinical data
*  Risk-based outputs provide more nuanced insight than binary classification
*  Logistic Regression achieves strong performance with high interpretability
*  Minimizing false negatives is essential in medical screening tasks

## **Future Improvements**

* Hyperparameter tuning to further improve model performance
* Bias and subgroup analysis to assess fairness across populations
* Cross-dataset validation for robustness
* Deployment as an educational or demonstration tool in the future

---
### Notes:
- This project is intended as a baseline machine learning model, not a clinical diagnostic tool.
- No deep learning models or deployment frameworks are used.
- The emphasis is on understanding the machine learning pipeline and evaluation methodology.
