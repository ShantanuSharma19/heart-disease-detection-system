# Heart Disease Detection System

## 📋 Project Overview

A machine learning project that predicts the presence of heart disease using clinical indicators. The system achieves **82% accuracy** in identifying patients at risk of heart disease, making it suitable for preliminary medical screening.

## 📊 Dataset

- **Size**: 920 patient records
- **Features**: 14 clinical indicators
- **Target Classes**: 
  - 509 patients with heart disease (55%)
  - 411 patients without heart disease (45%)
- **Source**: UCI Heart Disease Dataset

## 🔍 Key Features Used

| Feature | Description |
|---------|-------------|
| Age | Patient age in years |
| Sex | Male/Female |
| cp | Chest pain type (4 types) |
| trestbps | Resting blood pressure (mmHg) |
| chol | Serum cholesterol (mg/dl) |
| fbs | Fasting blood sugar > 120 mg/dl |
| restecg | Resting electrocardiographic results |
| thalch | Maximum heart rate achieved |
| exang | Exercise-induced angina |
| oldpeak | ST depression induced by exercise |
| slope | Slope of peak exercise ST segment |
| ca | Number of major vessels (0-3) |
| thal | Thalassemia classification |

## 🛠️ Data Processing

1. **Data Cleaning**: 
   - Handled missing values using median (numerical) and mode (categorical)
   - Removed redundant 'id' column
   - Final dataset: 920 samples with 0 missing values

2. **Feature Engineering**: 
   - One-hot encoding for categorical variables
   - Expanded feature space to 28 dimensions

3. **Data Split**: 
   - Training: 736 samples (80%)
   - Testing: 184 samples (20%)

## 🤖 Model Details

**Algorithm**: Logistic Regression  
**Preprocessing**: StandardScaler normalization  
**Hyperparameters**: max_iter=1000

### Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 82.1% |
| Precision (Disease) | 87% |
| Recall (Disease) | 83% |
| F1-Score (Disease) | 0.85 |

### Confusion Matrix
```
                 Predicted
              No Disease | Disease
Actual No      61      14
       Yes     19      90
```

## 📈 Results Summary

- ✅ **High Recall (83%)**: Successfully identifies 83% of actual disease cases
- ✅ **High Precision (87%)**: 87% of positive predictions are correct
- ⚠️ **14 False Positives**: Minor over-prediction of disease
- ⚠️ **19 False Negatives**: 19% of diseased patients missed

## 📁 Files Included

- `heart-disease-detection-system.ipynb` - Complete analysis and model training
- `heart_disease_uci.csv` - Dataset (920 records)
- `MLC project- final report.pdf` - Detailed project report
- `report file.pdf` - Additional documentation

## 🚀 Usage

### Prerequisites
```bash
pip install pandas numpy scikit-learn
```

### Running the Model
```python
# Load and preprocess data
df = pd.read_csv('heart_disease_uci.csv')

# Train the model
from sklearn.linear_model import LogisticRegression
model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)

# Make predictions
predictions = model.predict(X_test)
```

## 💡 Key Insights

1. **Clinical Relevance**: The model effectively captures patterns associated with heart disease
2. **Balanced Performance**: Good balance between sensitivity and specificity
3. **Feature Importance**: Chest pain type, maximum heart rate, and ST parameters are strong predictors
4. **Medical Application**: Suitable as a preliminary screening tool, with medical professional review recommended

## 🎯 Recommendations

- Use for patient risk stratification in healthcare settings
- Combine with other diagnostic tests for final diagnosis
- Consider class weights to reduce false negatives in high-risk scenarios
- Regular model updates with new patient data

## 📝 Author

**Shantanu Sharma**  
GitHub: [@ShantanuSharma19](https://github.com/ShantanuSharma19)

## 📄 License

This project is open source and available for educational and research purposes.

---

*Last Updated: June 2026*
