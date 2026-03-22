# Pandas-Data-Cleaning-Learning

## 📌 Overview

This project demonstrates **end-to-end data cleaning, preprocessing, and exploratory data analysis (EDA)** using **Python (Pandas & NumPy)**.

The notebook walks through:

* Creating and exporting datasets
* Importing messy real-world data
* Cleaning and transforming data
* Handling missing values intelligently
* Performing filtering, feature engineering, and analysis

---

## 🧰 Technologies Used

* Python 🐍
* Pandas
* NumPy
* Jupyter Notebook

---

## 📂 Dataset

The project uses a dataset:

```
Messy_Employment_India_Dataset.csv
```

This dataset contains:

* Employee details
* Salary information
* Education levels
* Employment status
* Experience and age groups

---

## ⚙️ Project Workflow

### 1️⃣ Data Creation & Export

* Created a sample dataset using Python dictionaries
* Converted into a Pandas DataFrame
* Exported to CSV format

```python
df.to_csv("sample12.csv", index=False)
```

---

### 2️⃣ Data Loading

* Imported dataset using:

```python
df = pd.read_csv("Messy_Employment_India_Dataset.csv")
```

---

### 3️⃣ Initial Data Exploration

Used built-in Pandas functions:

* `df.head()` → preview data
* `df.info()` → structure & data types
* `df.describe()` → statistical summary
* `df.shape` → dataset size
* `df.columns` → column names

---

### 4️⃣ Data Cleaning

#### 🔹 Column Renaming

```python
df = df.rename(columns={"Years of Experience": "Years Exp"})
```

#### 🔹 Handling Missing Values

* Filled categorical data using **mode**
* Used **logical conditions** for smarter filling:

  * Salary-based employment status
  * Category-based imputation

#### 🔹 Fixing Inconsistent Categories

Example:

* `"Bachelors"` → `"Bachelor"`
* `"Ph.D"` → `"PhD"`
* `"high school"` → `"High School"`

---

### 5️⃣ Data Selection & Filtering

#### Selecting Columns

```python
df["Years Exp"]
df[["Years Exp", "Age Group"]]
```

#### Filtering Rows

```python
df[df["Monthly Salary (INR)"] > 149000]
```

#### Multiple Conditions

```python
df[(df["Monthly Salary (INR)"] > 130000) & (df["Monthly Salary (INR)"] < 132000)]
```

---

### 6️⃣ Feature Engineering

#### Adding New Column

```python
df["Bonus"] = df["Monthly Salary (INR)"] * 0.1
```

#### Inserting Column at Specific Position

```python
df.insert(0, "Emp_ID", np.random.randint(1, 2000, size=len(df)))
```

#### Deleting Column

```python
del df["Emp_ID"]
```

---

### 7️⃣ Handling Missing Data (Advanced)

#### ✔ Categorical Imputation

* Mode-based filling
* Distribution-based filling (probabilistic)

#### ✔ Logical Imputation

* Salary → Employment Status
* Age Group → Education mapping

---

## 🧠 Key Learnings

* Real-world data is messy and inconsistent
* Cleaning data requires **logic, not just functions**
* Categorical and numerical data require different handling techniques
* Proper preprocessing improves analysis quality significantly

---

## 🚀 How to Run

1. Clone the repository:

```bash
git clone <your-repo-link>
```

2. Install dependencies:

```bash
pip install pandas numpy
```

3. Open Jupyter Notebook:

```bash
jupyter notebook
```

4. Run `Pandas_complete.ipynb`

---
