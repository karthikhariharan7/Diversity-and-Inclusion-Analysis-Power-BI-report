
# Diversity & Inclusion Analysis

This dashboard helps the Human Resources at our PhoneNow telecom client is highly into diversity and inclusion. They’ve been working hard to improve gender balance at the executive management level.

# Diversity & Inclusion Analysis-Dashboard

### Dashboard Link :https://app.powerbi.com/view?r=eyJrIjoiMzhiY2E4NzktMTc4Yy00OWM5LTg2ZDgtMzQwNjcxNjY4YzNiIiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9

## Problem Statement

Create visualizations to represent HR data, particularly focusing on gender-related KPIs. Identify and discuss potential root causes for the slow progress in achieving gender balance at the executive management level.

### Tools used - Power BI

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4: The data was good enough to start calculations
- Step 5: Created a new measure table to store all measures inside this table for clarity.
- Step 6: A measure to calculate the count of Total Employees & count of Leavers
            
            # of Employee = DISTINCTCOUNT('Pharma Group AG'[Employee ID])
            # of Leavers = CALCULATE(count('Pharma Group AG'[Employee ID]),'Pharma Group AG'[FY20 leaver?]="Yes")
- Step 7: A measure to calculate the count of Men & Women Employees.
            
            # of Men = CALCULATE(Count('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Gender]="Male")
            # of Female = CALCULATE(Count('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Gender]="Female")
- Step 8:  A measure to calculate the hire percentage of Men & Women Employees.

            Men Hired % = DIVIDE(CALCULATE([# of Employee],'Pharma Group AG'[Gender]="Male",'Pharma Group AG'[New hire FY20?]="Y"),CALCULATE([# of Employee],'Pharma Group AG'[New hire FY20?]="Y"))
            Women Hired % = DIVIDE(CALCULATE([# of Employee],'Pharma Group AG'[Gender]="Female",'Pharma Group AG'[New hire FY20?]="Y"),CALCULATE([# of Employee],'Pharma Group AG'[New hire FY20?]="Y"))

- Step 9: A measure to calculate the percentage of Employees Promoted in (FY21) & Women Employees Promoted.

            % Employees promoted (FY21) = DIVIDE(CALCULATE([# of Employee],'Pharma Group AG'[Promotion in FY21?]="Yes"),[# of Employee])
            % of women promoted = DIVIDE(CALCULATE([# of Employee],'Pharma Group AG'[Gender]="Female",'Pharma Group AG'[Promotion in FY21?]="Yes" || 'Pharma Group AG'[Promotion in FY20?]="Y"),[# of Employee])
- Step 10: A measure to calculate the Performance Rating of Men & Women.

            Men performance rating = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Male")
            Women performance rating = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Female")
- Step 11: Slicers added for Department, Job level, Age Group & Region Group is added.
- Step 12 - Donut, bar & line charts are used to present the above data.

# Insights

A Double page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Male & Female Customers = 500

- Number of Male Employee = 295

- Number of Female Employee = 205

- Percentage of Men Hired = 48%

- Percentage of Women Hired = 51.5%

           
### [2] Average Ratings
- Overall Men Performance Rating - 2.41

- Overall Women Performance Rating - 2.42
  
  
### [3] Leavers Percentage
- Men leavers percentage - 55.32%

- Women leavers percentage - 44.68%

 ### [4] Some other insights
 
 - In HR Department Womens have 100% hiring rate 

 - In Executive Job level Men have 100% hiring rate
