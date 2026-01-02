## Introduction

This project analyzes the data science job market using real-world job posting data from 2023 to identify high-value skills, salary benchmarks, and regional pay differences.

The analysis is designed to support data-driven decisions for HR teams, recruiters, and workforce planners by highlighting which skills and roles command higher compensation.

### Business Questions

The analysis focuses on the following business questions:

1. **How does the number of required skills impact salary levels?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023.

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

### 1️⃣ Do more skills get you better pay?

## Data Preparation
- Job posting and skill data were cleaned, transformed, and modeled using Power Query.
- The dataset was structured into separate job and skill tables and optimized for analysis using Power Pivot relationships, enabling accurate salary and skill-level insights.

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/Images/2_Project_Analysis_Chart1.png)

#### 🤔 So What

- This insight helps organizations justify higher compensation for specialized roles and supports skill-based workforce planning and upskilling strategies.

## 2️⃣ What’s the salary for data jobs in different regions?

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/Images/2_Project_Analysis_Chart2.png)

#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, supporting compensation benchmarking and geographically informed hiring decisions while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![2_Project_Analysis_Screenshot5.png](/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![2_Project_Analysis_Screenshot6.png](/Images/2_Project_Analysis_Screenshot6.png)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/Images/2_Project_Analysis_Chart3.png)

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/Images/2_Project_Analysis_Chart4.png)

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, particularly for organizations prioritizing high-impact technical skills in hiring and training programs

## Business Use Cases

- Salary benchmarking for data roles

- Identifying high-value skills for hiring and training

- Supporting location-based compensation strategies

- Workforce planning and upskilling decisions

## Conclusion

This Excel-based analysis demonstrates how job market and skill data can be transformed into actionable insights for salary benchmarking and workforce planning.

By combining Power Query, Power Pivot, DAX, and advanced visualizations, the project highlights which roles and skills deliver the highest market value, supporting more informed hiring, compensation, and upskilling decisions.
