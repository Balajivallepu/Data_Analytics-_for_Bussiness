# Experiment No. 9 – Exploratory Data Analysis on Business Datasets

## 📌 Project Title

**Student Learning Analytics Dashboard using Power BI**

---

## 📖 Problem Statement

A large student learning dataset is analyzed to understand key trends, patterns, and relationships in student learning behavior and academic performance.

The project uses **Microsoft Power BI** to perform Exploratory Data Analysis (EDA) and develop an interactive dashboard. The dashboard helps analyze study habits, attendance, coding practice, assignment completion, learning platforms, AI tool usage, mock tests, and performance scores.

---

## 🎯 Objectives

The main objectives of this experiment are:

1. Understand the structure of the student learning dataset.
2. Analyze student learning behavior.
3. Calculate important performance indicators.
4. Examine relationships between learning activities and performance.
5. Compare student performance across academic years.
6. Analyze the usage of different learning platforms.
7. Identify different student performance segments.
8. Create meaningful data visualizations.
9. Develop an interactive Power BI dashboard.
10. Generate useful insights from the dataset.

---

## 🛠️ Tools and Technologies

* **Microsoft Power BI Desktop**
* **Power Query**
* **DAX**
* **CSV Dataset**
* **Data Visualization**
* **Exploratory Data Analysis (EDA)**

---

## 📊 Dataset

The project uses a **synthetic dataset containing 500 student records**.

### Dataset Attributes

| Column                        | Data Type      |
| ----------------------------- | -------------- |
| Student_ID                    | Text           |
| Year                          | Text           |
| Semester                      | Whole Number   |
| Study_Hours_Per_Day           | Decimal Number |
| Learning_Platform             | Text           |
| AI_Tool_Used                  | Text           |
| Coding_Hours_Per_Week         | Decimal Number |
| Attendance_Percent            | Decimal Number |
| Assignment_Completion_Percent | Decimal Number |
| YouTube_Hours_Per_Week        | Decimal Number |
| Group_Study                   | Text           |
| Mock_Tests_Per_Month          | Whole Number   |
| Performance_Score             | Decimal Number |
| Student_Segment               | Text           |

---

## 🔄 Methodology

The following steps were followed:

1. Dataset Import
2. Data Cleaning and Transformation
3. Data Type Validation
4. DAX Measure Creation
5. KPI Creation
6. Dashboard Development
7. Interactive Filtering
8. Data Visualization
9. Insight Generation

---

## 📥 Step 1: Dataset Import

The student dataset was imported into Power BI Desktop using the **Text/CSV** connector.

### Procedure

1. Open Power BI Desktop.
2. Select **Get Data**.
3. Select **Text/CSV**.
4. Choose the student dataset.
5. Preview the data.
6. Click **Load**.

---

## 🧹 Step 2: Data Cleaning

The dataset was checked and prepared for analysis.

The following were validated:

* Column names
* Missing values
* Duplicate records
* Data types
* Numerical fields
* Categorical fields
* Performance values

Power Query was used for data preparation and transformation where required.

---

## 🔢 Step 3: DAX Measures

The following DAX measures were created.

### Total Students

```DAX
Total Students =
DISTINCTCOUNT(Student_Data[Student_ID])
```

### Average Performance

```DAX
Average Performance =
AVERAGE(Student_Data[Performance_Score])
```

### Average Attendance

```DAX
Average Attendance =
AVERAGE(Student_Data[Attendance_Percent])
```

### Average Study Hours

```DAX
Average Study Hours =
AVERAGE(Student_Data[Study_Hours_Per_Day])
```

### Average Coding Hours

```DAX
Average Coding Hours =
AVERAGE(Student_Data[Coding_Hours_Per_Week])
```

---

## 📌 Step 4: KPI Cards

Five KPI cards were created:

* **Total Students**
* **Average Performance**
* **Average Attendance**
* **Average Study Hours**
* **Average Coding Hours**

These KPIs provide a quick summary of the overall student learning and performance data.

---

## 📊 Step 5: Dashboard Visualizations

The dashboard contains six major charts.

### 1. Average Performance by Year

**Chart:** Clustered Column Chart

* Axis: `Year`
* Value: `Average Performance`

This chart compares student performance across different academic years.

---

### 2. Study Hours vs Performance

**Chart:** Scatter Chart

* X-axis: `Study_Hours_Per_Day`
* Y-axis: `Performance_Score`
* Details: `Student_ID`
* Legend: `Student_Segment`

This visualization helps identify the relationship between study time and performance.

---

### 3. Attendance vs Performance

**Chart:** Scatter Chart

* X-axis: `Attendance_Percent`
* Y-axis: `Performance_Score`
* Details: `Student_ID`

This chart helps analyze whether attendance is associated with student performance.

---

### 4. Student Performance Segments

**Chart:** Donut Chart

* Legend: `Student_Segment`
* Values: `Total Students`

Students are categorized into:

* High Performer
* Average Performer
* Needs Improvement

---

### 5. Students by Learning Platform

**Chart:** Bar Chart

* Axis: `Learning_Platform`
* Value: `Total Students`

This visualization identifies the most commonly used learning platforms.

---

### 6. Coding Practice and Performance by Year

**Chart:** Combo Chart

* Axis: `Year`
* Column: `Average Coding Hours`
* Line: `Average Performance`

This chart compares coding practice with student performance across academic years.

---

## 🎛️ Interactive Filters

The following slicers were added to make the dashboard interactive:

* **Year**
* **Semester**
* **Learning Platform**
* **Student Segment**

Users can select different values to analyze specific groups of students.

---

## 🎨 Dashboard Design

A professional dark-themed layout was used.

### Design Features

* Dark background
* Professional dashboard header
* KPI cards
* Blue and teal accents
* Clear chart titles
* Interactive slicers
* Consistent visual layout
* One-page dashboard

---

## ❓ Business Questions Answered

The dashboard helps answer the following questions:

1. How many students are included in the dataset?
2. What is the average student performance?
3. What is the average attendance?
4. How many hours do students study?
5. Which year has better performance?
6. Is study time related to performance?
7. Is attendance related to performance?
8. Which learning platform is most popular?
9. What percentage of students are high performers?
10. How does coding practice vary across years?

---

## 💡 Key Insights

The dashboard can be used to identify:

* Differences in student performance between academic years.
* The relationship between study hours and performance.
* The relationship between attendance and performance.
* The most commonly used learning platforms.
* The distribution of high, average, and low-performing students.
* Differences in coding practice across academic years.
* Learning behavior patterns among different student segments.

> **Note:** Specific numerical insights should be reported from the final Power BI dashboard after the dataset has been analyzed.

---

## 📁 Project Structure

```text
Experiment-9-EDA/
│
├── README.md
│
├── Dataset/
│   └── Student_Data.csv
│
├── PowerBI/
│   └── Student_Learning_Analytics.pbix
│
└── Screenshots/
    └── Dashboard.png
```

---

## ▶️ How to Run the Project

### Step 1

Install **Microsoft Power BI Desktop**.

### Step 2

Download or open the project files.

### Step 3

Open:

```text
Student_Learning_Analytics.pbix
```

### Step 4

If required, update the dataset source location.

### Step 5

Refresh the data using:

**Home → Refresh**

### Step 6

Use the slicers to interact with the dashboard.

---

## 📈 Expected Output

The final output is a **one-page interactive Student Learning Analytics Dashboard** containing:

* 5 KPI cards
* 4 interactive slicers
* 6 analytical charts
* Student performance analysis
* Learning behavior analysis
* Academic year comparison
* Performance segmentation

---

## 🏁 Conclusion

The **Student Learning Analytics Dashboard** demonstrates how Power BI can be used to perform Exploratory Data Analysis on a student dataset.

The dataset was imported, cleaned, transformed, and analyzed using DAX measures and visualizations. KPI cards provide an overview of important statistics, while charts analyze performance, study hours, attendance, learning platforms, student segments, and coding practice.

Interactive slicers allow users to explore different student groups and identify useful patterns. The final dashboard provides a simple and professional approach to understanding student learning behavior and academic performance.

---

## 🎓 Learning Outcomes

After completing this experiment, the following skills were developed:

* Power BI data import
* Data cleaning and transformation
* Data type validation
* DAX measure creation
* KPI creation
* Exploratory Data Analysis
* Data visualization
* Student performance analysis
* Interactive slicers
* Dashboard design
* Insight generation
* Data-driven decision-making

---

## 👨‍💻 Project Information

**Experiment:** 9
**Topic:** Exploratory Data Analysis on Business Datasets
**Domain:** Data Analytics / Education Analytics
**Tool:** Microsoft Power BI
**Dataset Size:** 500 Student Records
**Dashboard Type:** Interactive One-Page Dashboard
