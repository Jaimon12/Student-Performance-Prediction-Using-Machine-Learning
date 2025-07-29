# Student Performance Prediction Using Machine Learning

A machine learning project to predict student academic outcomes (pass/fail) based on socio-demographic, academic, and behavioral factors.

---

## 🎯 Objective

- Predict whether a student will pass or fail using early-term data.
- Identify key factors that influence academic success.
- Enable educational institutions to provide timely interventions.

---

## 📁 Dataset

**Source**: UCI Machine Learning Repository – [Student Performance Dataset](https://www.kaggle.com/datasets/devansodariya/student-performance-data)  
**Records**: 395 students  
**Features**: 33 attributes including:

- **Demographics**: Age, gender, family size, parental education
- **Academic behavior**: Study time, past failures, school support
- **Personal/social**: Alcohol use, internet access, relationships
- **Grades**: G1, G2, G3 (1st, 2nd, and final period grades)

**Target Variable**: `pass_fail`  
- `1`: G3 ≥ 10 (Pass)  
- `0`: G3 < 10 (Fail)  

Grades G1, G2, and G3 were excluded from modeling to simulate early prediction.

---

## 🛠️ Methodology

1. **Data Preprocessing**
   - Converted `G3` to binary `pass_fail` column.
   - Dropped G1, G2, G3 to avoid data leakage.
   - Encoded categorical variables using `LabelEncoder`.
   - Performed 80/20 stratified train-test split.

2. **Modeling**
   Trained and evaluated three classifiers:
   - **Logistic Regression**
   - **Random Forest**
   - **XGBoost**

3. **Evaluation Metrics**
   - Accuracy
   - Precision, Recall, F1 Score
   - ROC Curve and AUC
   - Confusion Matrix
   - Feature Importance (for tree-based models)

---

## 📊 Results

| Model              | Accuracy | Precision | Recall | F1 Score | AUC  |
|-------------------|----------|-----------|--------|----------|------|
| Logistic Regression | 0.79     | 0.81      | 0.93   | 0.86     | 0.86 |
| Random Forest       | 0.82     | 0.83      | 0.94   | 0.88     | 0.89 |
| XGBoost             | 0.84     | 0.85      | 0.95   | 0.90     | 0.91 |

**Top 5 Features (XGBoost):**
1. Failures
2. Study Time
3. Mother’s Education
4. Absences
5. Going Out

---

## 🔍 Insights

- Students with previous academic failures, low study time, and frequent absences are more likely to fail.
- Higher parental education—especially maternal—correlates with better student performance.
- Excessive socializing and alcohol use negatively impact academic outcomes.

---

## ✅ Conclusion

XGBoost outperformed other classifiers in predicting student success, offering both accuracy and explainability. These findings can support educational institutions in identifying at-risk students early in the academic term.

---

## 📌 Recommendations

- Integrate real-time behavioral data for deeper insights.
- Use model explanation tools (SHAP, LIME) for interpretability.
- Explore balancing techniques (e.g., SMOTE) if class imbalance increases.
- Extend the model to multiclass classification (e.g., low, medium, high performance).
- Deploy an interactive dashboard for school counselors or administrators.

---

## 📎 Files

- `student_performance.ipynb` – Jupyter notebook with complete code
- `student_performance_report.pdf` – Summary of project results
- `README.md` – Project overview

---

## 📄 License

MIT License

---

## 🤝 Contributions

Contributions are welcome! Feel free to fork, improve the models, or suggest new features.

---

## 💡 Inspiration

"Data-driven education empowers better futures."

