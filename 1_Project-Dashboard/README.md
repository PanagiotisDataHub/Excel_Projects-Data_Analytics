# 📊 Excel Salary Dashboard  
![Presentation1-github](https://github.com/user-attachments/assets/322a9c73-8513-4638-9dde-df7f1185a194)

## Introduction  
This salary dashboard was created to help job seekers and professionals analyze salaries for their desired roles and ensure they are fairly compensated.  

The dataset comes from the **Excel for Data Analytics** course by [Luke Barousse](https://github.com/lukebarousse) and [Kelly Adams](https://github.com/kellyjadams). It includes real-world job postings from 2023, providing insights into job titles, salaries, locations, and required skills.  

---

## Data Jobs Dataset  
The dataset used for this project contains **real-world data science job postings from 2023**. It is sourced from the **Excel for Data Analytics course**, which provides a foundation in data analysis using Excel.  

This dataset includes detailed information on:  
- **Job titles** – Common roles in the data industry  
- **Salaries** – Median salary figures based on job type and location  
- **Locations** – Country-based salary variations  
- **Skills** – Most in-demand technical and analytical skills  

---

## Dashboard File  
- **Final Dashboard**: [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx)  
- **Online Version** (without map chart): [Online Dashboard](#)  

---

## Excel Skills Used  
- **Charts** – Data visualization using bar and map charts  
- **Formulas & Functions** – Salary calculations and filtering  
- **Data Validation** – Interactive dropdowns for filtering job details  

---

## Dashboard Build  

### Salary by Job Titles & Schedule Types  
- **Bar Chart** – Visualizes median yearly salaries by job title and schedule type.  
- **Sorted in descending order** for better readability.  
- **Insight**: Senior roles and engineers tend to have higher salaries than analyst roles.  

![1_Salary_Dashboard_Chart1](https://github.com/user-attachments/assets/e2795cc0-9e20-46d9-8d46-c003d09a4df7)

### Country Median Salaries  
- **Map Chart** – Color-coded global salary distribution for data jobs.  
- **Plots median salaries by country** for easy comparison.  
- **Insight**: Highlights high- and low-paying regions.  

![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/2212e326-fed4-47de-b922-6a0d98872e75)

---

## Key Formulas Used  

### Median Salary by Job Titles  
```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2) *
    (jobs[job_country]=country) *
    (ISNUMBER(SEARCH(type, jobs[job_schedule_type]))) * 
    (jobs[salary_year_avg]<>0), 
    jobs[salary_year_avg]
  )
)
```
- 🔍 **Multi-Criteria Filtering** – Filters job title, country, and schedule type while excluding blank salaries.  
- 📊 **Array Formula** – Uses `MEDIAN()` with a nested `IF()` statement to analyze salary data dynamically.  
- 🎯 **Tailored Insights** – Provides salary breakdowns by job title, region, and schedule type.  
- 🔢 **Formula Purpose** – Populates the table below, returning the median salary based on job title, country, and job type.  

## 📑 Background Table  

This table **powers the horizontal bar chart** for **median salaries by job titles** and the **Median Salary KPI card**.  

![1_Salary_Dashboard_Screenshot1](https://github.com/user-attachments/assets/cda21195-1af7-4182-b51e-2a5cc749f49e)

---

## 📉 Dashboard Implementation  

The **horizontal bar chart** displays **median salary by job titles**, providing a **clear comparison of salary distributions** across different roles.  

<img src="https://github.com/user-attachments/assets/e5e78345-f9bc-4ad3-8dcf-cf30e87a2b82" width="500"/>

---

## ⏰ Count of Job Schedule Type  

```excel
=FILTER(J2#, (NOT(ISNUMBER(SEARCH("and", J2#))) + NOT(ISNUMBER(SEARCH(",", J2#)))) * (J2#<>0))
```
- 🔍 **Unique List Generation** – Uses `FILTER()` to exclude duplicate entries, removing any containing `"and"` or `","`.  
- 🔢 **Formula Purpose** – Creates a structured list of unique job schedules, used for further salary analysis.  

## 📑 Background Table  

This table **drives the bar chart** for **median salary by schedule types** and the **Job Count KPI card**.  

![1_Salary_Dashboard_Screenshot2](https://github.com/user-attachments/assets/e10d7232-1b0b-497c-b31b-032ae93854c7)

---

## 📉 Dashboard Implementation  

The **horizontal bar chart** visualizes **median salaries based on job schedule types**, enabling users to **compare salary variations by work schedule**.  

<img src="https://github.com/user-attachments/assets/b191b8ac-b357-4dc3-9216-220c62427832" width="500"/>

---

## ❎ Data Validation  

🔍 **Filtered List** – Applied as a **data validation rule** for **Job Title, Country, and Schedule Type** dropdowns.  
🔒 **Enhanced Data Validation** – Ensures:  
🎯 **User input is restricted** to **validated schedule types**.  
🚫 **Prevents incorrect or inconsistent data entries**.  
👥 **Improves dashboard usability** by enforcing **clean and structured data input**.  

 ![1_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/32ed2bc5-8260-4086-ba24-e5218ecf58d4)

---

## 🏁 Conclusion  

I created this dashboard to **analyze salary trends** across various **data-related roles**, providing **valuable salary insights** for job seekers and professionals.  

By leveraging **real-world job postings**, this project highlights how **job title, location, and work schedule** impact salary levels, helping users make **informed career decisions**.  


