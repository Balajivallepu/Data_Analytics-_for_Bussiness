# 📊 Marketing Campaign Performance Dashboard

## 📌 Project Overview

The **Marketing Campaign Performance Dashboard** is an interactive business intelligence project developed using **Microsoft Power BI**.

The project analyzes marketing campaign data across different campaign types, marketing channels, customer segments, target audiences, and locations. The dashboard helps management evaluate campaign effectiveness using important KPIs such as **Impressions, Clicks, Conversion Rate, Acquisition Cost, Engagement Score, and ROI**.

The dashboard consists of **two interactive pages**:

* **Page 1 – Executive Campaign Overview**
* **Page 2 – Campaign & ROI Analysis**

---

## 🎯 Problem Statement

A digital marketing agency has executed multiple campaigns across different channels and customer segments. Management needs a centralized reporting system to evaluate campaign performance and identify the most effective campaigns.

The objective is to develop an interactive Power BI dashboard that provides meaningful insights into:

* Campaign performance
* Marketing channel effectiveness
* Customer conversion
* Campaign ROI
* Acquisition cost
* Customer engagement
* Geographic performance
* Monthly campaign trends

---

## 📂 Dataset

**Dataset:** `marketing_campaign_dataset(1).csv`

The dataset contains **200,000 records and 16 columns**.

### Dataset Columns

| Column           | Description                          |
| ---------------- | ------------------------------------ |
| Campaign_ID      | Unique campaign identifier           |
| Company          | Company associated with the campaign |
| Campaign_Type    | Type of marketing campaign           |
| Target_Audience  | Target customer group                |
| Duration         | Campaign duration                    |
| Channel_Used     | Marketing channel                    |
| Conversion_Rate  | Campaign conversion rate             |
| Acquisition_Cost | Customer acquisition cost            |
| ROI              | Return on Investment                 |
| Location         | Campaign location                    |
| Language         | Target language                      |
| Clicks           | Number of clicks                     |
| Impressions      | Number of impressions                |
| Engagement_Score | Customer engagement score            |
| Customer_Segment | Customer classification              |
| Date             | Campaign date                        |

---

## 🛠️ Tools & Technologies

* **Microsoft Power BI Desktop**
* **Power Query**
* **DAX**
* **CSV Dataset**
* **GitHub**

---

# 🔄 Project Workflow

```text
Raw Marketing Dataset
        ↓
Data Import
        ↓
Power Query
        ↓
Data Cleaning
        ↓
Data Transformation
        ↓
Data Modeling
        ↓
DAX Measures
        ↓
Dashboard Development
        ↓
Interactive Analysis
        ↓
Business Insights
```

---

# 🧹 Data Preparation

The following data preparation activities were performed using Power Query:

* Removed duplicate records where required
* Checked missing values
* Corrected data types
* Converted Date into Date format
* Converted Acquisition Cost into numerical format
* Removed `$` and comma symbols from Acquisition Cost
* Verified Clicks and Impressions as numeric fields
* Verified Conversion Rate and ROI
* Standardized column names
* Created a Date table for time-based analysis

---

# 📅 Date Table

A separate Date table was created using DAX.

```DAX
DateTable =
ADDCOLUMNS(
    CALENDAR(
        MIN('Marketing Campaign'[Date]),
        MAX('Marketing Campaign'[Date])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Month Year", FORMAT([Date], "MMM YYYY"),
    "Quarter", "Q" & FORMAT([Date], "Q")
)
```

The Date table was connected with the Marketing Campaign table using the Date field.

---

# 📐 DAX Measures

## Total Campaigns

```DAX
Total Campaigns =
DISTINCTCOUNT('Marketing Campaign'[Campaign_ID])
```

## Total Impressions

```DAX
Total Impressions =
SUM('Marketing Campaign'[Impressions])
```

## Total Clicks

```DAX
Total Clicks =
SUM('Marketing Campaign'[Clicks])
```

## Estimated Conversions

The dataset does not contain a direct conversion-count field. Therefore, estimated conversions were calculated using Clicks and Conversion Rate.

```DAX
Estimated Conversions =
SUMX(
    'Marketing Campaign',
    'Marketing Campaign'[Clicks] *
    'Marketing Campaign'[Conversion_Rate]
)
```

## Average ROI

```DAX
Average ROI =
AVERAGE('Marketing Campaign'[ROI])
```

## Average Conversion Rate

```DAX
Average Conversion Rate =
AVERAGE('Marketing Campaign'[Conversion_Rate])
```

## CTR

```DAX
CTR =
DIVIDE(
    [Total Clicks],
    [Total Impressions],
    0
)
```

## Total Acquisition Cost

```DAX
Total Acquisition Cost =
SUM('Marketing Campaign'[Acquisition_Cost])
```

## Cost Per Click

```DAX
Cost Per Click =
DIVIDE(
    [Total Acquisition Cost],
    [Total Clicks],
    0
)
```

## Cost Per Conversion

```DAX
Cost Per Conversion =
DIVIDE(
    [Total Acquisition Cost],
    [Estimated Conversions],
    0
)
```

---

# 🎨 Dashboard Color Theme

The dashboard uses a modern digital marketing color theme.

| Element              | HEX Code  |
| -------------------- | --------- |
| Header / Dark Navy   | `#172554` |
| Primary Blue         | `#2563EB` |
| Impressions / Cyan   | `#0891B2` |
| Clicks / Orange      | `#F97316` |
| Conversions / Purple | `#7C3AED` |
| ROI / Green          | `#16A34A` |
| Negative / Red       | `#DC2626` |
| Background           | `#F8FAFC` |
| Cards                | `#FFFFFF` |
| Text                 | `#1E293B` |
| Border               | `#E2E8F0` |

---

# 📊 Dashboard Pages

## 🟦 Page 1 – Executive Campaign Overview

The first page provides a high-level summary of marketing campaign performance.

### KPI Cards

* Total Campaigns
* Total Impressions
* Total Clicks
* Estimated Conversions
* Average ROI

### Visualizations

* Monthly Campaign Performance
* ROI by Campaign Type
* ROI by Marketing Channel
* Campaign Distribution by Target Audience
* Conversion Rate by Customer Segment

### Filters

* Year
* Campaign Type
* Channel
* Location
* Customer Segment

### Purpose

This page allows management to quickly understand overall campaign performance and identify major trends.

---

# 🟣 Page 2 – Campaign & ROI Analysis

The second page provides detailed campaign analysis.

### KPI Cards

* CTR
* Conversion Rate
* Cost Per Click
* Cost Per Conversion

### Visualizations

* ROI vs Acquisition Cost
* Channel Effectiveness
* Conversion Rate by Campaign Type
* Geographic Campaign Performance
* Engagement Score vs Conversion Rate
* Detailed Campaign Performance Table
* Top 10 Campaigns by ROI

### Purpose

This page helps management evaluate campaign efficiency, investment, engagement, conversion, and profitability.

---

# 🎛️ Interactive Features

The dashboard includes several interactive features:

### Slicers

Users can filter the dashboard by:

* Year
* Campaign Type
* Channel
* Location
* Customer Segment

### Cross Filtering

Selecting a chart element automatically filters other visuals on the page.

### Page Navigation

Users can navigate between the two dashboard pages using the Page Navigator.

### Reset Filters

A bookmark-based Reset Filters button allows users to return to the default dashboard view.

### Tooltips

Hovering over visual elements provides additional campaign information.

### Conditional Formatting

ROI and Conversion Rate are highlighted using different colors to identify high- and low-performing campaigns.

---

# 📈 Key Business Questions

The dashboard answers important marketing questions such as:

1. Which campaign type provides the highest ROI?
2. Which marketing channel performs best?
3. Which campaigns generate the most clicks?
4. Which campaigns achieve better conversion rates?
5. Which customer segment has the highest conversion rate?
6. Which locations generate better campaign results?
7. Which campaigns have high acquisition costs?
8. Which campaigns provide high ROI at lower cost?
9. Does higher engagement lead to higher conversion?
10. What are the monthly campaign performance trends?

---

# 💡 Business Insights

The dashboard can be used to identify:

* High-performing marketing channels
* High-ROI campaigns
* Low-performing campaigns
* Cost-efficient campaigns
* Customer segments with stronger conversion
* Geographic opportunities
* Campaign types with better engagement
* Monthly performance trends

These insights can support better allocation of marketing budgets and improve future campaign planning.

---

# 📁 Project Structure

```text
Marketing-Campaign-Performance-Dashboard/
│
├── README.md
│
├── Dataset/
│   └── marketing_campaign_dataset(1).csv
│
├── PowerBI/
│   └── Marketing_Campaign_Performance.pbix
│
├── Report/
│   └── Marketing_Campaign_Performance_Report.pdf
│
└── Screenshots/
    ├── Dashboard_Page_1.png
    └── Dashboard_Page_2.png
```

---

# 🚀 How to Use the Project

### Step 1

Download or clone this repository.

### Step 2

Open the Power BI file:

```text
Marketing_Campaign_Performance.pbix
```

### Step 3

If required, update the dataset path in Power BI.

### Step 4

Click:

**Home → Refresh**

### Step 5

Use the slicers and charts to explore campaign performance.

---

# 📌 Project Objectives

The main objectives of this project are:

* To analyze marketing campaign performance.
* To measure campaign ROI.
* To evaluate marketing channels.
* To analyze customer conversion.
* To monitor acquisition costs.
* To identify high-performing campaigns.
* To create an interactive business intelligence dashboard.
* To support data-driven marketing decisions.

---

# 🎓 Learning Outcomes

Through this project, I learned:

* Importing CSV data into Power BI
* Data cleaning using Power Query
* Data transformation
* Data modeling
* Creating Date tables
* Creating DAX measures
* Calculating marketing KPIs
* Designing interactive dashboards
* Using slicers and filters
* Creating charts and KPI cards
* Applying conditional formatting
* Creating bookmarks
* Implementing page navigation
* Analyzing marketing performance
* Generating business insights from raw data

---

# 🏁 Conclusion

The **Marketing Campaign Performance Dashboard** successfully transforms raw marketing campaign data into an interactive and visually appealing business intelligence solution.

The dashboard provides management with a centralized view of campaign performance, including impressions, clicks, conversions, ROI, acquisition costs, engagement, customer segments, channels, and locations.

The two-page dashboard enables both **high-level executive monitoring** and **detailed campaign analysis**. Interactive filters, navigation, tooltips, and conditional formatting make the dashboard easy to use and suitable for marketing decision-making.

This project demonstrates the practical application of **Power BI, Power Query, and DAX** for marketing analytics and data-driven business intelligence.

---

# 👨‍💻 Project Information

**Project Title:** Marketing Campaign Performance Dashboard

**Domain:** Marketing Analytics / Business Intelligence

**Tool:** Microsoft Power BI

**Dataset:** Marketing Campaign Dataset

**Dashboard Pages:** 2

**Data Source:** CSV

**Key KPIs:** Impressions, Clicks, Conversions, CTR, ROI, Acquisition Cost, CPC

---

## ⭐ Final Result

**Page 1:** Executive Campaign Overview
**Page 2:** Campaign & ROI Analysis

The project provides an interactive and professional dashboard for evaluating digital marketing campaign performance and supporting data-driven decisions.
