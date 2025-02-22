# Excel Data Job Analysis

## Introduction  

As someone passionate about data, I wanted to analyze the **best-paying jobs and most in-demand skills** in the data industry. This project allowed me to explore **key trends in the data job market** while also improving my **Excel skills** by using advanced data analysis features.  

### Questions to Analyze
To understand the data science job market, I asked the following:

 1. **Do more skills get you better pay?**  
 2. **What’s the salary for data jobs in different regions?**  
 3. **What are the top skills of data professionals?** 
 4. **What’s the pay for the top 10 skills?**  

### Excel Skills Used  

The following **Excel features** were essential for this analysis:  
- 📊 **Pivot Tables** – Organizing and summarizing salary data  
- 📈 **Pivot Charts** – Visualizing insights from the dataset  
- 🧮 **DAX (Data Analysis Expressions)** – Custom calculations for deeper analysis  
- 🔍 **Power Query** – Extracting and transforming data  
- 💪 **Power Pivot** – Creating relationships between datasets  

### Data Jobs Dataset  

This dataset provides **detailed insights into data-related jobs from 2023**, helping to uncover trends in salaries and required skills. It includes:  

- 👨‍💼 **Job Titles** – Roles in the data industry  
- 💰 **Salaries** – Median salaries based on job type and location  
- 📍 **Locations** – Country-based salary variations  
- 🛠️ **Skills** – The most in-demand technical skills  

---

## 1. Do more skills get you better pay?  

### **🔍 Tool Used: Power Query (ETL)**  

**📥 Extract**  
- I used **Power Query** to extract the original dataset ```data_salary_all.xlsx``` and created two queries:
  - **First one with all the data jobs information**, focusing on salaries.  
  - **Another listing the skills associated with each job ID.**    

**🔄 Transform**  
- Cleaned the dataset by **changing column types, removing unnecessary columns, and formatting text**.  
- Eliminated duplicate values, unnecessary characters, and **trimmed extra whitespaces** for better analysis.  

📊 **data_jobs_all**  
![2_Project_Analysis_Screenshot1](https://github.com/user-attachments/assets/a649f234-ae85-4815-b130-4fc2800dd8f5)  

🛠️ **data_job_skills**  
![2_Project_Analysis_Screenshot2](https://github.com/user-attachments/assets/18afc8b9-77b8-45be-a772-f14e56173eeb)  

**🔗 Load**  
- Finally, loaded the **transformed queries** into the workbook to prepare for analysis.

📊 **data_jobs_all** 
![2_Project_Analysis_Screenshot3](https://github.com/user-attachments/assets/dd474c1b-536f-4eee-9bea-d7801fb1e4f5)

🛠️ **data_job_skills**  
![2_Project_Analysis_Screenshot4](https://github.com/user-attachments/assets/014bb36f-cdd8-4e39-80ea-0a4ba809cf6a)

### **📊 Analysis**  

- 📈 There is a **clear connection** between the **number of skills required in job postings and median salary**—jobs that demand **more skills** tend to list **higher salaries**, especially for roles like **Senior Data Engineer** and **Data Scientist**.  
- 💼 Roles with **fewer required skills**, such as **Business Analyst**, generally offer **lower salaries**, reinforcing the idea that **specialized skill sets** command **higher market value**.  
- 🔍 Acquiring **multiple relevant skills** is crucial for **workers and job seekers** looking to **increase their earning potential** in the data industry.  

![2_Project_Analysis_Chart1](https://github.com/user-attachments/assets/9b348dcb-cd32-4ef4-922c-fd2bdf4fe5ba)  

---

## 2. What’s the salary for data jobs in different regions?  

### **🛠 Tool Used: PivotTables & DAX**  

📈 **Pivot Table**  
- Using **Power Pivot** and the **data model**, I created a **PivotTable** with ```job_title_short``` in the rows and ```salary_year_avg``` in the values section.  
- Then, I added a **new measure** to calculate the **median salary for United States jobs**.  
- *(I would have liked to focus this on Greece, but not enough data was present in the dataset to get relevant information.)*  

```excel
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)
```

