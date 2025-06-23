# Leveraging HR Data for Workforce Insights: A Business Intelligence Dashboard for Chinazam Auto Parts

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploring Data Analysis](#exploring-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#results/findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)

### Project Overview

The purpose of this project is to provide Human Resource (HR) managers with actionable insights into their workforce by leveraging a comprehensive dataset of employee information. The dataset includes key demographic and performance indicators such as employee age, gender, position, salary, hiring and termination details, departmental data, performance and engagement scores, as well as employee satisfaction metrics. Through exploratory data analysis (EDA), the project aims to:

- Understand employee demographics and distribution across departments and positions.

- Identify patterns related to turnover, hiring, and terminations.

- Assess departmental performance and satisfaction levels.

- Evaluate diversity within the organization and compare it to industry standards.

- Enable data-driven decisions for HR policies and talent management strategies.

![Overall Dashboard](https://github.com/user-attachments/assets/9778aaa4-a234-4da7-aa0d-c956586d6f55)

### Data Sources

Employee Data: The primary data set used for this analysis is the "HRData.csv" file containing detailed information about each employee demographics obtained from the HR department of Chinazam Auto Parts Inc.

### Tools
- Excel - Data Analysis [Download here](https://microsoft.com)
- PowerPoint -  Dashboard Background Design [Download here](https://www.microsoft.com/en-ca/microsoft-365/powerpoint)
- Power BI - Dashboard Design [Download here](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads)

### Data Cleaning and Preparation
In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploring Data Analysis

EDA involved exploring the HR data to answer key questions, such as:

- What is the overall gender distribution across all departments?
- What are the common recruitment sources?
- Which departments have the highest turnover rates?
- What is the average salary across departments and positions?
- Are there gender or marital status-based salary disparities?
- How do performance and satisfaction scores vary by gender?

### Data Analysis

Some interesting DAX calulations used for data analysis are as follows:
```DAX 
Active = IF(ISBLANK(CALCULATE([Headcount], HRData[Status Group]="Active")),0,CALCULATE([Headcount], HRData[Status Group]="Active"))

Active % = DIVIDE([Active], [Headcount], 0)

Female = IF(ISBLANK(CALCULATE([Headcount],HRData[Gender]="F")),0,CALCULATE([Headcount],HRData[Gender]="F"))

Female % = DIVIDE([Female],[Headcount],0)

Headcount = COUNTROWS(HRData)

Male = IF(ISBLANK(CALCULATE([Headcount],HRData[Gender]="M")),0,CALCULATE([Headcount],HRData[Gender]="M"))

Male % = DIVIDE([Male],[Headcount],0)

Salary = SUM(HRData[Salary])

Terminated = IF(ISBLANK(CALCULATE([Headcount], HRData[Status Group]="Terminated")),0,CALCULATE([Headcount],
 
HRData[Status Group]="Terminated"))

Terminated % = DIVIDE([Terminated], [Headcount], 0)
```
### Results/Findings

Based on preliminary analysis, the results obtained are as follows:

1. The workforce has a greater number of female employees compared to their male counterpart.
2. Indeed and LinkedIn dominate as recruitment sources.
3. The overall number of Active and Terminiated employee is in the ratio of 2:1 prompting further review into the various factors associated with employee termination
4. Strong positive correlation (r = 0.65) observed between performance scores and employee engagement survey results.
5. Minor salary gaps observed between male and female employees, prompting further review and potential salary adjustments.
6. Departments with higher engagement survey scores also exhibit higher employee satisfaction levels, suggesting strong team dynamics and effective management.

### Recommendations

Based on the we recommend the following actions:
- Maintain inclusivity by promoting gender diversity across departments and roles.
- Leverage the success of Indeed and LinkedIn, while exploring additional platforms to diversify the candidate pool.
- Investigate the root causes of employee turnover and implement targeted retention and engagement strategies.
- Strengthen feedback, recognition, and reward programs to further drive performance through increased engagement.
- Conduct regular salary reviews to address and rectify any gender pay gaps, ensuring equitable compensation practices.
- Identify departments with strong engagement and satisfaction, and replicate their practices across the organization.

### Limitations

Although this project provides valuable insights into workforce demographics and dynamics, it is subject to certain limitations. Firstly, the dataset lacks qualitativeinputs, such as employee interviews or open‑ended survey responses that could deepen understanding of the underlying causes behind trends. The statistical relationships identified, such as those between engagement and performance, do not imply direct causation. Secondly, the data reflects a snapshot in time, making it challenging to assess long‑term trends. Lastly, external influences, such as economic shifts, competitive market dynamics, or changes in organizational policies, were also not accounted for in this analysis.
