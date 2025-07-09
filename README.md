# Cybersecurity SQL Investigations Portfolio
SQL queries for investigating cybersecurity login events and employee data.

## Project Description
As part of my cybersecurity training, I used SQL queries to investigate potential security issues by filtering data from an organization's login and employee records. I focused on identifying suspicious login behavior and narrowing down employees for device updates based on department and location. This project demonstrates my ability to use AND, OR, NOT, and LIKE operators to analyze data, a critical skill for threat detection and incident response.

## Retrieve After Hours Failed Login Attempts
To identify failed login attempts made outside of normal business hours (after 6:00 PM), I used the following SQL query:

<pre> SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = FALSE; <pre>


# Cybersecurity SQL Investigations Portfolio

This query helped locate users who failed to log in after hours, which could indicate attempted unauthorized access.

## Retrieve Login Attempts on Specific Dates
To investigate login activity around a suspicious event, I queried login attempts made on May 8 and May 9, 2022:

SELECT * 
FROM log_in_attempts 
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';

This allowed me to isolate activity for dates of interest in the security investigation.

## Retrieve Login Attempts Outside of Mexico
To exclude login attempts that originated in Mexico (including values like 'MEX' or 'MEXICO'), I used:

SELECT * 
FROM log_in_attempts 
WHERE NOT country LIKE 'MEX%';

This filter identified logins that may have come from foreign or unrecognized locations.

## Retrieve Employees in Marketing
To locate employees in the Marketing department who work in any office located in the East building, I used:

SELECT * 
FROM employees 
WHERE department = 'Marketing' AND office LIKE 'East%';

This helped identify users whose devices required specific updates in that department and building.

## Retrieve Employees in Finance or Sales
For a scheduled computer update, I retrieved employees from either the Finance or Sales department using:

SELECT * 
FROM employees 
WHERE department = 'Finance' OR department = 'Sales';

This ensured that only relevant departments were included in the maintenance task.

## Retrieve All Employees Not in IT
To check employees whose devices still needed updates (excluding IT, which was already completed), I used:

SELECT * 
FROM employees 
WHERE NOT department = 'Information Technology';

This helped focus efforts on departments that hadn’t been updated yet.

## Summary
This project demonstrated my ability to filter and analyze data using SQL, a key part of a cybersecurity analyst's toolkit. I used logical operators (AND, OR, NOT) and pattern matching (LIKE) to retrieve targeted data from login and employee records. These skills are vital for investigating incidents, isolating threats, and managing assets effectively across departments.

Screenshots
![Exemplar-Filter-with-AND-OR-and-NOT-No1](https://github.com/user-attachments/assets/504af46b-88b2-48b3-8ea1-dc95c897d766)
![Exemplar-Filter-with-AND-OR-and-NOT-No2](https://github.com/user-attachments/assets/2fe4b591-c6b3-4bdb-a83c-af1fd2b72fc2)
![Exemplar-Filter-with-AND-OR-and-NOT-No3](https://github.com/user-attachments/assets/24601c74-eced-4092-aafb-697bd16b8666)
![Exemplar-Filter-with-AND-OR-and-NOT-No4](https://github.com/user-attachments/assets/bacabf85-fe94-4d0e-a5fa-f1d41aeb575f)
![Exemplar-Filter-with-AND-OR-and-NOT-No5](https://github.com/user-attachments/assets/3bc74daa-b85f-47e5-85db-3aefb2fba4bb)
![Exemplar-Filter-with-AND-OR-and-NOT-No6](https://github.com/user-attachments/assets/a060d9ad-9c0d-4e52-bc0b-f5ed9e3ab761)
