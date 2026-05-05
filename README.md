# 🚢 Titanic Survival Prediction | EDA & Machine Learning

![Python](https://img.shields.io/badge/python-3.8+-blue.svg) ![Jupyter](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white) ![Kaggle](https://img.shields.io/badge/Kaggle-035a7d?style=for-the-badge&logo=kaggle&logoColor=white) ![Status](https://img.shields.io/badge/status-completed-green) ![License](https://img.shields.io/badge/license-MIT-green)

---

## 📋 Project Overview

The sinking of the Titanic on April 15, 1912, remains one of the most tragic maritime disasters in history, claiming over 1,500 lives out of 2,224 passengers and crew. This project analyzes the famous Titanic dataset to predict passenger survival using machine learning techniques.

**What this project covers:**
- 🔍 Exploratory Data Analysis (EDA)
- 🧹 Data Cleaning & Preprocessing
- ⚙️ Feature Engineering
- 🤖 Machine Learning Modeling
- 🎯 Hyperparameter Tuning

---

## 📊 Dataset Details

| Detail | Info |
|--------|------|
| **Source** | [Kaggle Titanic Dataset](https://www.kaggle.com/datasets/yasserh/titanic-dataset) |
| **Rows** | 891 passengers |
| **Columns** | 12 features |
| **Target** | `Survived` (0 = No, 1 = Yes) |
| **Format** | CSV |

### Features Table

| Column | Description |
|--------|-------------|
| `PassengerId` | Unique passenger identifier |
| `Survived` | Survival status (0 = No, 1 = Yes) |
| `Pclass` | Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd) |
| `Name` | Passenger full name |
| `Sex` | Gender (male/female) |
| `Age` | Age in years |
| `SibSp` | Number of siblings/spouses aboard |
| `Parch` | Number of parents/children aboard |
| `Ticket` | Ticket number |
| `Fare` | Passenger fare |
| `Cabin` | Cabin number |
| `Embarked` | Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton) |

---

## 📁 Project Structure

```
Titanic-Dataset-EDA/
├── README.md
├── requirements.txt
├── Data/
│   ├── .gitkeep
│   └── Titanic-Dataset.csv
├── Notebooks/
│   ├── .gitkeep
│   ├── 02_Modeling.ipynb
│   ├── EDA.ipynb
│   └── outputs/
│       └── plots/
│           ├── age_boxplot.png
│           ├── age_distribution.png
│           ├── age_vs_survived_boxplot.png
│           ├── confusion_matrices.png
│           ├── correlation_heatmap.png
│           ├── embarked_countplot.png
│           ├── fare_boxplot.png
│           ├── fare_distribution.png
│           ├── fare_vs_survived_boxplot.png
│           ├── pclass_countplot.png
│           ├── rf_feature_importance.png
│           ├── roc_curves.png
│           ├── sex_countplot.png
│           ├── survival_by_embarked.png
│           ├── survival_by_pclass.png
│           ├── survival_by_sex.png
│           ├── survival_countplot.png
│           ├── survival_piechart.png
│           └── xgb_feature_importance.png
└── Outputs/
```

---

## 📚 Libraries Used

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation and analysis |
| `numpy` | Numerical operations and arrays |
| `matplotlib` | Basic plotting and visualization |
| `seaborn` | Statistical data visualization |
| `scikit-learn` | Machine learning algorithms and tools |
| `xgboost` | Gradient boosting framework |
| `jupyter` | Interactive notebook environment |

---

## 🔍 EDA Highlights

- 📊 **Overall Survival Rate**: 38% of passengers survived
- 👩 **Gender Impact**: Women had 74% survival rate vs. 19% for men
- 💺 **Class Disparity**: 1st class survival at 63% vs. 3rd class at 24%
- 👶 **Age Factor**: Children under 10 had significantly higher survival rates
- 💰 **Fare Correlation**: Higher ticket fares correlated with better survival chances

---

## ⚙️ Feature Engineering

| Feature | Description |
|---------|-------------|
| `FamilySize` | Total family members (SibSp + Parch + 1) |
| `IsAlone` | Binary flag (1 if FamilySize == 1, else 0) |
| `AgeGroup` | Categorized age groups (Child: 0-12, Teen: 13-19, Adult: 20-59, Senior: 60+) |
| `Title` | Extracted titles from names (Mr, Mrs, Miss, Master, etc.) |

---

## 🤖 Models & Results

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.83 | 0.83 | 0.70 | 0.76 | 0.85 |
| Decision Tree | 0.79 | 0.74 | 0.70 | 0.72 | 0.78 |
| Random Forest | 0.82 | 0.78 | 0.75 | 0.76 | 0.86 |
| **XGBoost** ⭐ | 0.81 | 0.76 | 0.74 | 0.75 | 0.87 |
| KNN | 0.68 | 0.59 | 0.54 | 0.56 | 0.72 |

**Best Model: XGBoost** - Achieved highest ROC-AUC and balanced performance metrics.

---

## 🚀 How to Run

1. **Clone the repository**  
   ```bash
   git clone https://github.com/Arslaniftikhaar/Titanic-Dataset-EDA.git
   cd titanic-survival-prediction
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Open Jupyter and run notebooks**  
   - Launch Jupyter Notebook or JupyterLab
   - Run `01_EDA.ipynb` first for comprehensive data exploration
   - Then run `02_Modeling.ipynb` for preprocessing, training, and evaluation

4. **View results**  
   All plots are automatically saved to `outputs/plots/`

---

## 📦 Requirements

### Dependencies
```
pandas==2.0.0
numpy==1.24.0
matplotlib==3.7.0
seaborn==0.12.0
scikit-learn==1.3.0
xgboost==1.7.0
jupyter==1.0.0
```

### Installation
```bash
pip install -r requirements.txt
```

---

## 💡 Key Takeaways

- 👥 **Gender was the strongest predictor** of survival, with women having much higher chances
- 💺 **Passenger class reflected survival inequality** - wealth and social status played crucial roles
- 👶 **Age mattered significantly** - children were prioritized during evacuation
- 👨‍👩‍👧‍👦 **Family size impacted outcomes** - small families (2-4 members) survived more than solo travelers or large families
- 🤖 **XGBoost performed best** after hyperparameter tuning, achieving the highest predictive accuracy

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Arslan Iftikhaar**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/arslan-iftikhar314/)  
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Arslaniftikhaar)

⭐ **Star this repo if you found it helpful!**

