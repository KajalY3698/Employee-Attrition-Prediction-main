

# 🏢 Will They Stay or Will They Go?
### *Predicting Employee Attrition Before It's Too Late*

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Status](https://img.shields.io/badge/Status-Complete-28a745?style=for-the-badge)]()
[![Dataset](https://img.shields.io/badge/IBM-HR%20Dataset-054ADA?style=for-the-badge&logo=ibm&logoColor=white)]()

</div>

---

## 🎬 The Story Behind The Model

> *"It costs 6-9 months of an employee's salary to replace them."*
> — SHRM Research

Every time a talented employee resigns, companies lose money, knowledge, and team morale. HR teams often see it coming — but too late to act.

**This project turns hindsight into foresight.** Using machine learning on IBM's real-world HR dataset, I built a model that identifies flight-risk employees *before* they hand in their resignation letter.

---

## ⚡ What Can This Model Do?

```
Given an employee profile  →  Model predicts  →  Take action early
─────────────────────────     ──────────────     ──────────────────
Age: 32                        🔴 HIGH RISK       Schedule 1:1
Salary: Below Average          Attrition: YES     Offer raise/promotion
Satisfaction: Low                                 Review workload
Overtime: Always
```

---

## 📊 The Dataset at a Glance

| Property | Value |
|---|---|
| 📁 Source | IBM HR Analytics (Kaggle) |
| 👥 Employees | 1,470 records |
| 🔢 Features | 35 attributes |
| 🎯 Target | `Attrition` → Yes / No |
| ⚖️ Class Balance | ~84% No, ~16% Yes *(imbalanced!)* |

---

## 🔍 What Drives Attrition? (Spoiler)

After training and feature importance analysis, these were the **biggest red flags**:

```
🥇  Monthly Income          ███████████████████  Lowest earners leave most
🥈  Overtime                ███████████████████   Burnout is real
🥉  Job Satisfaction        ███████████████████    Unhappy = unstable
4️⃣  Age                     ███████████████████    Younger employees move faster
5️⃣  Work-Life Balance       ███████████████████      People value their time
6️⃣  Years at Company        ███████████████████        The 2-year itch is real
```

---

## 🛠️ How It Was Built

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐     ┌────────────┐
│  Raw Data   │────▶│     EDA      │────▶│  Feature    │────▶│   SMOTE    │
│  (35 cols)  │     │  & Cleaning  │     │ Engineering │     │(Fix Imbal.)│
└─────────────┘     └──────────────┘     └─────────────┘     └────────────┘
                                                                     │
┌─────────────┐     ┌──────────────┐     ┌─────────────┐            ▼
│  Results &  │◀────│  Evaluation  │◀────│   Random    │◀────┌────────────┐
│  Insights   │     │  (F1, ROC)   │     │   Forest    │     │  Training  │
└─────────────┘     └──────────────┘     └─────────────┘     └────────────┘
```

### Why Random Forest?
- Handles mixed data types (categorical + numerical) natively
- Built-in feature importance ranking
- Robust to outliers — HR data is messy
- No need for feature scaling

### Why SMOTE?
Because only **16% of employees actually left** — a naive model would just predict "No" for everyone and get 84% accuracy. SMOTE synthetically balances the dataset so the model actually *learns* what attrition looks like.

---

## 📈 Model Performance

| Metric | Score |
|---|---|
| Accuracy | ~87% |
| Precision (Attrition) | ~78% |
| Recall (Attrition) | ~81% |
| ROC-AUC | ~0.91 |

> 📌 *Recall matters more here — missing a flight-risk employee is more costly than a false alarm.*

---

## 🚀 Run It Yourself

```bash
# 1. Clone the repo
git clone https://github.com/your-username/employee-attrition.git
cd employee-attrition

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux

# 3. Launch the notebook
jupyter notebook Employee_Attrition.

```

---

## 📁 Project Structure

```
employee-attrition/
│
├── 📓 Employee_Attrition.ipynb   ← Main notebook (EDA + Model)
├── 📊 WA_Fn-UseC_-HR-Employee-Attrition.csv  ← Dataset
└── 📖 README.md
```

---

## 💡 Real-World Application

This model can be used by HR teams to:

- 🔔 **Flag employees** with high attrition probability monthly
- 📋 **Prioritize retention conversations** with at-risk employees
- 💰 **Reduce turnover costs** by acting before resignations happen
- 📊 **Identify systemic issues** (e.g., overtime culture, low pay bands)

---


<div align="center">
  <sub>Built with 🧠 curiosity and ☕ chai | © 2026</sub>
</div>
