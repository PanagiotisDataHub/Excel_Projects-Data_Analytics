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

🧮 **DAX**  
To determine the **median yearly salary**, I utilized **DAX** for accurate calculations.  

```excel
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### **📊 Analysis**  

- 💼 **Senior Data Engineer** and **Data Scientist** roles offer **higher median salaries** both in the **US and internationally**, emphasizing the **global demand for advanced data expertise** and the need for **competitive salary negotiation**.  
- 💰 A **significant salary gap** exists between **US and Non-US positions**, particularly in **high-tech jobs**, making it essential for professionals to **align salary expectations** with market standards.  
- 🌍 **Non-US regions may be underrepresented** in the dataset, highlighting the importance of **researching local salary data** to ensure **fair compensation**.  

![2_Project_Analysis_Chart2](https://github.com/user-attachments/assets/099a3a15-9e67-4c23-9e23-b85fc819bc62)

---

## 3. What are the top skills of data professionals?  

### **🛠 Tool Used: Power Pivot**  

💪 **Power Pivot**  
- Integrated the ```data_jobs_all``` and ```data_jobs_skills``` tables into **one model**.  
- Since the data was already cleaned in **Power Query**, Power Pivot automatically created a **relationship between these tables**.  

🔗 **Data Model**  
- Established a **relationship between both tables** using the ```job_id``` column. 

![2_Project_Analysis_Screenshot5](https://github.com/user-attachments/assets/aeb705b5-030c-413a-af83-49105402ac3d)

📃 **Power Pivot Menu**  
- The **Power Pivot menu** was used to refine the data model, allowing for **easier calculation of measures**.  

 ![2_Project_Analysis_Screenshot6](https://github.com/user-attachments/assets/bd5b50f5-9946-4ee2-84a3-188a32a67a7e)

### **📊 Analysis**  

- 💻 **SQL and Python** dominate as **the most in-demand skills** in data-related jobs, reinforcing their role as **essential tools in data processing and analysis**.  
- ☁️ **Cloud platforms like AWS and Azure** have a strong presence, highlighting the industry’s **transition towards cloud computing and big data technologies**.  
- 🎯 Understanding which skills are most sought after **helps professionals stay competitive** and enables **educational programs to focus on the most valuable technologies**.  

![2_Project_Analysis_Chart3](https://github.com/user-attachments/assets/5c96c3c9-00b0-4389-9346-2f23b1d1bdb3)

---

## 4. What’s the pay of the top 10 skills?  

### **🛠 Tool Used: Advanced Charts (Pivot Chart)**  

📈 **PivotChart**  
- Created a **combo PivotChart** to visualize **median salary** alongside **skill likelihood (%)** from the **PivotTable**.  
  - **Primary Axis:** Displays **Median Salary** using a **Clustered Column** chart.  
  - **Secondary Axis:** Shows **Skill Likelihood (%)** as a **Line with Markers**.  
- Customized the chart by **adding titles**, **removing unnecessary gridlines**, and **changing markers to diamonds** for better clarity.  

### **📊 Analysis**  

- 💰 **Higher median salaries** are strongly linked to **skills like Python, Oracle, and SQL**, emphasizing their importance in **high-paying tech roles**.  
- 📉 **Skills like PowerPoint and Word** tend to have **lower median salaries and demand**, indicating that **general office tools are less valued in high-paying data jobs**.  
- 🎯 This reinforces the importance of **investing in specialized technical skills**, particularly for professionals looking to **maximize their salary potential**.

![2_Project_Analysis_Chart4](https://github.com/user-attachments/assets/f1338cec-5187-41b9-8126-010b3f653d2c)

## **🏁 Conclusion**  

This project allowed me to explore **key trends in the data science job market** while strengthening my **Excel skills**. By analyzing **real-world job postings**, I examined **job titles, salaries, locations, and in-demand skills**, helping job seekers make **informed career decisions**.  

Through **Power Query, PivotTables, DAX, and advanced charts**, I identified **strong correlations between technical skills and salary levels**, particularly in **Python, SQL, and cloud technologies**.  

I hope this project not only offers **valuable insights into the data job market** but also showcases the **Excel features and functionalities** I learned through the **Excel for Data Analytics course**.  

