# Hospital Emergency Room Analysis


### Project Overview
This data analysis project aims to provide insights into the efficiency of a Hospital Emergency Room, enabling the hospital to make data-driven decisions to improve its efficiency and patient satisfaction.

### Data Source
Hospital Emergency Room Data: The primary dataset used for this analysis is the "Hospital ER_Data.csv" file, containing detailed personal information about patients who had visited the Emergency Room of this hospital in 2023-2024.

### Tools Used
Power BI (Data Cleaning and Preparation in Power Query, Measures and Date table created in DAX)

### Data Cleaning and Preparation

Data Loading and inspection (Specific: check for row duplicates by checking if all patient IDs are unique)

Replacing short forms such as F,M, and CM to Female, Male, and Not Confirmed under the Patient Gender Column

Changing data type from date/time to time for my new 'Start of Hour Column'

Creating new columns to assist with analysis:
Admission Date: Extract out only the date from date and time 
Age Group: Use conditional column to group patients into different age bands
Wait Time: Use conditional column to split wait time to different groups

Create Date Table in Dax to assist with analysis of data over Year, Month, and Day.




    
