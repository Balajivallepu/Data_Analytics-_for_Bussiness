# FINANCE KPI DASHBOARD

Project: Developing Finance KPI Dashboards

Course:
Data Analytics for Business

Program:
Master of Computer Applications (MCA)

Semester:
III

Experiment No.:
7

1. PROJECT OVERVIEW

---

This project develops an interactive Finance KPI Dashboard using Power BI.

The dashboard helps management monitor financial performance by comparing
budgeted amounts with actual spending across departments, regions,
categories, and payment methods.

The dashboard provides an interactive view of budget utilization,
spending patterns, and budget variance to support financial
decision-making and budget control.

2. PROBLEM STATEMENT

---

Senior management of a manufacturing company needs clear visibility
into financial performance and spending against approved budgets.

Manually analyzing thousands of financial transactions makes it
difficult to identify overspending, budget gaps, and spending trends.

The objective of this project is to develop an interactive Finance KPI
Dashboard in Power BI that tracks Total Budget, Total Actual Spending,
Budget Variance, Budget Utilization %, and Transactions.

3. DATASET

---

Dataset Name:
Budget vs Actual Financial Dataset

Source:
Kaggle

Dataset Link:
https://www.kaggle.com/datasets/kennathalexanderroy/budget-vs-actual-financial-dataset

The dataset contains transaction-level financial information including:

* Date
* Department
* Category
* Region
* Budget Amount
* Actual Amount
* Payment Method
* Transaction ID

Only the specified Kaggle dataset is used for this project.

4. TOOLS USED

---

* Power BI Desktop
* Microsoft Excel
* DAX
* Power Query
* GitHub

5. DATA PREPARATION

---

The dataset was imported into Power BI from Excel.

The following data preparation activities were performed:

* Verified data types
* Checked Date fields
* Checked numeric Budget and Actual Amount fields
* Checked text fields
* Created Year column
* Created Month column
* Created Month Number column
* Sorted Month using Month Number
* Created Variance column
* Created Variance % column
* Created Budget Utilization % column

6. CALCULATED COLUMNS

---

Variance:

Budget Amount - Actual Amount

Variance %:

(Budget Amount - Actual Amount) / Budget Amount

Budget Utilization %:

Actual Amount / Budget Amount

Year:

Extracted from Date

Month:

Extracted from Date

Month Number:

Extracted from Date for correct chronological sorting

7. DAX MEASURES

---

Total Budget:

SUM of Budget Amount

Total Actual:

SUM of Actual Amount

Total Variance:

Total Budget - Total Actual

Budget Utilization:

Total Actual / Total Budget

Transaction Count:

Distinct count of Transaction ID

8. DASHBOARD PAGES

---

PAGE 1 - FINANCIAL OVERVIEW

The Financial Overview page provides a high-level view of financial
performance.

KPIs included:

* Total Budget
* Total Actual
* Total Variance
* Budget Utilization %
* Transaction Count

Visualizations included:

* Monthly Budget vs Actual
* Actual Spending by Department
* Actual Spending by Category

Interactive filters:

* Date
* Department
* Category
* Region

PAGE 2 - BUDGET & EXPENSE ANALYSIS

The Budget & Expense Analysis page provides detailed analysis of
budget utilization and spending variance.

KPIs included:

* Total Budget
* Total Actual
* Total Variance
* Budget Utilization %

Visualizations included:

* Budget vs Actual by Department
* Budget Variance by Category
* Actual Spending by Region
* Detailed Financial Analysis Matrix

Interactive filters:

* Department
* Region
* Category
* Payment Method

9. DASHBOARD COLORS

---

The dashboard uses a professional finance-oriented color theme.

Background:
#F4F7FB

Header:
#0B1F3A

Budget:
#42A5F5

Actual:
#1565C0

Positive Variance:
#2E7D32

Negative Variance:
#C62828

Teal:
#00897B

Card Background:
#FFFFFF

Text:
#263238

10. INTERACTIVITY

---

The dashboard includes interactive slicers that allow users to filter
financial information dynamically.

Navigation buttons are provided to move between dashboard pages.

A Back/Home button is included for easier navigation.

The charts and KPI cards respond to the selected filters.

11. KEY FEATURES

---

* Interactive Finance KPI Dashboard
* KPI cards
* Budget vs Actual analysis
* Budget variance analysis
* Budget utilization analysis
* Department-wise spending analysis
* Category-wise spending analysis
* Region-wise spending analysis
* Monthly financial trend analysis
* Interactive slicers
* Page navigation
* Professional color theme
* Detailed financial matrix

12. GITHUB WORKFLOW

---

The project follows the GitHub workflow discussed in class.

Steps followed:

1. Created a GitHub repository.

2. Added the project dataset.

3. Created the Power BI dashboard.

4. Saved the Power BI .pbix file.

5. Added dashboard screenshots.

6. Created project documentation.

7. Added README file.

8. Committed project files.

9. Pushed the files to GitHub.

10. Submitted the GitHub repository link.

11. PROJECT STRUCTURE

---

finance-kpi-dashboard/

```
README.txt

data/
    project_7_DAB.xlsx

dashboard/
    Finance_KPI_Dashboard.pbix

screenshots/
    page1_financial_overview.png
    page2_budget_expense_analysis.png

documentation/
    Assignment_7_Report.pdf
```

## 14. EXPECTED OUTCOME

The dashboard provides management with a clear and interactive view
of financial performance.

It helps users identify:

* Budget overspending
* Budget remaining
* High-spending departments
* High-spending categories
* Regional spending patterns
* Monthly spending trends
* Budget utilization levels

The dashboard supports faster financial analysis and improves
visibility into budget control.

15. CONCLUSION

---

The Finance KPI Dashboard provides an interactive and visually
structured approach to analyzing budget and actual spending.

Power BI is used to transform transaction-level financial data into
meaningful KPIs and visualizations.

The dashboard enables management to monitor budget performance,
identify variance, analyze spending patterns, and make
data-driven financial decisions.

