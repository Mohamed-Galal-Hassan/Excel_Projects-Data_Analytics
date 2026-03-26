# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This interactive Excel dashboard was developed to systematically analyze contemporary salary distributions across data science roles. Constructed as a foundational portfolio project to demonstrate practical data analytics capabilities, this tool enables users to investigate compensation metrics based on job title, geographic location, and employment type to ensure alignment with current market valuations.

The underlying dataset was sourced from a comprehensive Excel data analytics curriculum I completed. It provides a structured foundation of real-world job market data, containing detailed records on job classifications, compensation rates, geographic coordinates, and required technical proficiencies.

### Dashboard File
The finalized interactive dashboard is accessible here: [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Technical Competencies Demonstrated

The execution of this analysis required the application of the following Excel functionalities:

- **📉 Charts** (Advanced Visualization)
- **🧮 Formulas and Functions** (Complex Array and Logical Processing)
- **❎ Data Validation** (Dynamic Input Control)

### Source Dataset

The dataset utilized for this project aggregates real-world data science job postings from 2023. It serves as the quantitative basis for the analysis, providing specific data points on:

- **👨‍💼 Standardized Job titles**
- **💰 Annualized and Hourly Salaries**
- **📍 Geographic Locations**
- **🛠️ Technical Skill Requirements**

## Dashboard Architecture

### 📉 Charts

#### 📊 Data Science Job Salaries - Horizontal Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Implementation:** Configured a horizontal bar chart referencing aggregated median salary values, with optimized layout and formatting.
- 🎨 **Design Architecture:** Horizontal orientation selected to facilitate the objective visual comparison of compensation figures across distinct text labels.
- 📉 **Data Structuring:** Job titles are sorted in descending order of median salary to optimize scannability.
- 💡 **Analytical Insight:** Provides immediate identification of compensation hierarchies, clearly quantifying the salary premium for Senior and Engineering roles compared to standard Analyst positions.

#### 🗺️ Global Median Salaries - Geospatial Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Implementation:** Deployed Excel's native map chart functionality to project median salaries onto a global coordinate system.
- 🎨 **Design Architecture:** Utilized a sequential color gradient to represent the magnitude of median salaries across different national markets.
- 📊 **Data Processing:** Aggregated and plotted the median salary strictly for countries with statistically significant data volumes.
- 👁️ **Visual Enhancement:** Visualizes macro-level geographic compensation disparities.
- 💡 **Analytical Insight:** Instantly highlights high-yield versus low-yield labor markets globally.

### 🧮 Computational Logic

#### 💰 Dynamic Median Salary Calculation

```excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
