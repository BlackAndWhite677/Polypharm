# 💊 Polypharm

**Predicting Drug-Drug Interaction Severity Using Machine Learning From Scratch**

---

## 📖 Overview

**Polypharm** is a machine learning project that predicts the severity of drug-drug interactions (DDI) as **Low (0)**, **Medium (1)**, or **High (2)**.

All models are implemented **entirely from scratch** using only `numpy`, `pandas`, and `matplotlib` — no `sklearn`, no `PyTorch`, no `XGBoost`.

---

## 📊 Dataset

| Detail | Value |
|---|---|
| Total DDI pairs | 130,422 |
| Unique drugs | 1,902 |
| Source | DDInter pharmacological interaction database |
| Target | `interaction_severity` (3-class classification) |

**Key challenge — severe class imbalance:**

| Class | Share |
|---|---|
| Low | 5.2% |
| Medium | 74.1% |
| High | 20.6% |

---

## 🛠️ What's Built From Scratch

| Component | Details |
|---|---|
| Train-Test Split | Stratified manual split (80/20) |
| Decision Tree | Gini Index splitting |
| Weighted Decision Tree | Gini with class penalty weights |
| Naive Bayes | Gaussian likelihood, log probabilities |
| Linear SVM | Hinge loss + L2, One-vs-Rest |
| Logistic Regression | Softmax, mini-batch gradient descent |
| Stacking Ensemble | Meta-model on base predictions |
| Evaluation Metrics | Accuracy, Precision, Recall, Macro F1 |

---

## 📈 Results

| Model | Test Accuracy | Test Macro F1 |
|---|---|---|
| Linear SVM | 0.7413 | 0.2838 |
| Logistic Regression | 0.7413 | 0.3435 |
| Decision Tree | 0.7460 | 0.3833 |
| Stacking Ensemble | 0.3655 | 0.4685 |
| **Weighted Decision Tree** | 0.5311 | **0.4755** ✅ |

---

## 💡 Key Insight

> Accuracy is misleading on imbalanced medical data. A model predicting **Medium** for everything scores 74% accuracy but completely fails on the critical **High** and **Low** cases. **Macro F1** is the real metric here.

---

## 🧰 Tech Stack

`Python 3.x` · `NumPy` · `Pandas` · `Matplotlib` · `Seaborn` · `Google Colab`

---

## ▶️ How to Run

1. Open `Polypharm.ipynb` in Google Colab
2. Upload `ddinter_with_drug_severity.csv` when prompted
3. Run cells sequentially — each cell builds on the previous

---

## 📁 Project Structure

```
Polypharm/
├── Polypharm.ipynb                   # Main notebook (all code)
├── README.md                         # This file
└── ddinter_with_drug_severity.csv    # Dataset (upload manually)
```

---

## 👤 Author

**Aditi Vyshnavi S**
B.Tech Information Technology, SSN College of Engineering
