# Data Science Salary Dashboard

![Data_Science_Salary_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/5c8396ca-19a8-4ea0-9d34-5c7a7192c380)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

### Dashboard File
My final dashboard is in [Data_Science_Salary_Dashboard.xlsx](https://github.com/user-attachments/files/26281659/Data_Science_Salary_Dashboard.xlsx)

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img width="1336" height="867" alt="Data_Science_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/0201b132-7edb-4136-9c29-6ea464c9954b" />

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![Data_Science_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/72a65b39-cedf-40a7-848b-433b6235a51a)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

<img width="265" height="220" alt="Data_Science_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/caf976d8-8ccc-4459-bb46-497d79393e1f" />

📉 Dashboard Implementation

<img width="1148" height="1214" alt="Data_Science_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/407bb364-7ff9-4b08-970b-ea947a1a1c06" />

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

<img width="195" height="119" alt="Data_Science_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/86b66c07-4027-47a5-bb92-8f3f167572bf" />


📉 Dashboard Implementation:

<img width="942" height="1212" alt="Data_Science_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/b294e70d-56a4-421f-828a-38180ced08cb" />

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

![Data_Science_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/47bd1e69-ebd6-487b-922d-533624b906ce)
