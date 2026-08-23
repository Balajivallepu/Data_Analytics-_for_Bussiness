# Retail Business Analytics and Sales Performance Dashboard

## 📊 Project Overview

The **Retail Business Analytics and Sales Performance Dashboard** is an end-to-end Business Intelligence project developed to analyze retail sales, products, customers, orders, and geographical performance.

The project transforms raw retail transaction data into meaningful business insights using **MySQL, SQL, Power Query, Power BI, DAX, Power BI Service, and GitHub**.

---

## 🎯 Objectives

* Import and manage retail transaction data.
* Clean and validate raw sales data.
* Build a structured MySQL database.
* Create a star-schema data model.
* Connect MySQL with Power BI.
* Develop DAX-based business KPIs.
* Analyze sales trends and performance.
* Identify top-performing products.
* Analyze customer and country performance.
* Perform sales forecasting.
* Implement What-If analysis.
* Implement Row-Level Security.
* Publish the dashboard using Power BI Service.
* Maintain project documentation using GitHub.

---

## 🛠️ Technology Stack

| Technology       | Purpose                           |
| ---------------- | --------------------------------- |
| CSV              | Source Dataset                    |
| MySQL Workbench  | Database Management               |
| SQL              | Data Cleaning and Transformation  |
| Power Query      | Data Preparation                  |
| Power BI Desktop | Dashboard Development             |
| DAX              | KPI Calculations                  |
| Power BI Service | Report Publishing                 |
| GitHub           | Version Control and Documentation |

---

## 🏗️ Project Architecture

```text
Raw CSV Dataset
       ↓
     MySQL
       ↓
Data Cleaning
       ↓
   Star Schema
       ↓
   SQL Views
       ↓
  Power Query
       ↓
   Power BI
       ↓
      DAX
       ↓
 Interactive Dashboard
       ↓
Forecasting / What-If / RLS
       ↓
Power BI Service
       ↓
 Business Insights
```

---

## 🗄️ Database Design

The project uses a **Star Schema**.

### Fact Table

* `FactSales`

### Dimension Tables

* `DimProduct`
* `DimCustomer`
* `DimCountry`
* `DimDate`

### FactSales Measures

* Quantity
* Unit Price
* Sales Amount
* Orders

---

## 🧹 Data Cleaning

The raw retail dataset is processed using MySQL.

The cleaning process includes:

* Removing unnecessary spaces.
* Converting invoice dates into valid date/time values.
* Removing invalid quantities.
* Removing invalid prices.
* Removing records with invalid dates.
* Handling missing Customer IDs.
* Creating the `SalesAmount` field.

Sales amount is calculated as:

```text
SalesAmount = Quantity × UnitPrice
```

---

## 📈 Power BI Dashboard

The Power BI report contains multiple analytical pages.

### Page 1 — Executive Dashboard

Provides an overall view of:

* Total Sales
* Total Orders
* Total Customers
* Total Quantity
* Average Order Value
* Sales Growth
* Sales by Country
* Top Products
* Yearly Sales Trend

### Page 2 — Sales Analysis

Provides:

* Monthly Sales Trend
* Sales by Country
* Sales by Year
* Orders by Country
* YTD Sales
* Average Order Value

### Page 3 — Product Analysis

Provides:

* Top 10 Products by Sales
* Top 10 Products by Quantity
* Product Sales vs Quantity
* Product Orders
* Average Unit Price
* Product Performance Table

### Page 4 — Customer & Geography

Provides:

* Total Customers
* Total Orders
* Sales per Customer
* Sales by Country
* Orders by Country
* Customer Distribution

### Page 5 — Sales Forecast

Provides:

* Historical Sales Trend
* Sales Forecast
* Future Sales Planning
* Trend Analysis

---

## 📊 Key DAX Measures

### Total Sales

```DAX
Total Sales =
SUM(FactSales[SalesAmount])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(FactSales[InvoiceNo])
```

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(FactSales[CustomerKey])
```

### Total Quantity

```DAX
Total Quantity =
SUM(FactSales[Quantity])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders],
    0
)
```

### Sales per Customer

```DAX
Sales per Customer =
DIVIDE(
    [Total Sales],
    [Total Customers],
    0
)
```

### Previous Year Sales

```DAX
Previous Year Sales =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(DimDate[Date])
)
```

### Sales Growth

```DAX
Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
```

### YTD Sales

```DAX
YTD Sales =
TOTALYTD(
    [Total Sales],
    DimDate[Date]
)
```

---

## 🎨 Dashboard Color Theme

The project uses a consistent professional color theme.

| Element    | HEX       |
| ---------- | --------- |
| Header     | `#12355B` |
| Sales      | `#1976D2` |
| Orders     | `#2E7D32` |
| Customers  | `#7B1FA2` |
| Quantity   | `#F57C00` |
| AOV        | `#C62828` |
| Growth     | `#2E7D32` |
| Background | `#F5F7FA` |
| Card       | `#FFFFFF` |
| Text       | `#263238` |
| Border     | `#D9E1E8` |

---

## 🔐 What-If Analysis

A **Discount % What-If parameter** is created to analyze the effect of discounts on projected sales.

Configuration:

```text
Minimum: 0%
Maximum: 30%
Increment: 5%
Default: 10%
```

This allows management to test different discount scenarios.

---

## 🔒 Row-Level Security

Row-Level Security is implemented in Power BI to restrict access to specific country-level data.

Example:

```text
Role: Country Manager

Country:
United Kingdom
```

This ensures that authorized users only access the data relevant to their assigned role.

---

## ☁️ Power BI Service

The completed Power BI report can be published to **Power BI Service**.

```text
Power BI Desktop
       ↓
     Publish
       ↓
Power BI Workspace
       ↓
Power BI Service
       ↓
Business Users
```

For automatic refresh from a locally hosted MySQL database, an appropriate on-premises data gateway and database credentials must be configured.

---

## 📁 Repository Structure

```text
retail-business-analytics/
│
├── dataset/
│   └── data(1).csv
│
├── sql/
│   ├── 01_database_setup.sql
│   ├── 02_data_cleaning.sql
│   ├── 03_star_schema.sql
│   └── 04_sql_views.sql
│
├── powerbi/
│   └── Retail_Business_Analytics.pbix
│
├── screenshots/
│   ├── 01_executive_dashboard.png
│   ├── 02_sales_analysis.png
│   ├── 03_product_analysis.png
│   ├── 04_customer_geography.png
│   ├── 05_sales_forecast.png
│   ├── 06_mysql_database.png
│   ├── 07_powerbi_model.png
│   └── 08_powerbi_service.png
│
├── documentation/
│   └── Retail_Business_Analytics_Report.pdf
│
├── presentation/
│   └── Retail_Business_Analytics_Presentation.pptx
│
└── README.md
```

---

## 💼 Business Questions

The dashboard answers:

1. What is the total sales revenue?
2. How many orders were generated?
3. How many customers purchased?
4. Which products generate the highest sales?
5. Which products have the highest quantity sold?
6. Which countries generate the highest revenue?
7. What is the yearly sales trend?
8. What is the average order value?
9. How does sales performance change over time?
10. Which products and markets should management prioritize?

---

## 💡 Business Value

The project supports management in:

* Sales monitoring
* Product performance analysis
* Inventory planning
* Customer analysis
* Market analysis
* Marketing decisions
* Revenue planning
* Sales forecasting
* Performance monitoring

---

## 📌 Project Learning Outcomes

Through this project, practical knowledge was gained in:

* MySQL database management
* SQL data cleaning
* Star-schema design
* Power Query
* Power BI data modeling
* DAX
* KPI development
* Interactive dashboard design
* Sales forecasting
* What-If analysis
* Row-Level Security
* Power BI Service
* GitHub project management

---

## 🚀 Future Scope

The project can be enhanced by implementing:

* Machine learning-based sales prediction
* Customer segmentation
* RFM analysis
* Customer churn prediction
* Product demand forecasting
* Real-time dashboards
* Cloud database integration
* Automated business alerts
* Advanced customer lifetime value analysis

---

## 🎓 Academic Project

**Project Name:** Retail Business Analytics and Sales Performance Dashboard

**Course:** Master of Computer Applications (MCA)

**Academic Year:** 2026


---

## 📄 Project Deliverables

* `Retail_Business_Analytics.pbix`
* Retail dataset
* MySQL SQL scripts
* Power BI screenshots
* Project Report PDF
* Final PowerPoint presentation
* GitHub repository
* Power BI Service report/link, if available

---

## ⭐ Conclusion

This project demonstrates a complete **end-to-end Business Intelligence workflow**, starting from raw retail transaction data and progressing through MySQL data management, data cleaning, star-schema modeling, Power BI visualization, DAX analytics, forecasting, What-If analysis, security, and cloud reporting.

The final dashboard converts raw retail data into actionable business information that can support better **sales, product, customer, inventory, and strategic decision-making**.
