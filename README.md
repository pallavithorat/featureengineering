# Feature Engineering Strategies — FAANG-Level Hands-On (Titanic)

**Goal:** Practice the feature engineering moves that win interviews and ship in production: missing data handling, categorical encoding, nonlinear transforms, and interaction features—*without leaking labels*.

**Outcome:** Students can:
- build leakage-safe feature pipelines with sklearn,
- choose appropriate encoding strategies,
- add meaningful interaction features,
- validate that features help via disciplined evaluation.

---

# How to Start

1. **Fork** this repository.  
2. Open `feature_student_lab.ipynb` in **Google Colab**.  
3. Complete all **TODO** sections.  
4. **Restart runtime → Run All** cells.  
5. Push changes and submit a **Pull Request**.  

⚠️ **Do NOT edit notebooks directly on GitHub.**

---

## Lab Rules (FAANG Style)

- ✅ Feature engineering is *hypothesis-driven* (state why a feature should help)
- ✅ Pipelines only: transforms must be fit on training folds only
- ✅ Compare against a baseline
- ✅ Track where leakage could occur

---

# Out of Scope

- Kaggle leaderboard optimization
- Deep learning models

---

# Notebook Rules

- Do **NOT** rename the notebook  
- Do **NOT** delete TODOs  
- Do **NOT** hardcode outputs  
- Notebook must run **top-to-bottom**  

---

# Dataset — Kaggle Titanic

Expected path:
- `data/titanic/train.csv`

Download:
- https://www.kaggle.com/competitions/titanic/data

Synthetic fallback is included if the file is missing.

---

## Section 1 — Baseline Pipeline

### Task 1.1: Baseline with minimal features

Use a clean baseline with:
- Numeric: `Age`, `Fare`, `SibSp`, `Parch`
- Categorical: `Pclass`, `Sex`, `Embarked`

**Checkpoint Questions:**

- Why is a baseline necessary before feature engineering?

---

## Section 2 — Missing Data

### Task 2.1: Missingness indicators

Add features like `Age_is_missing` / `Cabin_is_missing`.

**FAANG Gotcha:**

- Imputation can hide a strong signal: missingness itself.

---

## Section 3 — Encoding Categorical Variables

### Task 3.1: One-hot encoding (safe)

### Task 3.2: Target encoding (leakage-prone)

**Checkpoint Questions:**

- Why does naive target encoding leak? How do you fix it?

---

## Section 4 — Nonlinear Transforms + Binning

### Task 4.1: Log-transform Fare

### Task 4.2: Age buckets

---

## Section 5 — Interaction Features

### Task 5.1: Family size + IsAlone

### Task 5.2: Feature crosses (Sex × Pclass)

**Interview Angle:**

- When do interaction features help linear models?

---

## Submission Expectations

- Baseline vs engineered feature comparison (CV)
- Written answers to checkpoint questions
- At least 3 engineered features with justification

---

## FAANG Interview Evaluation Rubric

| Skill                          | Evaluated |
|-------------------------------|-----------|
| Leakage awareness              | ✅        |
| Pipeline correctness           | ✅        |
| Feature hypothesis quality     | ✅        |
| Experimental discipline (CV)   | ✅        |
| Error analysis clarity         | ✅        |

---

## Stretch Problems (Optional)

- Build out-of-fold target encoding for `Title` from `Name`
- Add `TicketGroupSize` and discuss leakage risk
- Compare calibration before/after feature engineering
