 E-Commerce-Sales-Analysis
To analyze e-commerce sales and customer transaction data to identify sales trends, customer purchasing patterns, product performance, and factors influencing revenue, while preparing the dataset for reliable analysis through appropriate data preprocessing.
Objective
To analyze e-commerce sales and customer purchasing patterns to identify trends, product performance, and factors influencing sales and revenue.
Dataset
.Source: Kaggle-E-Commerce Sales Dataset(https://www.kaggle.com/datasets/afaqkhan091/messy-e-commerce-sales-dataset-2026)
.12,181 Rows,12 Columns of e-commerce sales of products and categories
Project Steps & Data Cleaning
.Loaded the raw e-commerce transaction dataset using Pandas.
.Performed initial data exploration using head(), shape, info(), describe(), and column inspection.
.Identified missing values and duplicate records.
.Handled missing values:
.Filled missing Discount_Percent with 0.
.Replaced missing Shipping_City with "Unknown".
.Imputed missing Customer_Rating using the median.
.Removed duplicate records from the dataset.
.Converted mixed-format Order_Date values into a standardized DD-MM-YY format.
.Standardized inconsistent Payment_Method values such as PayPal, UPI, Net Banking, Credit Card, and Cash on Delivery.
.Standardized inconsistent Country names and abbreviations such as USA, US, U.S.A, and United States.
.Handled missing text values in the Shipping_City column.
.Created a Gross Revenue column using Quantity × Unit Price.
.Calculated Discount Amount based on Gross Revenue and Discount Percentage.
.Calculated Net Revenue after deducting discounts from Gross Revenue.
.Created an Is_Discounted flag to identify discounted orders.
.Performed statistical analysis on numerical variables using Mean, Median, Mode, Minimum, Maximum, Range, Variance, and Standard Deviation.
