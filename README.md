# NumPy and Pandas – Data Analytics Assignment

## 📌 Project Overview

This project is part of my **Python Data Analytics learning journey**.
The assignment focuses on using **NumPy** and **Pandas** to perform basic data manipulation, analysis, indexing, slicing, filtering, and aggregation.

The work was completed using **Google Colab** and Python.

---

# 🔢 Part 1: NumPy Array Operations

## 📖 Scenario

Daily average temperatures recorded over two weeks are analyzed using NumPy.

The objective is to understand NumPy arrays and perform mathematical operations, statistical calculations, indexing, slicing, and 2D array operations.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Google Colab

---

## 1. Creating a 1D NumPy Array

A 1D NumPy array named `temperatures_w1` was created for Week 1.

### Week 1 Temperatures

```python
[22.5, 25.3, 20.8, 23.4, 26.1, 24.8, 21.9]
```

```python
import numpy as np

temperatures_w1 = np.array([
    22.5, 25.3, 20.8, 23.4, 26.1, 24.8, 21.9
])
```

---

## 2. Array Inspection

The following properties were examined:

* Shape
* Data type
* Number of elements

```python
print(temperatures_w1.shape)
print(temperatures_w1.dtype)
print(temperatures_w1.size)
```

### Results

* Shape: `(7,)`
* Data Type: `float64`
* Number of Elements: `7`

---

## 3. Celsius to Fahrenheit Conversion

The temperatures were converted from Celsius to Fahrenheit using:

```text
Fahrenheit = (Celsius × 9/5) + 32
```

```python
temperatures_f = (temperatures_w1 * 9/5) + 32
```

### Fahrenheit Temperatures

```text
[72.5, 77.54, 69.44, 74.12, 78.98, 76.64, 71.42]
```

---

## 4. Temperature Statistics

Maximum, minimum, and mean temperatures were calculated.

```python
np.max(temperatures_w1)
np.min(temperatures_w1)
np.mean(temperatures_w1)
```

### Results

| Statistic           |   Value |
| ------------------- | ------: |
| Maximum Temperature |  26.1°C |
| Minimum Temperature |  20.8°C |
| Mean Temperature    | 23.54°C |

---

## 5. Array Slicing and Indexing

### First Three Days

```python
temperatures_w1[:3]
```

Result:

```text
[22.5, 25.3, 20.8]
```

### Weekend – Last Two Days

```python
temperatures_w1[-2:]
```

Result:

```text
[24.8, 21.9]
```

### Middle Three Days

```python
temperatures_w1[2:5]
```

Result:

```text
[20.8, 23.4, 26.1]
```

---

## 6. Creating a 2D NumPy Array

A 2D array was created where each row represents one week.

```python
temperatures = np.array([
    [22.5, 25.3, 20.8, 23.4, 26.1, 24.8, 21.9],
    [19.2, 22.5, 21.3, 24.0, 23.5, 22.8, 20.1]
])
```

### Array Structure

| Week   | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 |
| ------ | ----: | ----: | ----: | ----: | ----: | ----: | ----: |
| Week 1 |  22.5 |  25.3 |  20.8 |  23.4 |  26.1 |  24.8 |  21.9 |
| Week 2 |  19.2 |  22.5 |  21.3 |  24.0 |  23.5 |  22.8 |  20.1 |

### 2D Array Properties

```python
temperatures.shape
temperatures.dtype
temperatures.size
```

Results:

* Shape: `(2, 7)`
* Data Type: `float64`
* Total Elements: `14`

---

## 7. Extracting Data from 2D Array

### Week 1

```python
temperatures[0]
```

### Week 2

```python
temperatures[1]
```

### Weekends for Both Weeks

```python
temperatures[:, -2:]
```

Result:

```text
[[24.8, 21.9],
 [22.8, 20.1]]
```

---

# 🐼 Part 2: Pandas Series Operations

## 📖 Overview

Pandas Series operations were performed to understand labeled data, indexing, slicing, filtering, and data manipulation.

---

## 🛠️ Technologies Used

* Python
* Pandas
* Google Colab

---

## 1. Creating a Pandas Series

A Series named `marks` was created with custom index labels.

```python
import pandas as pd

marks = pd.Series(
    [95, 92, 89, 85, 80],
    index=['Rank1', 'Rank2', 'Rank3', 'Rank4', 'Rank5']
)
```

### Series

| Rank  | Marks |
| ----- | ----: |
| Rank1 |    95 |
| Rank2 |    92 |
| Rank3 |    89 |
| Rank4 |    85 |
| Rank5 |    80 |

---

## 2. Indexing and Slicing

### Access First Rank

```python
marks.iloc[0]
```

Result:

```text
95
```

### Top 3 Ranks Using `loc`

```python
marks.loc[['Rank1', 'Rank2', 'Rank3']]
```

### Third Rank Using `iloc`

```python
marks.iloc[2]
```

Result:

```text
89
```

### Marks Greater Than 90

```python
marks[marks > 90]
```

Result:

```text
Rank1    95
Rank2    92
```

---

## 3. Manipulating the Series

### Modify Rank1

```python
marks.loc['Rank1'] = 100
```

### Remove Rank5

```python
marks = marks.drop('Rank5')
```

### Calculate CGPA

```python
cgpa = marks / 10
```

---

# 📊 Part 3: Pandas DataFrame Operations

## 📖 Scenario

A transaction dataset containing product category, region, and transaction amount was analyzed using Pandas.

---

## 1. Creating the DataFrame

```python
transactions = pd.DataFrame({
    'TransactionID': [101, 102, 103, 104, 105, 106, 107, 108, 109, 110],

    'ProductCategory': [
        'Electronics', 'Clothing', 'Electronics', 'Furniture',
        'Clothing', 'Electronics', 'Furniture', 'Clothing',
        'Furniture', 'Electronics'
    ],

    'Region': [
        'North', 'South', 'North', 'East', 'West',
        'North', 'East', 'West', 'South', 'North'
    ],

    'Amount': [
        200, 150, 300, 450, 200,
        250, 300, 180, 350, 400
    ]
})
```

---

## 2. Data Exploration

### Display DataFrame

```python
transactions
```

### First 5 Rows

```python
transactions.head()
```

### Last 5 Rows

```python
transactions.tail()
```

### Shape

```python
transactions.shape
```

Result:

```text
(10, 4)
```

### Column Names

```python
transactions.columns
```

### Data Types

```python
transactions.dtypes
```

### Basic Information

```python
transactions.info()
```

---

## 3. Selecting Columns

### Product Category and Amount

```python
transactions[['ProductCategory', 'Amount']]
```

### Last 3 Columns

```python
transactions.iloc[:, -3:]
```

---

## 4. Filtering Data

Transactions from the **North region** with an **Amount greater than 200** were filtered.

```python
transactions[
    (transactions['Region'] == 'North') &
    (transactions['Amount'] > 200)
]
```

---

## 5. Value Counts

The number of transactions in each product category was calculated.

```python
transactions['ProductCategory'].value_counts()
```

### Result

```text
Electronics    4
Clothing       3
Furniture      3
```

---

## 6. Unique Regions

```python
transactions['Region'].unique()
```

### Result

```text
['North', 'South', 'East', 'West']
```

---

## 7. GroupBy and Mean

The average transaction amount for each region was calculated.

```python
transactions.groupby('Region')['Amount'].mean()
```

### Results

| Region | Mean Amount |
| ------ | ----------: |
| East   |      375.00 |
| North  |      287.50 |
| South  |      250.00 |
| West   |      190.00 |

---

# ✏️ Part 4: DataFrame Manipulation

## 1. Modify Transaction Amount

The amount for TransactionID `102` was changed from `150` to `165`.

```python
transactions.loc[
    transactions['TransactionID'] == 102,
    'Amount'
] = 165
```

---

## 2. Add Discount Column

A `Discount` column was created by calculating 10% of the transaction amount.

```python
transactions['Discount'] = transactions['Amount'] * 0.10
```

---

## 3. Remove TransactionID 109

```python
transactions = transactions[
    transactions['TransactionID'] != 109
]
```

---

## 4. Delete Discount Column

```python
transactions = transactions.drop(columns=['Discount'])
```

---

# 📚 Key Concepts Learned

## NumPy

* Creating 1D and 2D arrays
* Array properties
* Shape and data type
* Number of elements
* Mathematical operations
* Celsius to Fahrenheit conversion
* Maximum, minimum, and mean
* Indexing
* Slicing

## Pandas Series

* Creating Series
* Custom indexes
* `loc`
* `iloc`
* Boolean filtering
* Modifying values
* Removing values
* Basic calculations

## Pandas DataFrame

* Creating DataFrames
* Data exploration
* `head()`
* `tail()`
* `shape`
* `columns`
* `dtypes`
* `info()`
* Column selection
* Filtering
* `value_counts()`
* `unique()`
* `groupby()`
* `mean()`
* Adding columns
* Updating values
* Removing rows
* Removing columns

---

# 💡 Key Learning

This assignment helped me build a foundation in **NumPy and Pandas**, which are essential Python libraries for data analysis.

I practiced working with numerical arrays, structured datasets, filtering, indexing, slicing, aggregation, and basic data manipulation using **Google Colab**.

---

## 🚀 Next Steps

I plan to continue learning:

* Pandas Data Cleaning
* Handling Missing Values
* Data Transformation
* Data Visualization
* Exploratory Data Analysis (EDA)
* Matplotlib
* Seaborn
* SQL
* Power BI
