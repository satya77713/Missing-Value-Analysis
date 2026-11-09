# Missing Value Analysis using Pandas

## Overview

This project is part of the Veda Technology AI & ML Internship.

The objective of this task is to identify missing values in a dataset and calculate the number and percentage of missing values in each column using Python and Pandas.

The Titanic dataset is used to perform missing-value analysis and understand the importance of handling missing data before applying machine learning algorithms.

## Objective

- Identify missing values in a dataset.
- Calculate column-wise missing-value counts.
- Calculate the percentage of missing values.
- Identify columns that require missing-value treatment.
- Understand the importance of data quality in machine learning.

## Dataset Information

- **Dataset:** Titanic Dataset
- **File:** Titanic CSV Dataset
- **Source:** [Titanic Dataset – CSV](https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv)
- **Format:** CSV

## Tools & Technologies

- Python
- Pandas
- Matplotlib
- Google Colab

## Analysis Performed

### 1. Load the Dataset

Loaded the Titanic dataset using Pandas.

```python
df = pd.read_csv(url)
```

### 2. Identify Missing Values

Used `isnull()` to identify missing values in each column.

```python
missing_counts = df.isnull().sum()
```

### 3. Calculate Total Missing Values

Calculated the total number of missing values in the dataset.

```python
total_missing = df.isnull().sum().sum()
```

### 4. Calculate Missing Value Percentage

Calculated the percentage of missing values in each column.

```python
missing_percentage = (
    df.isnull().sum() / len(df) * 100
).round(2)
```

### 5. Create Missing Value Summary

Created a DataFrame containing missing-value counts and percentages.

```python
missing_summary = pd.DataFrame({
    'Missing Count': missing_counts,
    'Missing Percentage': missing_percentage
})
```

### 6. Identify Columns Requiring Treatment

Identified columns that contain one or more missing values.

```python
columns_to_treat = missing_summary[
    missing_summary['Missing Count'] > 0
]
```

### 7. Identify Rows with Missing Values

Used Boolean indexing to find records containing missing values.

```python
missing_rows = df[df.isnull().any(axis=1)]
```

### 8. Visualize Missing Values

Used Matplotlib to create a bar chart showing missing-value counts by column.

## Key Concepts Learned

- Understanding missing data.
- Detecting missing values using `isnull()`.
- Counting missing values using `sum()`.
- Calculating missing-value percentages.
- Creating a missing-value summary.
- Identifying columns requiring treatment.
- Visualizing missing data using Matplotlib.

## Project Structure

```text
Missing-Value-Analysis/
│
├── Missing_Value_Analysis.ipynb
├── README.md
└── Titanic.csv (optional)
```

The notebook loads the dataset directly from its online CSV source, so a separate dataset file is optional.

## How to Run

1. Open Google Colab.
2. Upload or open `Missing_Value_Analysis.ipynb`.
3. Run the notebook cells.
4. The Titanic dataset will be loaded from the CSV link.
5. View the missing-value counts and percentages.
6. Review the columns requiring treatment and the missing-value visualization.

## Internship Details

- **Organization:** Veda Technology
- **Track:** AI & ML Internship
- **Task:** 21 – Missing Value Analysis

## Conclusion

This task provided practical experience in identifying and analyzing missing values using Pandas. Understanding missing data is an important step in data preprocessing because missing values can affect data quality and machine learning model performance.
