
Supply Chain Customer Shopping Behavior Analysis

Overview
This project provides a end-to-end data analytics solution designed to help a leading retail chain understand customer purchasing patterns, demographic segments, and shopping preferences. By analysing historical transaction data, the goal is to extract actionable business insights that drive customer retention, optimize marketing strategies, and increase overall revenue.

Dataset
Source: Customer Shopping Behavior Dataset
Key Attributes:
Customer Profile: `Customer ID`, `Age`, `Gender`, `Location`, `Subscription Status`
Purchase Details:** `Item Purchased`, `Category`, `Purchase Amount (USD)`, `Review Rating`
Shopping Preferences:  `Size`, `Color`, `Season`, `Payment Method`, `Shipping Type`, `Discount Applied`, `Promo Code Used`, `Previous Purchases`, `Frequency of Purchases`

Tools & Technologies
Python (Pandas, NumPy, Matplotlib, Seaborn): Initial data ingestion, Data Quality Assessment (DQA), missing value imputation, outlier detection, and Exploratory Data Analysis (EDA).
MySQL Workbench:  Database schema setup, structured data loading, advanced SQL queries (aggregations, CTEs, window functions, and subqueries) for business logic extraction.
Power BI Desktop: Data modelling (star schema), DAX measures, and dynamic dashboard creation.
Gamma App: Visual presentation deck generation for stakeholder presentation.
Report: Documentation and project reporting.

Project Execution Steps
1. Data Ingestion & Exploratory Data Analysis (Python)
1.	Loaded raw transaction CSV file into Jupyter Notebook / PyCharm environment.
2.	Conducted initial data inspection: checked data types, null counts, summary statistics (`.describe()`), and distribution curves.
3.	Identified key trends, correlation matrices, and skewed numerical features.

2. Data Cleaning & Transformation
1.	Missing Values:  Imputed missing entries based on categorical modes and group-wise numerical medians.
2.	Feature Engineering:  Created derived attributes such as `Age Group` (e.g., Youth, Adult, Senior) and `Loyalty Tier` based on `Previous Purchases`.
3.	Standardization: Cleaned string formatting and standardized category values across all columns.

3. Database Management & SQL Queries (MySQL Workbench)
1.	Automated Database Population: Exported the processed DataFrame directly from Python into MySQL Workbench using sqlalchemy / pymysql to establish the Customer behavior database and table structure.
2.	Authored SQL queries to answer core business questions:
3.	Revenue breakdown by category and gender.
4.	Customer lifetime purchase frequency vs. subscription status.
5.	Impact of promo codes and discounts on average order value (AOV).
6.	Top-performing shipping methods and payment preferences across age demographics.

4. Data Modelling & Power BI Dashboard
* Imported cleaned dataset and SQL view outputs into Power BI Desktop.
* Established a dimensional star-schema model.
* Developed custom DAX metrics:
1.	`Total Revenue = SUM(Transactions[Purchase Amount])`
2.	`Average Order Value (AOV) = AVERAGE(Transactions[Purchase Amount ])`
3.	`Customer Retention Rate` & `Promo Usage Ratio`

* Designed interactive dashboard tabs:
1.	Executive Overview: High-level KPIs, monthly sales trends, category contribution.
2.	Customer Behavior & Demographics: Age/Gender distribution, loyalty segment analysis, subscription impact.
3.	Product & Channel Performance: Top items, discount effectiveness, payment and shipping trends.

5. Reporting & PPT Generation (Gamma)
1.	Summarized core insights into a concise PDF / Markdown executive summary report.
2.	Processed business findings into Gamma App to generate a visually polished, executive-ready presentation deck for business stakeholders.


Key Results & Business Insights
Promo Code & Discount Impact: Promo code usage increased total transaction volume, but Average Order Value (AOV) was slightly higher among non-discounted purchases, suggesting discounts drive volume rather than basket size.
Subscription Drive:  Subscribed customers demonstrate higher repeat purchase frequency compared to non-subscribers, indicating strong retention potential via loyalty perks.
Demographic Highlights: The 25–40 age bracket accounts for the highest total spend, with a preference for Clothing and Footwear categories during Autumn and Winter seasons.
Payment & Shipping: Credit card and Mobile Payments are the dominant transaction methods, while Free Shipping significantly correlates with higher customer review ratings.

How to Run This Project

Prerequisites
Python 3.8+ (Pandas, NumPy, Matplotlib, Seaborn, MySQL Connector)
MySQL Server & MySQL Workbench
Power BI Desktop

Installation & Setup

1. Clone the Repository:
   ```bash
   git clone https://github.com/Priyankaewp/customer-behavior-analysis.git
   cd customer-behavior-analysis

https://github.com/Priyankaewp/Customer-Shopping-Analysis
   ```

2. Run Python Scripts (EDA & Cleaning):
   ```bash
   pip install -r requirements.txt
   python scripts/ DA Project Customer_Shopping_Behavior.py
   ```
   *Output:* Generates `customer_shopping_behavior.csv` in the `data/` folder.

3. Set Up MySQL Database:
   * Open MySQL Workbench and execute ` Proj_Customer_Behavior.sql ` to build tables.
   * Load ` customer_shopping_behavior.csv` into the database.
   * Execute `sql/ Proj_Customer_Behavior.sql ` to generate analytical views.

4. Open Power BI Dashboard:
   * Launch Power BI Desktop and open `dashboards/ DA Project Customer_Shopping_Behavior_Dashboard.pbix`.
   * Update data source file path or database credentials if prompted to refresh visuals.

Repository Structure
```
├── data/
│   ├── customer_shopping_behavior_raw.csv
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── DA Project Customer_Shopping_Behavior.ipynb
├── sql/
│   └── Proj_Customer_Behavior.sql
├── dashboards/
│   └── Customer_Shopping_Behavior_Dashboard.pbix
├── presentation/
│   └── Customer-Shopping-Behavior-Analysis.pdf
├── README.md
└── requirements.txt



