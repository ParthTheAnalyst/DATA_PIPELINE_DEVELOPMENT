# DATA_PIPELINE_DEVELOPMENT

COMPANY: CODTECH IT SOLUTIONS

NAME: PARTH CHANDWANI

INTERN ID: CT08DF409

DOMAIN: DATA SCIENCE

DURATION: 8 WEEKS

MENTOR: NEELA SANTOSH

DESCRIPTION OF THE TASK:
---

# 🧮 Salary Data ETL Pipeline

## 📌 Project Overview

This project implements an **ETL (Extract, Transform, Load) pipeline** in Python to process salary data from a CSV file (`Salaries.csv`). The goal is to clean, transform, and encode the data so it is ready for downstream tasks such as machine learning or data analysis. The final processed data is saved in `processed_salaries_data.csv`.

---

## 📂 Input & Output Files

* **Input File**: `Salaries.csv`
* **Output File**: `processed_salaries_data.csv`

---

## ⚙️ Pipeline Stages

### 1. **Extract**

* Reads data from `Salaries.csv` using `pandas.read_csv`.
* Logs initial shape, column data types, and missing value statistics.

### 2. **Clean and Feature Definition**

* Drops irrelevant columns: `Status`, `Notes`.
* Converts the following columns to numeric (with error coercion to `NaN`):

  * `BasePay`, `OvertimePay`, `OtherPay`, `Benefits`, `TotalPay`, `TotalPayBenefits`, `Year`
* Identifies:

  * Numerical features: Used for imputation and scaling.
  * Categorical features: Used for encoding.
  * Pass-through features: `Id`, `EmployeeName`

### 3. **Transform**

* Constructs a preprocessing pipeline using `scikit-learn`:

  * **Numerical features**:

    * Imputed with median values.
    * Scaled using `StandardScaler`.
  * **Categorical features**:

    * Imputed with most frequent value.
    * One-hot encoded using `OneHotEncoder`.
* Applies transformations and combines with pass-through columns.

### 4. **Load**

* Saves the final transformed dataset to `processed_salaries_data.csv`.
* Logs memory usage and final structure.

---

## 🧪 Logging & Output

The script provides detailed logs for every step:

* Extracted data shape and structure.
* Columns with missing values.
* Conversion and cleaning details.
* Transformation statistics and shapes.
* Final verification logs including a sample preview and memory usage.

---

## 🗂️ Data Overview

### 📊 Original Columns (13 total)

| Column Name      | Type    | Description                        |
| ---------------- | ------- | ---------------------------------- |
| Id               | int64   | Unique identifier                  |
| EmployeeName     | object  | Name of the employee               |
| JobTitle         | object  | Position held                      |
| BasePay          | object  | Base salary (converted to float64) |
| OvertimePay      | object  | Overtime earnings (converted)      |
| OtherPay         | object  | Other additional pay (converted)   |
| Benefits         | object  | Benefits value (converted)         |
| TotalPay         | float64 | Base + Overtime + OtherPay         |
| TotalPayBenefits | float64 | TotalPay + Benefits                |
| Year             | int64   | Year of record (converted)         |
| Notes            | object  | Dropped due to being empty         |
| Agency           | object  | Employer agency                    |
| Status           | object  | Dropped due to being irrelevant    |

---

## 🧠 Features After Transformation

* Total columns after encoding: **2169**
* Dtype distribution: `float64 (2167)`, `int64 (1)`, `object (1)`
* Memory Usage: **\~2.4 GB**

---

## 📌 How to Run

1. Place the input file `Salaries.csv` in the project directory.
2. Run the ETL script:

   ```bash
   python pipeline.py
   ```
3. The output file `processed_salaries_data.csv` will be created.

---

## 🛠️ Dependencies

* `pandas`
* `numpy`
* `scikit-learn`
* Python 3.13+

---

## 🔍 Optional: Sample Output (First 5 Rows)

```
   Id    EmployeeName    ...    cat__JobTitle_ZOO CURATOR   cat__Agency_San Francisco
0   1     NATHANIEL FORD   ...                   0.0                       1.0
1   2       GARY JIMENEZ   ...                   0.0                       1.0
2   3     ALBERT PARDINI   ...                   0.0                       1.0
3   4   CHRISTOPHER CHONG ...                   0.0                       1.0
4   5     PATRICK GARDNER ...                   0.0                       1.0
```

---

![Image](https://github.com/user-attachments/assets/c402cd11-c6ef-4c30-ae63-e1b9c25ea41e)
![Image](https://github.com/user-attachments/assets/d2079155-3ca2-4d74-b9ca-7e2278448dfb)
![Image](https://github.com/user-attachments/assets/9f83646f-1234-423b-ab8a-67843362f050)
![Image](https://github.com/user-attachments/assets/7b2064b3-5c81-42bb-b562-b5ec9e4abc6c)
![Image](https://github.com/user-attachments/assets/062d4c57-aefb-4bbf-a925-dc4966479af2)
