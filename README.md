# File-Permissions-in-Linux
<h1>File Permissions in Linux</h1>

<h2>Description</h2>
This is a project that I completed regarding File permissions in Linux. The scenerio is based on a fictional company and was completed within a shell environment.
The research team at my organization needs to update the file permissions for certain files and directories within the <em>projects</em> directory. 
The permissions do not currently reflect the level of
authorization that should be given. Checking and updating these permissions will help keep
their system secure. To complete this task, I performed the following tasks:

<br />

<h2>Scenerio</h2>

In this scenerio, I am security professional at a large organization. I mainly work with their research team. Part of my job is to ensure users 
on tis team are authorized with the appropriate permissions.

I am tasked with examining existing permissions on the file system. I will need to determine if the permissions match the authorization 
that should be given. If they do not match, you'll need to modify the permisions to authorize the appropriate users and remove 
any unauthorized access

<p >
<h3> Retrieve after hours failed login attempts</h3>
There was a potential security incident that occurred after business hours (after 18:00). All 
after hours login attempts that failed need to be investigated.

The following code demonstrates how I created a SQL query to filter for a failed login attempts
that occurrred after business hours.
  
<br align="center"/>
<img src="https://imgur.com/OzDVrcM.png" height="80%" width="80%" alt="Control Categories"/>
<br />

The first part of the screenshot is my query and the second part is a portion of the output.
This query filters for failed login attempts that occcurred after 18:00. First, I start 
by selecting all data from the <em> log_in_attempts </em> table. Then, I used a <em> WHERE </em> clause with an <em> AND </em> operator
to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition
is <em> login_time > '18:00' </em>, which filters for the login attempts that occurred after 18:00. The second condition
is <em> success = FALSE </em>, which filters for the failed login attempts.
 
<h3> Retrieve login attempts on specific dates</h3>
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022--05-09 
or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filters for login attempts that 
occurred on specific dates.

<img src="https://imgur.com/kMMW0o6.png" height="80%" width="80%" alt="summery Audit Scope and Goals"/>
<br />

The first part of the screenshot is my query, and the second part is a portion of the output.
This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I 
started by selecting all data from the <em> log_in_attempts </em> table. Then, I used a <em> WHERE </em> clause
with an <em> OR </em> operator to filter my results to output only login attempts that occurred on either
2022-05-09 or 2022-05-08. The first condition is <em> login_date  = '2022-05-09'</em>, which
filters for logins on 2022-05-09. The second condition is <em>login_date = '2022-05-08'</em>,
which filters for logins on 2022-05-08.

<br />

<h3>Retrieve login attempts outside of Mexico</h3>

After investigating the organization’s data on login attempts, I believe there is an issue with the
login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that
occurred outside of Mexico

<br/>
<img src="https://imgur.com/AQkZsi4.png" height="80%" width="80%" alt="Control Categories"/>
<br />

The first part of the screenshot is my query, and the second part is a portion of the output.
This query returns all login attempts that occurred in countries other than Mexico. First, I
started by selecting all data from the <em>log_in_attempts</em> table. Then, I used a <em>WHERE</em> clause
with <em>NOT</em> to filter for countries other than Mexico. I used <em>LIKE</em> with <em>MEX%</em> as the pattern to
match because the dataset represents Mexico as MEX and MEXICO. The percentage sign <em>(%)</em>
represents any number of unspecified characters when used with <em>LIKE</em>.


<br />

<h3>Retrieve employees in Marketing</h3>

My team wants to update the computers for certain employees in the Marketing department.
To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines
from employees in the Marketing department in the East building.

<br/>
<img src="https://imgur.com/JD4kEya.png" height="80%" width="80%" alt="Compliance Checklist choices"/>
<br />

The first part of the screenshot is my query, and the second part is a portion of the output.
This query returns all employees in the Marketing department in the East building. First, I
started by selecting all data from the <em>employees</em> table. Then, I used a <em>WHERE</em> clause with <em>AND</em>
to filter for employees who work in the Marketing department and in the East building. I used
<em>LIKE</em> with <em>East%</em> as the pattern to match because the data in the <em>office</em> column represents
the East building with the specific office number. The first condition is the <em>department =
'Marketing'</em> portion, which filters for employees in the Marketing department. The second
condition is the <em>office LIKE 'East%'</em> portion, which filters for employees in the East
building.

<br />

<h3>Retrieve employees in Finance or Sales</h3>

The machines for employees in the Finance and Sales departments also need to be updated.
Since a different security update is needed, I have to get information on employees only from
these two departments.
The following code demonstrates how I created a SQL query to filter for employee machines
from employees in the Finance or Sales departments.

<br/>
<img src="https://imgur.com/fJISnIs.png" height="80%" width="80%" alt="Risk Assessment"/>
<br />

The first part of the screenshot is my query, and the second part is a portion of the output.
This query returns all employees in the Finance and Sales departments. First, I started by
selecting all data from the <em>employees</em> table. Then, I used a <em>WHERE</em> clause with <em>OR</em> to filter for
employees who are in the Finance and Sales departments. I used the <em>OR</em> operator instead of
<em>AND</em> because I want all employees who are in either department. The first condition is
<em>department = 'Finance'</em>, which filters for employees from the Finance department. The
second condition is <em>department = 'Sales'</em>, which filters for employees from the Sales
department.

<br />

<h3>Retrieve all employees not in IT</h3>

My team needs to make one more security update on employees who are not in the
Information Technology department. To make the update, I first have to get information on
these employees.

The following demonstrates how I created a SQL query to filter for employee machines from
employees not in the Information Technology department.

<br/>
<img src="https://imgur.com/n673u8R.png" height="80%" width="80%" alt="Risk Assessment"/>
<br />

The first part of the screenshot is my query, and the second part is a portion of the output. The
query returns all employees not in the Information Technology department. First, I started by
selecting all data from the <em>employees</em> table. Then, I used a <em>WHERE</em> clause with <em>NOT</em> to filter for
employees not in this department

<br />

<h3>Summary</h3>

I applied filters to SQL queries to get specific information on login attempts and employee
machines. I used two different tables, <em>log_in_attempts</em> and <em>employees</em>. I used the <em>AND</em>,
<em>OR</em>, and <em>NOT</em> operators to filter for the specific information needed for each task. I also used
LIKE and the percentage sign <em>(%)</em> wildcard to filter for patterns
