# Pewlett-Hackard-Analysis
## Module 7 - SQL

## Purpose of Module 7
In this module, we were introduced to Postgres SQL and pgAdmin with the goal of composing basic SQL statements to manipulate and display the tables of relational databases. Through the completion of this module, I am able to display the relational database through Entity Relationship Diagram, import  and export CSV datasets, create queries using the data and SQL statements, and troubleshoot errors along the way. 

## Overview of Assignment 
This assignment asked us to build an employee database for Pewlett Hackard with SQL. The goal of this database was to “future-proof” the company by determining how many employees are eligible to retire. Through a series of queries, we created and exported tables to display the retired employees and utilized SQL functions to sort the data further. 

## Resources
#### Data: 
The data for Module 7 comes from the following CSV files:
  
    -departments.csv
	-dept_emp.csv
	-dept_manager.csv
	-employees.csv
	-salaries.csv
	-titles.csv
#### Software used: 
	-pgAdmin 4 Version 6.1 
	-PostgreSQL 11.14 Version 6.0
#### Entity Relationship Diagram:  
The ERD was created through the following Quick DBD:
  
    - quickdatabasediagrams.com 
The ERD I created and used as reference throughout the module

<img width="575" alt="ERD" src="https://user-images.githubusercontent.com/92558842/144717327-ae57f8ca-c26b-4104-b2ea-8eac5e9ebbda.png">

	

## Pewlett-Hackard Results 
Through the module and challenge, we complied a series of tables displaying information that offers insight on the retirement wave the company is bound to face. In the module, we created the essential tables for the company, such as the **_emp_info.csv_** (a sample displayed below) which provides the company a list of all the current employees (to_date 01/01/9999) who were born between 01/01/1985 and 12/31/1988. 

<img width="605" alt="emp_info" src="https://user-images.githubusercontent.com/92558842/144717354-c08030da-6ebc-4f1e-bc67-991460dad888.png">

We were also able to provide information through the creation of queries and tables on managers who are eligible to retire. We can further provide the company with a list of who and how many employees are eligible to retire by department. 
In the challenge, we created two additional tables; one to display the most recent job title for employees eligible to retire and the total of  potential retirees per department and the second table to display the employees who are eligible to participate in the mentorship program the company is creating. 
### The Number of Retiring Employees by Title- Deliverable 1 
For this section of the challenge, we created queries to create the **_unique_titles.csv_** which holds all the unique titles of current employees born between 01/01/1952 and 12/31/1955. From the sample of the table below, we can see a list of each employee, their employee number, and title. 

<img width="468" alt="unique_titles" src="https://user-images.githubusercontent.com/92558842/144717369-3bbd63a6-923b-4639-b853-91b78a8cbacf.png">

Using the information from the **_unique_titles_** table, we utilized the following query to get the number of employees eligible to retire and grouped that count by their most recent job title. 

<img width="624" alt="retiring_titles_query" src="https://user-images.githubusercontent.com/92558842/144717377-b73cc12d-f503-493f-ab53-ae66995295a5.png">

From this, we created **_retiring_titles.csv_** which is displayed below:

<img width="212" alt="retiring_titles" src="https://user-images.githubusercontent.com/92558842/144717387-8e266012-4982-478d-b08a-63fabe8e23c0.png">

### The Employees eligible for the Mentorship Program  - Deliverable 2 
To complete deliverable 2, we had to use a series of joins and filters, displayed in the query below,  to create the **_mentorship_eligibilty.csv_** containing employees who are eligible to participate in the upcoming mentorship program. 

<img width="567" alt="mentorship_query" src="https://user-images.githubusercontent.com/92558842/144717405-4f445ce4-d7ab-4561-bb32-d10e8cb5e6a5.png">

From this, we receive a list of employees, their employee number, birthday, from and to employment dates, and their most recent title. A sample of this table is displayed below. 

<img width="721" alt="mentorship_eligibilty" src="https://user-images.githubusercontent.com/92558842/144717418-3525bd7c-0073-41e4-9da3-c43bd6daae43.png">

### Major Take-Aways from Analysis: 
1. The first deliverable requested that we make the **_retirement_titles_** table. Although this table is useful in giving us the 133,776 employees eligible to retire, it also includes employees who are no longer employed with the company, as we can see in the image below where employee number 10005, Maliniak’s last day was 12/09/1996. 
<img width="655" alt="retirement_table" src="https://user-images.githubusercontent.com/92558842/144717428-0195e38f-0c8c-41b7-b4b7-c65695767683.png">

2. After collecting the unique_titles table, we are able to see that there are 90,398 employees eligible to retire which suggests that 43,378 employees had a change in job title while employed with the company. This is good insight for the company as it suggests promotions or moving up within the company. 
3. Although the results include employees who no longer work with the company, we are able to see through the **_retiring_titles_** table that the Senior Engineer and Senior Staff departments can potentially lose 29,414 and 28,254 employees respectively if the employees choose to retire. The Engineer department can loose 14,222 employees, Staff- 12,243 employees, Technique Leader- 4,502 employees, Assistant Engineer 1,761 employees, and Management- 2 employees. That's 30.13% of Pewlett Hackard's total employees! 
4. From the second deliverable and the creation of the mentorship_eligibility table, we are able to see that there are 1,549 current employees who are eligible for the mentorship program. 
5. When ordering the **_mentorship_eligibility_** table by “from_date” or when the employee was hired, we can see from the table below that of those eligible, a large portion of the employees began working with the company in 1985- meaning their tenure has been 36 years. 

<img width="724" alt="mentorship_byhiredate" src="https://user-images.githubusercontent.com/92558842/144717453-e9901389-3fdf-4d5f-9c57-335376904746.png">
 This information is also very telling for the company as it indicates positive employee retention. 


## Summary

### How many roles will need to be filled as the “silver tsunami” begins to make an impact?
After altering the retiring titles query and table to include only those currently employed with the company, we can see that 72,458 employees are eligible to retire. We can not guarantee that amount of employees will retire as it is a personal choice and the company can not force people to retire, according to the Age Discrimination Amendments of 1986. Through the table below, we receive insight on how many potential employees can retire by their most recent job title. 

<img width="227" alt="retiring_titles_current" src="https://user-images.githubusercontent.com/92558842/144717460-57dc6f33-0fe3-4b1f-a882-4ccf27172615.png">

### Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett-Hackard employees?
After grouping current employees that are eligible for the mentorship program through the following query, displayed in the table below, we can see that only 1.68% of the Senior Staff department, 4.31% of the Engineer department, 3.99% of the Staff department, 1.13% of the Senior Engineer, 2.14% of the Technique Leader, 4.95% of the Assistant Engineer, and 0 Managers of the total potential retirees are eligible. With 167,666 current employees who are not eligible to retire, this indicates that there are not enough qualified employees to mentor the next generation of employees in the company. 

<img width="303" alt="mentorshipbytitle_query" src="https://user-images.githubusercontent.com/92558842/144717486-74994a01-09cf-474b-bb13-050c7337a6e2.png">

<img width="219" alt="mentorshipbytitle" src="https://user-images.githubusercontent.com/92558842/144717491-43b8d47c-b86a-4658-bb81-e774c22dd293.png">

We can also see through the following table the breakdown of current employees with the company by job title. 

<img width="214" alt="current_emp_bytitle" src="https://user-images.githubusercontent.com/92558842/144717482-73b0c677-a481-4fa7-b526-f54d0c87f92a.png">

The amount of employees for each title follow similar patterns to that of the retiring employees by title counts, indicating that the “silver tsunami” has the potential to occur again and a mentorship program should be implemented with each age group to prevent unprepared employees and a poor work environment. 
