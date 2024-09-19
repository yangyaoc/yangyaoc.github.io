# Apply filters to SQL queries

## Project description
My organization is working to make their system more secure. It is my job to ensure the system
is safe, investigate all potential security issues, and update employee computers as needed.
The following steps provide examples of how I used SQL with filters to perform
security-related tasks.

## Retrieve after hours failed login attempts
There was a potential security incident that occurred after business hours (after 18:00). All after
hours login attempts that failed need to be investigated.
The following code demonstrates how I created a SQL query to filter for failed login attempts
that occurred after business hours.

<img width="633" alt="Screenshot 2024-09-19 at 7 45 30 AM" src="https://github.com/user-attachments/assets/09fd12c3-c666-4bcb-ab3b-3609c1e20a2a">

The upper part of the screenshot is my query, and the lower part is a portion of the output.
This query filters for failed login attempts that occurred after 18:00. 
1) I started by selecting all data from the `log_in_attempts` table.
2) I used a `WHERE` clause with an `AND` operator
to filter my results to output only login attempts that occurred after 18:00 and were
unsuccessful.
<br>The first condition is `login_time > '18:00'`, which filters for the login
attempts that occurred after 18:00. The second condition is `success = FALSE`, which filters
for the failed login attempts.

## Retrieve login attempts on specific dates
An irregular event occurred on 2022-05-09. I need to investigate any login activity that happened on 2022-05-09
or on the day before.

The code below shows how I wrote a SQL query to filter for login attempts that
occurred on specific dates.
<img width="629" alt="Screenshot 2024-09-19 at 7 50 03 AM" src="https://github.com/user-attachments/assets/4d04bfc4-36fb-405d-895f-773f5c375d9a">

The upper part of the screenshot is my query, and the lower part is a portion of the output.
This query shows all login attempts that occurred on 2022-05-09 or 2022-05-08. 
1) I started by selecting all data from the `log_in_attempts table`.
2) Then, I used a `WHERE` clause with an `OR` operator to filter my results to output only login attempts that occurred on either
2022-05-09 or 2022-05-08.
<br>The first condition is `login_date = '2022-05-09'`, which filters for logins on 2022-05-09. The second condition is `login_date = '2022-05-08'`, which filters for logins on 2022-05-08.

## Retrieve login attempts outside of Mexico
After filtering the organization’s data on login attempts, I think there is an issue with the
login attempts that occurred outside of Mexico. These login attempts should be investigated.
The following code shows how I wrote a SQL query to filter for login attempts which
occurred outside of Mexico.

<img width="623" alt="Screenshot 2024-09-19 at 7 57 34 AM" src="https://github.com/user-attachments/assets/7f22a85c-8051-45fa-ace7-c3a6f4dc7cc2">

The upper part of the screenshot is my query, and the lower part is a part of the output.
This query shows all login attempts that occurred in countries that are not Mexico. 
1) I started by selecting all data from the `log_in_attempts` table.
2) I used a `WHERE` clause with `NOT` to filter for countries other than Mexico. I used `LIKE` with `MEX%` as the pattern to
match because the dataset represents Mexico as `MEX` and `MEXICO`. The percentage sign (`%`)
represents any number of unspecified characters when used with `LIKE`.

## Retrieve employees in Marketing
My team wants to update the computers for certain employees in the Marketing department.
To do this, I have to get information on which employee machines to update.
The following code demonstrates how I created a SQL query to filter for employee machines
from employees in the Marketing department in the East building.

<img width="639" alt="Screenshot 2024-09-19 at 8 08 25 AM" src="https://github.com/user-attachments/assets/471f88f2-5567-4767-81c5-d15153c5c534">

The upper part of the screenshot is my query, and the lower part is a portion of the output.
This query shows all employees in the Marketing department in the East building.

1)I started by selecting all data from the `employees` table. 
2)I used a `WHERE` clause with `AND` to filter for employees who work in the Marketing department and in the East building. I used
`LIKE` with `East%` as the pattern to match because the data in the `office` column represents
the East building with the specific office number. 
<br>The first condition is the `department ='Marketing'` portion, which filters for employees in the Marketing department. The second
condition is the `office LIKE 'East%'` portion, which filters for employees in the East
building.

## Summary
There are two tables I used, `log_in_attempts` and `employees`. I also used the `AND`,
`OR`, and `NOT` operators to filter for specific task. To find patterns, I used `LIKE` and the percentage sign (`%`) wildcard. 
