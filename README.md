# Hospital Emergency Room Analysis

This is a Power BI project I have done after taking the Excel Skills for Data Analytics and Visualization Specialization from Macquarie University.

### Project Overview
This data analysis project aims to provide insights into the efficiency of a Hospital Emergency Room, enabling the hospital to make data-driven decisions to improve its efficiency and patient satisfaction.

### Data Source
Hospital Emergency Room Data: The primary dataset used for this analysis is the "Hospital ER_Data.csv" file. It contains detailed personal information about patients who had visited the Emergency Room of this hospital in 2023-2024.

### Tools Used
Power BI (Data Cleaning and Preparation in Power Query, Measures and Date table created in DAX)

### Data Cleaning and Preparation

1. Data Loading and inspection:

2. Check for row duplicates by checking if all patient IDs are unique)

3. Replacing short forms such as F,M, and CM to Female, Male, and Not Confirmed under the Patient Gender Column

4. Changing data type from date/time to time for my new 'Start of Hour Column'

5. Creating new columns to assist with analysis:

  - Admission Date: Extract out only the date from date and time 

  - Age Group: Use a conditional column to group patients into different age bands

  - Wait Time: Use a conditional column to split wait time to different groups

6. Create a Date Table in DAX to assist with analysis of data over Year, Month, and Day.

### Some Measures
- Correlation Coefficient
- Number Of Patients = DISTINCTCOUNT('Hospital ER_Data'[Patient Id])
- Average Wait Time = AVERAGE('Hospital ER_Data'[Patient Waittime])
- Number Of Patients Referred = CALCULATE(COUNTROWS('Hospital ER_Data'),'Hospital ER_Data'[Department Referral]<>"None")
- Hospital Admission = CALCULATE(COUNT('Hospital ER_Data'[Patient Admission Flag]), ('Hospital ER_Data'[Patient Admission Flag] = "TRUE"))
- Admission Rates = DIVIDE([Hospital Admission],[Number Of Patients],0)

### Exploratory Data Analysis
EDA involved exploring the emergency room data to answer key questions such as 
- What is the busiest day and hour for the Emergency Room?
- What is the patient demographic? (Race, Gender, and Age)
- Does the wait time differ by race or gender?
- Is there any correlation between patient satisfaction and wait time
- Is there any possible relationship between patient satisfaction, wait time, and age
- What are the common departments that patients are referred to?


### Key Takeaways

#### Number of Patients By Day and Hour (2023-2024)

<img width="350" height="400" alt="image" src="https://github.com/user-attachments/assets/a6015397-a340-404b-abd3-8c0faa592dab" />


The busiest day is Saturday(1377 Patients), followed by Thursday(1332 Patients), and Sunday(1318 Patients).
The least busy day is Wednesday (1260 Patients)

The busiest Hour is 22:00 - 23:00(808 Patients), followed by 06:00 - 07:00(790 Patients), and 00:00 - 01:00(778 Patients)

Based on these data, the busiest days and hours tend to lie on the weekends and happen late at night or early in the morning. This is the case as patients might have postponed their medical visits until after work or school, or because most regular doctors' offices and clinics are closed at these times.

### Patient Demographics (2023-2024)

The percentage of male and female patients is relatively similar, where they each make up close to half of the total number of patients. 

The 30-39(1200 Patients) and 20-29(1188 Patients) age group makes up a large portion of the patients visiting the Emergency R Room. Meanwhile, the 0-9 age group makes up the smallest portion of the patients visiting the ER.

White people make up the largest number of patients visiting the ER (27.9%), followed by African Americans (21.2%).
However, both Native Americans(5.4%) and Pacific Islanders (5.4%) make up the smallest proportion of total patients visiting the Emergency Room.

### Wait Time by Gender and Race

<img width="485" height="212" alt="Screenshot 2025-08-12 145215" src="https://github.com/user-attachments/assets/d9761acf-56ea-4831-9a8d-658b54d93619" />

<img width="500" height="236" alt="Screenshot 2025-08-12 145537" src="https://github.com/user-attachments/assets/94d72627-2dfb-4479-b1d8-1723bde21449" />

In general, there is not much difference in wait time between patients of different races and genders, suggesting a rather fair queuing system.

### Correlation between Patient Satisfaction and Wait Time

<img width="512" height="200" alt="image" src="https://github.com/user-attachments/assets/be6b414f-7a53-43ae-9cb7-5d46f92f612b" />

The correlation coefficient is 0.43, indicating that there is a moderate positive correlation between patient satisfaction
and wait time. This tells us that there are likely other factors beyond wait time.

### Relationship between Patient Satisfaction, Wait Time, and Age

<img width="350" height="400" alt="Screenshot 2025-08-13 150529" src="https://github.com/user-attachments/assets/f9c94cb4-1348-4f29-91ff-37ae183c72c9" />

In general, patients in age groups (10-19), (30-39), and (40-49) tend to be much less satisfied when wait time exceeds 40 minutes. Patients of ages 70-79 have much lower satisfaction regardless of time when compared to other age groups.

### Departments patients are usually referred to

<img width="484" height="203" alt="Screenshot 2025-08-13 152018" src="https://github.com/user-attachments/assets/5068e207-fa0d-4640-af0f-da42a4980637" />

In general, the proportion of patients referred to the various departments is relatively similar across all age groups.
The department with the greatest number of referrals is general practice, while the department with the least number of referrals is renal.
