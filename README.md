# Remote-work-and-mental-health

## Table of Contents

- [Project overview](#project-overview)
- [Data Source](#Data-source)
- [Recommendations](#Recommendations)

### Project Overview

This project aims to assess the impact of remote work on employees' mental health, focusing on key areas such as stress levels, social isolation, and job satisfaction. By analyzing these factors across various demographics and work locations (remote, hybrid, onsite), the study seeks to reveal patterns that can inform better support strategies. The insights gathered will guide recommendations for organizations, helping them to implement policies and resources that enhance mental well-being, foster a healthier work-life balance, and create a supportive work environment for remote employees.

### Data Source

Remote Work & Mental Health Data: The primary Data set used for this analysis is the "Imapct_of_Remote_Work_on_Mental_Health.csv", file, containing information
about the Impact of remote work on mental health from Kaggle.com.

## Tools
- Excel- Data cleaning
- SQL - Data Analysis
- Tableau - Visualisation 

### Data Cleaning/Preperation

Duplicate Removal: To maintain data integrity, I checked the dataset for duplicate values within the "Employee_ID" column and removed any duplicates found.

Blank Cell Verification: I thoroughly inspected the dataset for blank cells in each column to ensure completeness, confirming that there were no missing values.

Spell Check: I utilized Excel's spell check function to verify correct spelling throughout the dataset, ensuring clarity and professionalism in all text fields.

Data Validation: I applied data validation to the "Work_Location" column to restrict entries to "Onsite," "Remote," and "Hybrid," preventing any inconsistent values.

Data Structuring: I organized the dataset into an Excel table format, improving readability and enabling more efficient data manipulation.

Find and Replace: I used the "Find and Replace" function to identify and correct any inconsistencies or unintended data entries, ensuring accurate, standardized information across all columns.

Overall, while the dataset was relatively clean initially, I applied these steps to verify its accuracy, completeness, and proper formatting.

### Exploratory Data Analysis

How does work location (remote, hybrid, onsite) influence stress levels?

What is the relationship between social isolation and job satisfaction?

Are there demographic trends in mental health conditions?

Does access to mental health resources vary by work location, and how does this impact stress levels?

### Data Analysis

Included some SQL queries I deployed

SQL:

Regarding this Question: How does work location (remote, hybrid, onsite) influence stress levels?

Data Overview:
The dataset contains information about employees' Work Location and their corresponding Stress Level. The stress levels are categorized as:

Low
Medium
High

To perform the analysis, stress levels were assigned numeric values for easier calculation:

Low = 1
Medium = 2
High = 3

Methodology:
The analysis was carried out using an SQL query to calculate the average numeric stress level for each work location (Remote, Hybrid, Onsite). The SQL query converts the Stress_Level categories into numeric values, calculates the average stress level for each work location, and rounds the result to two decimal places for clarity.

SQL Query Used:

SELECT Work_Location,
       ROUND(AVG(CASE 
                  WHEN Stress_Level = 'low' THEN 1
                  WHEN Stress_Level = 'medium' THEN 2
                  WHEN Stress_Level = 'high' THEN 3
                  ELSE NULL 
                END), 2) AS avg_numeric_stress_level
FROM remote
WHERE Stress_Level IS NOT NULL
GROUP BY Work_Location;

Results:
The query results in the following average numeric stress levels for each work location:

<img width="212" alt="image" src="https://github.com/user-attachments/assets/3c1f9ae4-0977-4f76-a27e-c1069066d6f6">

Interpretation:
Hybrid workers have an average stress level of 2.01, which is close to Medium on the stress scale.

Remote workers have a slightly higher average stress level of 2.03, indicating that remote workers, on average, experience a medium level of stress.

Onsite workers have an average stress level of 1.99, which is just slightly below 2.0 (Medium), suggesting that the average stress level for onsite employees is close to medium but slightly lower than hybrid and remote workers.
