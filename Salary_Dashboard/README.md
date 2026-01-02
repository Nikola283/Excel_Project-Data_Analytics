# Excel Salary Dashboard

![1_Salary_Dashboard.png](/Images/1_Salary_Dashboard_Final_Dashboard.gif)

This project presents an interactive Excel dashboard designed to analyze and benchmark salaries for data-related roles using real-world job posting data from 2023. The dashboard enables fast, data-driven insights into compensation trends across job titles, countries, and employment types.

It is built for decision-makers, not just analysts — such as HR teams, recruiters, and consultants who need reliable salary benchmarks.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Tools & Techniques

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Solution

I developed an Excel-based salary dashboard that:

- Automatically calculates median salaries based on multiple criteria

- Allows users to filter results by job title, country, and job schedule type

- Visualizes salary trends clearly using charts and maps

- The result is a clean, interactive dashboard that supports faster and more informed compensation decisions.

## Technical Implementation (Optional)
The following section highlights selected technical details for those interested in the implementation.

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

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

🍽️ Background Table

![1_Salary_Dashboard_Screenshot1.png](/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

## Key Insights

- Senior and Engineering roles consistently show higher median salaries, often significantly outperforming Analyst roles across most regions.

- Salary differences between countries are substantial, indicating opportunities for:

- Remote hiring

- Location-based compensation strategies

- Full-time roles tend to offer more stable and predictable salary ranges, which is valuable for long-term workforce planning.

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

<img src="/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion
- This Excel dashboard demonstrates how salary data can be transformed into actionable insights for compensation benchmarking and workforce planning.
- By combining interactive filters, automated calculations, and clear visualizations, the dashboard supports faster and more confident decision-making for HR, recruitment, and consulting teams.
- This dashboard reduces manual salary analysis and provides instant access to structured insights, saving time and improving decision quality.
