# 🔐 Leveraging Artificial Intelligence for Predictive Cybersecurity Threat Intelligence

> M.Sc. Cybersecurity Applied Research Project — Dublin Business School, 2025  
> **Author:** Vimalkanth Muthaliyappan Veerakumar | **Student ID:** 20025544  
> **Supervisor:** Ankush Arya

---

## 📌 Project Overview

This project develops and evaluates an AI/ML-based framework for **predictive cybersecurity threat intelligence**, with a focus on detecting **minority-class cyber attacks** (Bot traffic, infiltration, APTs) in highly imbalanced network traffic datasets.

The core challenge addressed: traditional ML models are biased toward the majority class (benign traffic), causing them to **miss rare but dangerous attacks**. This project uses **SMOTE** oversampling and compares four classification models to solve this.

---

## 🧠 Models Evaluated

| Model | Accuracy | Bot Recall | Bot F1-Score |
|---|---|---|---|
| Random Forest | **1.00** | **1.00** | **1.00** |
| XGBoost | **1.00** | **1.00** | **1.00** |
| SVM (LinearSVC) | 0.96 | 1.00 | 0.93 |
| Logistic Regression | 0.97 | 1.00 | 0.95 |

> ⚠️ Perfect scores on RF and XGBoost are likely influenced by SMOTE-generated synthetic samples closely mirroring training data. Cross-validation on real-world data is recommended before deployment.

---

## 📂 Repository Structure

```
cybersecurity-threat-intelligence/
│
├── notebooks/
│   └── Artefacts.ipynb           # Main ML pipeline notebook
│
├── data/
│   └── README_data.md            # Dataset info & download instructions
│
├── results/
│   ├── random_forest_report.txt
│   ├── xgboost_report.txt
│   ├── svm_report.txt
│   └── logistic_regression_report.txt
│
├── docs/
│   └── Applied_Research_Project.pdf   # Full thesis document
│
├── requirements.txt               # Python dependencies
├── .gitignore
└── README.md
```

---

## 📊 Dataset

**CIC-IDS2018 (UNB, 2018)** — Canadian Institute for Cybersecurity Intrusion Detection Dataset

- **Rows:** 1,048,575 | **Features:** 80 | **Target:** `Label` (Benign / Bot)
- The dataset is **not included** in this repository due to its large size (~336 MB).
- 📥 Download from: [https://www.unb.ca/cic/datasets/ids-2018.html](https://www.unb.ca/cic/datasets/ids-2018.html)
- After downloading, place the file at: `data/CIC-IDS2018.csv`

**Class Imbalance:**

| Class | Count |
|---|---|
| Benign | ~700,000 |
| Bot | ~286,000 |

After SMOTE: Both classes balanced to **608,644 records** each.

---

## ⚙️ Methodology (CRISP-DM)

```
1. Business Understanding  →  Detect rare cyber threats proactively
2. Data Understanding      →  EDA on CIC-IDS2018 (class dist, flow analysis, port analysis)
3. Data Preprocessing      →  Remove duplicates, encode labels, handle inf/NaN, drop Timestamp
4. Modeling                →  Random Forest, XGBoost, SVM, Logistic Regression
5. Evaluation              →  Precision, Recall, F1-Score, Confusion Matrix
6. Deployment              →  Framework for real-time SOC integration
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/cybersecurity-threat-intelligence.git
cd cybersecurity-threat-intelligence
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Add the dataset

Download the CIC-IDS2018 dataset and place it at:

```
data/CIC-IDS2018.csv
```

### 4. Run the notebook

```bash
jupyter notebook notebooks/Artefacts.ipynb
```

Or open directly in **Google Colab** (recommended for large dataset):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

> If using Colab, upload the CSV to your Google Drive and update the path in Cell 2:
> ```python
> df = pd.read_csv('/content/drive/MyDrive/CIC-IDS2018.csv')
> ```

---

## 🔬 Key Findings

- **SMOTE** successfully resolved class imbalance, balancing both classes to 608,644 samples
- **Random Forest & XGBoost** achieved perfect classification scores on the balanced dataset
- **SVM & Logistic Regression** achieved perfect bot recall (1.00) with slightly lower benign precision
- All models exceeded the **90% recall threshold** for malicious traffic — satisfying H1
- Ensemble models significantly outperformed linear models on non-linear feature relationships

---

## 🛠️ Tech Stack

- **Language:** Python 3.x
- **ML Libraries:** scikit-learn, XGBoost, imbalanced-learn
- **Data Processing:** pandas, NumPy
- **Visualisation:** Matplotlib, Seaborn
- **Environment:** Google Colab / Jupyter Notebook

---

## 🔮 Future Work

- [ ] Apply **SHAP / LIME** for model explainability
- [ ] Test with **ADASYN** and **SMOTE-ENN** hybrid resampling
- [ ] Validate models on **live network traffic** for real-world generalisation
- [ ] Implement **continuous retraining** pipeline for emerging threats
- [ ] Extend to multi-class attack classification (infiltration, DDoS, web attacks, APTs)

---

## 📄 Citation

If you use this project in your work, please cite:

```
Vimalkanth, M.V. (2025). Leveraging Artificial Intelligence for Predictive 
Cybersecurity Threat Intelligence. M.Sc. Applied Research Project, 
Dublin Business School.
```

---

## 📜 License

This project is for academic purposes. Dataset usage is subject to the 
[UNB CIC-IDS2018 terms of use](https://www.unb.ca/cic/datasets/ids-2018.html).
