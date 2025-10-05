## Patient Data Cleaning Using Python and Power Query

### Table of Contents
1. [Project Overview](#project-overview)
2. [Objectives](#objectives)
3. [Data Challenges Observed](#data-challenges-observed)
4. [Data Cleaning Approach](#data-cleaning-approach)
5. [Tools](#tools)
6. [Key Learnings](#key-learnings)

### Project Overview
This project demonstrates how to transform messy healthcare data into a clean, analysis-ready dataset. It combines the efficiency of Python's automation with Power Query's data transformation capabilities to achieve data quality.

### Objectives
- Detect and correct inconsistent date formats
- Remove invalid or impossible dates
- Fill missing date values using Powe Query's Fill Down
- Strip time components from datetime fields
- Ensure data uniformity for further analysis

### Data Challenges Observed
- Multiple inconsistent date formats(12/13-2023, April 31, 2022, 13.04.2024)
- Excel serial and float date values (43120, 45756, 45472)
- Missing or invalid dates (2023-02-30)
- Noise such as (estimated) in data columns
- Date-time values including unnecessary time portions(2024-10-16 00:00:00)

### Data Cleaning Approach
Step 1 - Python Cleaning
- Used Pandas and dateutil to:
  - Standardize all date columns into a uniform YYYY-MM-DD
  - Automatically detect and fix numeric(serial) and string dates
  - Remove text noise and impossible dates
  - Save a clean version in sheet 2 as Python_DC
Step 2 -Power Query Refinement
- Imported the python cleaned Excel file into Power Query to:
  - Use the Fill Down function to fill missing date cells
  - Convert all datetime columns to date only (removed time)
  - Verify column consistency before export
  - Save first cleaned dataset with the timestamp in sheet 3 as PowerQuery_DC
  - Save final dataset in Sheet 4 as PowerQuery_FDC
The final excel workbook has 4 sheets following the order below;
- Sheet1: Messy patient data appearing as messy_patient_data
- Sheet2: Messy patient data cleaned with python appearing as Python_DC
- Sheet3: Clean version of messy patient data with timestamp appearing as PowerQuery_DC
- Sheet4: Clean version of messy patient data without timestamp appearing as PowerQuery_FDC
- The Excel workbook was saved as [Cleaned_Patient_Data.xlsx](https://github.com/user-attachments/files/22708800/Cleaned_Patient_Data.xlsx)

### Data Sources
The primary dataset used is the [Messy Patient Data.xlsx](https://github.com/user-attachments/files/22708789/Messy.Patient.Data.xlsx) file, containing the messy patient data used.

### Tools
- Anaconda (Pandas, Numpy, dateutil)
- Microsoft Excel Power Query
- Jupyter Notebook
  
### Key Learnings
- Power Query's Fill Down feature complements Python automation for real world data cleaning
- Proper documentation of cleaning workflow ensures transparency and reproducibility
  

