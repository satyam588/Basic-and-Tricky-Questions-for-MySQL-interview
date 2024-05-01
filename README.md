# Basic-and-Tricky-Questions-for-MySQL-interview


#How to get second highest data in column ? 
# 1st Approach
SELECT * FROM employee ORDER by salary DESC LIMIT 1,1;

# 2nd Approach
SELECT * FROM employee ORDER by salary DESC LIMIT 1 offset 1;

#How to get mysql server current timezone ?
select @@system_time_zone;

# Write SQL Query to find duplicate rows in a database
select *, count(*) as duplicate from employee group by salary having duplicate > 1;

# How to append strings in select statements ?
# Basic
select *, CONCAT('Department ', department) as appended_department FROM employee;

#Complex
SELECT id,
	CASE
		WHEN gender = 'Male' THEN CONCAT(first_name, ' Mr.')
        WHEN gender = 'Female' THEN CONCAT('Miss ', first_name)
	ELSE 
		first_name
	END as first_name, last_name, email, gender, salary, department
FROM employee;

# How can you find 10 employees with Odd number as Employee ID?
SELECT * FROM employee where MOD(id, 2) = 1 LIMIT 10;


