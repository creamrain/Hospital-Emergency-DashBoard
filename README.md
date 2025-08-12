# Hospital Emergency Room Analysis


### Project Overview
This data analysis project aims to provide insights into the efficiency of a Hospital Emergency Room, enabling the hospital to make data-driven decisions to improve its efficiency and patient satisfaction.

### Data Source
Hospital Emergency Room Data: The primary dataset used for this analysis is the "Hospital ER_Data.csv" file, containing detailed personal information about patients who had visited the Emergency Room of this hospital in 2023-2024.

### Tools Used
Power BI (Data Cleaning and Preparation in Power Query, Measures and Date table created in DAX)

### Data Cleaning and Preparation

1. Data Loading and inspection:

2. Check for row duplicates by checking if all patient IDs are unique)

3. Replacing short forms such as F,M, and CM to Female, Male, and Not Confirmed under the Patient Gender Column

4. Changing data type from date/time to time for my new 'Start of Hour Column'

5. Creating new columns to assist with analysis:

  - Admission Date: Extract out only the date from date and time 

  - Age Group: Use conditional column to group patients into different age bands

  - Wait Time: Use conditional column to split wait time to different groups

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
<img width="520" height="565" alt="image" src="https://github.com/user-attachments/assets/a6015397-a340-404b-abd3-8c0faa592dab" />

The busiest day is Saturday(1377 Patients), followed by Thursday(1332 Patients), and Sunday(1318 Patients).
The least busy day is Wednesday (1260 Patients)

The busiest Hour is 22:00 - 23:00(808 Patients), followed by 06:00 - 07:00(790 Patients), and 00:00 - 01:00(778 Patients)

Based on these data, the busiest days and hours tend to lie on the weekends and happen late at night or early in the morning. This is the case as patients might have postponed their medical visits until after work or school, or because most regular doctors' offices and clinics are closed at these times.

### Patient Demographics (2023-2024)

The percentage of male and female patients is relatively similar, where they each make up close to half of the total number of patients. 

The 30-39(1200 Patients) and 20-29(1188 Patients) age group makes up a large portion of the patients visiting the Emergency R Room. Meanwhile, the 0-9 age group makes up the smallest portion of the patients visiting the ER.

White people make up the largest number of patients visiting the ER (27.9%), followed by African Americans (21.2%).
However, both Native Americans(5.4%) and Pacific Islanders (5.4%) make up the smallest proportion of total patients visiting the Emergency Room.

### Wait Time by Gender and Race)


Sun: 1318
Mon 1314
tue: 1305
wed: 1260
thurs 1332
fri: 1310
    
