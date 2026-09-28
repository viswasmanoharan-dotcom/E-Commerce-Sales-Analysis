#  E-Commerce Sales Data Analysis & Cleaning

##  Project Overview

This project focuses on analyzing an e-commerce sales dataset using Python. The project covers the complete data analysis workflow, including data inspection, data cleaning, missing-value handling, duplicate detection, data-type conversion, outlier analysis, exploratory data analysis (EDA), and visualization.

The analysis aims to transform raw e-commerce transaction data into a structured and analysis-ready dataset while identifying meaningful patterns in sales, pricing, discounts, products, customers, and order performance.

**Dataset Source:** [Kaggle – Messy E-Commerce Sales Dataset 2026](https://www.kaggle.com/datasets/afaqkhan091/messy-e-commerce-sales-dataset-2026)

---

## 🎯 Project Objective

* Clean and preprocess raw e-commerce transaction data to improve data quality and consistency.
* Analyze sales, pricing, discounts, product categories, customer ratings, and order-related patterns to generate useful business insights.

---

##  Tools & Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas** – Data manipulation and cleaning
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Git & GitHub** – Project version control and portfolio management

---

##  Dataset

The dataset contains e-commerce transaction information, including fields related to:

* Order details
* Customer information
* Product categories and names
* Quantity
* Unit price
* Discount percentage
* Payment methods
* Shipping information
* Country
* Order status
* Customer ratings

---

##  Data Cleaning Steps

### 1. Data Inspection

Initial inspection was performed to understand the structure and quality of the dataset.

```python
df.head()
df.shape
df.info()
df.describe()
```

### 2. Missing Value Detection

Missing values were identified using:

```python
df.isnull().sum()
```

Missing values were handled using appropriate methods depending on the column type and business context.

### 3. Duplicate Detection

Duplicate records were checked using:

```python
df.duplicated().sum()
```

Duplicate records were removed where appropriate.

```python
df = df.drop_duplicates()
```

### 4. Data Type Conversion

Columns containing dates and numerical values were converted into appropriate data types.

For example:

```python
df['Order_Date'] = pd.to_datetime(df['Order_Date'])
```

This makes the data easier to use for time-based analysis.

### 5. Text/Data Standardization

Categorical and text fields were checked for inconsistent formatting, unnecessary spaces, and inconsistent representations.

Example:

```python
df['Product_Category'] = df['Product_Category'].str.strip()
```

### 6. Outlier Detection

The **Interquartile Range (IQR)** method was used to identify potential outliers in numerical variables such as:

* Quantity
* Unit Price
* Discount Percentage
* Customer Rating

Example:

```python
Q1 = df['Unit_Price_USD'].quantile(0.25)
Q3 = df['Unit_Price_USD'].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
```

Potential outliers were investigated before deciding whether they should be retained, capped, or removed.

### 7. Outlier Treatment

For values identified as invalid or inappropriate for analysis, the corresponding records were removed or treated using an appropriate method.

For example:

```python
df = df[
    (df['Unit_Price_USD'] >= lower_bound) &
    (df['Unit_Price_USD'] <= upper_bound)
]
```

### 8. Final Data Validation

After cleaning, the dataset was checked again for:

```python
df.isnull().sum()
df.duplicated().sum()
df.info()
df.describe()
```

This ensured that the final dataset was suitable for exploratory analysis.

---

## 📈 Exploratory Data Analysis

After cleaning, the dataset can be analyzed to identify:

* Sales trends over time
* Product category performance
* Product pricing patterns
* Discount distribution
* Order-status distribution
* Payment-method usage
* Customer-rating patterns
* Quantity and sales relationships
* High- and low-priced products
* Relationship between discounts and sales

Visualizations were created using **Matplotlib and Seaborn**.

---

## 🔍 Key Analysis Areas

### Sales Analysis

Analyze sales patterns across dates, product categories, and order statuses.

### Product Analysis

Identify product categories and products with different pricing and demand patterns.

### Pricing Analysis

Study unit-price distributions and identify unusual pricing values using statistical techniques.

### Customer Analysis

Analyze customer ratings and purchasing-related patterns.

### Discount Analysis

Examine discount percentages and their relationship with sales-related variables.

---

##  Project Structure

```text
E-Commerce-Sales-Analysis/
│
├── data/
│   └── ecommerce_sales.csv
│
├── notebooks/
│   └── ecommerce_sales_analysis.ipynb
│
├── visualizations/
│   ├── sales_trend.png
│   ├── category_analysis.png
│   └── price_distribution.png
│
├── README.md
└── requirements.txt
```

---

##  Skills Demonstrated

* Data Cleaning
* Data Preprocessing
* Missing Value Handling
* Duplicate Detection
* Data Type Conversion
* Data Standardization
* Outlier Detection
* Exploratory Data Analysis
* Statistical Analysis
* Data Visualization
* Business-oriented Data Interpretation
* Python/Pandas/NumPy
* Matplotlib/Seaborn

---

##  Conclusion

This project demonstrates the ability to take raw e-commerce transaction data, identify data-quality issues, perform systematic data cleaning, analyze numerical and categorical variables, detect potential outliers, and create visualizations to support business-oriented analysis.

The cleaned dataset provides a reliable foundation for further **sales analytics, customer analytics, product analysis, and business intelligence** projects.
