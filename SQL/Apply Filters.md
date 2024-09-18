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

The first part of the screenshot is my query, and the second part is a portion of the output.
This query filters for failed login attempts that occurred after 18:00. First, I started by selecting
all data from the `log_in_attempts` table. Then, I used a `WHERE` clause with an `AND` operator
to filter my results to output only login attempts that occurred after 18:00 and were
unsuccessful. The first condition is `login_time > '18:00'`, which filters for the login
attempts that occurred after 18:00. The second condition is `success = FALSE`, which filters
for the failed login attempts.

## Retrieve login attempts on specific dates
An irregular event occurred on 2022-05-09. I need to investigate any login activity that happened on 2022-05-09
or on the day before.

The code below shows how I wrote a SQL query to filter for login attempts that
occurred on specific dates.
<img width="629" alt="Screenshot 2024-09-19 at 7 50 03 AM" src="https://github.com/user-attachments/assets/4d04bfc4-36fb-405d-895f-773f5c375d9a">

The upper part of the screenshot is my query, and the lower part is a portion of the output.
This query shows all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I
started by selecting all data from the `log_in_attempts table`. Then, I used a `WHERE` clause
with an `OR` operator to filter my results to output only login attempts that occurred on either
2022-05-09 or 2022-05-08. The first condition is `login_date = '2022-05-09'`, which
filters for logins on 2022-05-09. The second condition is `login_date = '2022-05-08'`,
which filters for logins on 2022-05-08.

