#  E-Commerce Sales Data Analysis 
## Dataset Introduction

The **Messy E-Commerce Sales Dataset 2026** is a transactional e-commerce dataset designed to represent real-world online sales data. It contains information related to customer orders, products, pricing, discounts, payment methods, shipping locations, order status, and customer ratings.

The dataset can be used to analyze **sales performance, customer purchasing behavior, product performance, pricing, discounts, payment preferences, and order fulfillment patterns**.

The dataset contains **12,000 order records** and provides a practical foundation for performing data preparation, exploratory data analysis (EDA), statistical analysis, visualization, and business-oriented analysis.

## Project Objective

The primary objective of this project is to analyze e-commerce transaction data and identify meaningful patterns in **sales, customers, products, pricing, discounts, and order fulfillment**.

### Key Objectives

* Analyze overall sales and revenue performance.
* Identify high-performing product categories and products.
* Understand customer purchasing patterns.
* Analyze the relationship between product prices, quantities, and discounts.
* Examine payment method preferences.
* Analyze order status and fulfillment patterns.
* Evaluate customer ratings to understand customer experience.
* Identify trends and patterns that can support data-driven business decisions.
* Apply data preprocessing and exploratory data analysis techniques to prepare the dataset for reliable analysis.

## Dataset Columns

| Column               | Description                                                                      |
| -------------------- | -------------------------------------------------------------------------------- |
| **Order_ID**         | Unique identifier assigned to each customer order.                               |
| **Customer_ID**      | Unique identifier representing the customer who placed the order.                |
| **Order_Date**       | Date on which the order was placed.                                              |
| **Product_Category** | Category or classification of the product purchased.                             |
| **Product_Name**     | Name of the product included in the order.                                       |
| **Quantity**         | Number of units of the product purchased in the order.                           |
| **Unit_Price_USD**   | Price of one unit of the product in US dollars.                                  |
| **Discount_Percent** | Percentage discount applied to the product or order.                             |
| **Payment_Method**   | Payment method used by the customer to complete the transaction.                 |
| **Shipping_City**    | City to which the order was shipped.                                             |
| **Country**          | Country associated with the order or shipping destination.                       |
| **Order_Status**     | Current status of the order, such as completed, pending, cancelled, or returned. |
| **Customer_Rating**  | Rating provided by the customer for the purchase/order experience.               |






## Project Outcome

The project aims to transform raw e-commerce transaction data into **actionable business insights** by combining data preprocessing, exploratory analysis, statistical techniques, and visualization. The final analysis can help identify sales trends, customer behavior, product performance, and opportunities for improving pricing, promotions, and overall e-commerce operations.


##  Project Overview

This project focuses on analyzing an e-commerce sales dataset using Python. The project covers the complete data analysis workflow, including data inspection, data cleaning, missing-value handling, duplicate detection, data-type conversion, outlier analysis, exploratory data analysis (EDA), and visualization.

The analysis aims to transform raw e-commerce transaction data into a structured and analysis-ready dataset while identifying meaningful patterns in sales, pricing, discounts, products, customers, and order performance.

**Dataset Source:** [Kaggle – Messy E-Commerce Sales Dataset 2026](https://www.kaggle.com/datasets/afaqkhan091/messy-e-commerce-sales-dataset-2026)

##  Tools & Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas** – Data manipulation and cleaning
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Git & GitHub** – Project version control and portfolio management

---



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
