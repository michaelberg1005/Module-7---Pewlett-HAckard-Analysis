# Module-7---Pewlett-HAckard-Analysis
Module 7 UCB work
## Problem trying to solve
There are two key problems we are trying to solve
1. How many employees of each title are retirement ready and are expected to leave so management knows how many of each position it needs to replace.
2. Which employees are eligible for a mentorship program in order to help facilitate the training and development of the future employees who are going to replace the ones retiring.
## Description of Analysis
Here is a detailed list of the steps I did to find out the answers to the problems we are trying to solve:
1. I created a table of the requisite information (employee no, first and last name, title, from date and salary into a new table using inner joins with employee numbers as teh primary/foreign keys, but was filtered by employee eligible for retirement using "WHERE" statements.
2. However, I ran into a problem, where employees who had been there a long time had gone through multiple titles, and we only wanted the most recent title, as that is the role that would have to be replaced.
3. In order to filter the data down further to only include the most recent title for retirement eligible employees, I used a partitioning method on employee no, first and last name, from date and title from the table i just created in step 1, and ordered it by employee no. 
4. To determine eligible employees for the mentorship program i created a table filtering the employee data by employees born in 1965 with a WHERE statement. 
5. I then needed to join other requisite information from the titles table with an INTO and JOIN statements, but filtered by current employees using a WHERE statement on date '9999-01-01'.
## Summary of Results
1. Based on my analysis of Pewlett Hackard employees, there are 31,118 employees who were born between 1/1/1952 amd 12/31/1955, who are retiring soon and are current employees. Within that, there are 251 Assistant Engineers, 2,711 Engineers, 2 Managers, 13,651 Senior Engineers, 12,872 Senior Staff, 2,022 Staff and 1,609 Technique Leaders who are going to be retiring. Please see csv table titled "retirement_by_title_challenge_table_1" for a cleaner view of this data.
2. There are 1,549 employees who are availble for the mentorship role, based on the criteria of being born in 1965. Please see csv table titled "mentorship_list_challenge_table_2" for complete details of the employees availble for the mentorship role.

PLEASE SEE "schema.sql" for technical code behind table creation for items 1 and 2, as well as the queries used to help filter the data. Challenge code begins line 199.

## Additional Recommendations, Limitations and Next Steps
One recommendation/next step for further analysis on this data set would be to filter the mentorship roles further, by assigning people with a subset of titles, who have the proper level of seniority, coupled with potentially more time, to help increase the focus on who would be a good fit. Another analysis to do with this data set is to see the average salary of each title for the whole company, then compare it to the average salary of the retiring employees to see how much money should be "saved" or "lost" by replacing retiring employees with an average salaried one. It is also worth noting that one key limitation of this analysis are you don't know the location of where the employees are located, and salaries could vary by geography, especially when replacing those titles.

## ERD Schema Map
Please see below for my ERD schema map i used to help filter the data of Pewlett Hackard:
![ERD Schema Map Pewlett Hackard](https://github.com/michaelberg1005/Module-7---Pewlett-HAckard-Analysis/blob/master/EmployeeDB.png)
