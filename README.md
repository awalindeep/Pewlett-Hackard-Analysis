# Pewlett Hackard Analysis

*Analysis with SQL for Pewlett Hackard HR Department*

## Project Overview

The purpose of this analysis is to prepare Pewlett-Hackard, a company with several thousand employees, for the upcoming “silver tsunami”. A large number of employees will begin retiring at a rapid rate in the next few years and the company wants to be prepared with the retirement packages, open positions and employees’ training. In order to ensure a smooth transition this analysis focuses on the following:

1. Identify the retiring employees by their title.
2. Determine the sum of retiring employees grouped by title.
3. Identify the employees eligible for participation in the mentorship program.
4. Determine the number of roles-to-fill grouped by title and department.
5. Determine the number of qualified, retirement-ready employees to mentor the next generation grouped by title and department.

## Background

The data is gathered from six CSV files and the analysis is performed using relational databases. In this analysis we are using:

-   **QuickDBD**  to create quick database design for better visualization,
-   **PostreSQL**  a database system to load, build and host company’s data, and
-   **pgAdmin**  a GUI, using SQL Language to explore, manipulate and extract the data.
- 
### Resources Utilized to Complete Analysis

-   **Data Sources:**  
[departments.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/departments.csv), [dept_emp.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/dept_emp.csv), [dept_manager.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/dept_manager.csv), [employees.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/employees.csv), [salaries.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/salaries.csv), [titles.csv](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/titles.csv)
    
-   **Entity Relationship Diagram (ERD) Tool**:  [Quick Database Diagrams](https://www.quickdatabasediagrams.com/)
    
-   **Relational Database Management System**: PostgreSQL, pgAdmin
    

## Pewlett Hackard Employee Database ERD and Schema

**ERD** An entity-relationship diagram (ERD) is crucial to creating a good database design. It is used as a high-level logical data model, which is useful in developing a conceptual design for databases.

![EmployeeDB](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/EmployeeDB.png)
                            

**Schema**  - A  [schema](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Queries/schema.sql) is a blueprint or architecture of how data will look. It is a description of the actual construction of the database, an all-encompassing term that refers to the collective of tables, columns, triggers, relationships, key constraints, functions and procedures. Schemas are important for designing database management systems or relational database management systems .
## Results

**1. The list of retiring employees**

-   The table displays a list of employees who is going to retire in the next few years.
-    The table includes employee number, first name, last name, title, from-date and to-date.
-   The query returns 133,776 rows.
-   The list is long and extensive, yet at-a-glance analysis gives us some insights about the query. Some employees appear more than once due to change of title during their career at Pewlett-Hackard.

![Emp_Duplicates](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/EmployeesTitleDuplicates.PNG)

The query contains data all the titles that employees working at Pewlett-Hackard over the years. This resulted in duplicates, some employees appear two times or more; therefore, the number of retiring employees (133,776) is incorrect.

**2. The list of retiring employees without duplicates**

-   The table displays a list of employees who are going to retire in the next few years.
-  The table includes employee number, first name, last name, title, from-date and to-date.
-   The query returns 90,398 rows.
-   In the table each employee is listed once, as per their most recent title.

![emp_noDuplicates](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/EmployeeTitlesNoduplicates.png)


**3. The number of retiring employees grouped by title**

-   This query returns a cohesive table with 7 rows.
- The table includes employees’ titles and their sum.
-   From this table we can quickly see how many employees with certain title will retire in the next few years.

![Sumofemp](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/SumofEmployeetitles.png)

**4. The employees eligible for the mentorship program**

-   This query returns 1,549 rows.
-   The table contains employee number, first name, last name, birth date, from date, to date and title.
-   The table displays a list of employees who are eligible for the mentorship program.

![Mentor](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/Mentorship.png)




## Summary

**How many roles will need to be filled as the "silver tsunami" begins to make an impact?**
- It is expected that 90,398 employees will likely retire soon. The number of roles that will need to be filled is dependent on how many employees actually retire. These roles will need to be filled as the "silver tsunami" begins to make an impact.

To get the number of positions that will be open in next four years I ran additional query that breaks down how many staff will retire per department. Since every department will be affected in some way this query gives more precise numbers what each department can expect and how many roles will need to be filled.
 
 ![Rolestofill](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/Rolestofill.png)


**Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?**

- Although there is a good representation of expected retirees across all departments, there are on average 59 mentees to every 1 mentor. Depending on departmental needs and position type, the mentor-mentee ratio may vary to ensure mentees are gaining the necessary knowledge, skills, experience, information, and advice.
- Based on the data we can conclude that there are not enough mentors to prepare the next generation of Pewlett Hackard employees.

![Qualified](https://github.com/awalindeep/Pewlett-Hackard-Analysis/blob/AwalinGHMAIN/Analysis%20Projects%20Folder/Pewlett-Hackard-Analysis%20Folder/Data/PNG/qualifiedstaff.png)

