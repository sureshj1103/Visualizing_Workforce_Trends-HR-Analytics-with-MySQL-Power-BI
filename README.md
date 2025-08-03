# Visualizing_Workforce_Trends-HR-Analytics-with-MySQL-Power-BI
An end-to-end HR analytics project using MySQL for data processing and Power BI for dashboard visualization to provide actionable workforce insights.

📊 Project Title: HR Analytics Dashboard Using MySQL & Power BI
## 🚀 Brief One-Line Summary
An end-to-end HR analytics project using MySQL for data processing and Power BI for dashboard visualization to provide actionable workforce insights.

## 📘 Overview
In this project, we analyze employee data to uncover insights about attrition, job satisfaction, performance, and other HR metrics. The goal is to help HR professionals make data-driven decisions about retention and workforce management.

## ❓ Problem Statement
Companies often struggle with high employee turnover and low satisfaction levels. By leveraging data analytics, we aim to identify patterns and root causes behind attrition and provide solutions through actionable insights.

## 📦 Dataset
File Name: HR_Analytics.csv
Records: 1470 rows
Features: Age, Department, JobRole, MonthlyIncome, Education, EnvironmentSatisfaction, JobSatisfaction, PerformanceRating, Attrition, etc.

## 🧰 Tools and Technologies
Database: MySQL

Data Processing: SQL Queries

Visualization: Power BI

Language: SQL

Version Control: Git & GitHub

## 🧠 Methods
Data Import & Cleaning:

Imported CSV data into MySQL.

Handled missing/null values and converted datatypes.

Exploratory Data Analysis (EDA):

Analyzed attrition rates, department-wise headcount, and satisfaction levels.

SQL Queries:

Used GROUP BY, JOIN, and CASE statements to extract insights.

Created derived columns like Attrition Rate by Department.

Power BI Dashboard:

Connected to MySQL.

Created interactive visuals (bar charts, pie charts, KPIs, slicers).

## 🔍 Key Insights
High Attrition: In specific job roles like Sales Executive.

Job Satisfaction Correlation: Employees with low satisfaction tend to leave more.

Income & Performance: No direct correlation between salary and attrition found.

Departments: R&D has the highest number of employees but lowest attrition.

## 📈 Dashboard/Model/Output
A multi-page Power BI dashboard featuring:

KPIs: Total Employees, Attrition %, Avg Satisfaction.

Charts: Attrition by Role, Department Satisfaction, Age Distribution.

Filters: Gender, Education, Department, Job Role.

## 📎 Power BI file: HR.pbix included

🛠️ How to Run This Project?
Step 1: Load Data to MySQL
sql
Copy
Edit
-- Create Table
CREATE TABLE hr_analytics (
    Age INT,
    Attrition VARCHAR(10),
    BusinessTravel VARCHAR(50),
    Department VARCHAR(50),
    DistanceFromHome INT,
    Education INT,
    EducationField VARCHAR(50),
    EnvironmentSatisfaction INT,
    Gender VARCHAR(10),
    JobRole VARCHAR(50),
    JobSatisfaction INT,
    MaritalStatus VARCHAR(20),
    MonthlyIncome INT,
    NumCompaniesWorked INT,
    OverTime VARCHAR(10),
    PercentSalaryHike INT,
    PerformanceRating INT,
    TotalWorkingYears INT,
    TrainingTimesLastYear INT,
    YearsAtCompany INT
);

-- Load CSV into the table (use MySQL Workbench or LOAD DATA INFILE)
Step 2: Run SQL Queries for Analysis
sql
Copy
Edit
-- Attrition count by Department
SELECT Department, COUNT(*) AS total,
    SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) AS attritions,
    ROUND(SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS attrition_rate
FROM hr_analytics
GROUP BY Department;

-- Job Satisfaction by Role
SELECT JobRole, AVG(JobSatisfaction) AS avg_satisfaction
FROM hr_analytics
GROUP BY JobRole;
Step 3: Connect Power BI to MySQL
Go to Home > Get Data > MySQL Database

Enter credentials and select hr_analytics table.

Build visuals using your queries or import the full table.
<img width="870" height="624" alt="image" src="https://github.com/user-attachments/assets/46bf44ef-1ced-4425-a1e2-ab1463ece61a" />


## 🧾 Results & Conclusion
The dashboard helped identify departments with high attrition and roles with poor satisfaction. These findings allow HR to prioritize policy changes and targeted interventions to improve retention.
# Attrition Proportion by Marital Status:
Divorced: The attrition proportion is approximately 0.10.
Married: The attrition proportion is approximately 0.12.
Single: The attrition proportion is approximately 0.25.
Visualization of Attrition Rate: The bar chart illustrates that single employees have the highest attrition rate, followed by married and then divorced employees.

<img width="1330" height="750" alt="image" src="https://github.com/user-attachments/assets/c49c58ac-8ce9-40e8-b43b-834ae87cdd5b" />

## 🔭 Future Work
Predictive modeling using Python (logistic regression or random forest).
Integration with real-time HR systems (e.g., SAP or Workday).
Monthly automated reporting via Power BI Service.
