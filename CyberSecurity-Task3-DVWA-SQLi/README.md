# Task 3 – DVWA SQL Injection

## Objective

To understand and demonstrate a basic SQL Injection vulnerability using Damn Vulnerable Web Application (DVWA) in a local Kali Linux virtual machine.

## Environment

- Operating System: Kali Linux
- Virtualization: Oracle VirtualBox
- Application: Damn Vulnerable Web Application (DVWA)
- Web Server: Nginx
- Database: MariaDB
- Vulnerability: SQL Injection
- DVWA Security Level: Low
- Testing Environment: Localhost only

## DVWA Setup

DVWA was installed and configured on a local Kali Linux virtual machine. The DVWA database was successfully created using the Database Setup page.

The application was accessed locally at:

`http://127.0.0.1:42001`

The DVWA security level was initially set to Impossible. It was changed to Low to demonstrate the SQL Injection vulnerability in the controlled lab environment.

## SQL Injection Test

First, the User ID field was tested with a normal value:

`1`

The application returned:

- ID: 1
- First name: admin
- Surname: admin

A SQL Injection test was then performed using:

`1' OR '1'='1`

Instead of returning only one user, the application returned multiple user records, including:

- admin
- Gordon Brown
- Hack Me
- Pablo Picasso
- Bob Smith

This demonstrates that the application is vulnerable to basic SQL Injection when operating at the Low security level.

## Security Impact

SQL Injection occurs when user input is directly incorporated into an SQL query without proper validation or parameterization.

An attacker may potentially use this vulnerability to:

- Access unauthorized database records
- Modify or delete database information
- Bypass application restrictions
- Extract sensitive information
- Potentially compromise the underlying application or database

## Prevention

SQL Injection vulnerabilities can be prevented by:

1. Using prepared statements and parameterized queries.
2. Validating and sanitizing user input.
3. Avoiding direct concatenation of user input into SQL queries.
4. Applying least-privilege permissions to database accounts.
5. Using secure coding practices and regular security testing.
6. Keeping web applications and database software updated.

## Evidence

The following screenshot demonstrates the successful SQL Injection test:

`task3-sqli-evidence.png`

The screenshot shows the injected input and multiple user records returned by the application.

## Ethical Considerations

All testing was performed against a deliberately vulnerable DVWA installation running locally inside a Kali Linux virtual machine.

No external, production, or unauthorized systems were targeted.

## Conclusion

The DVWA SQL Injection exercise demonstrated how unsafe handling of user input can allow an attacker to alter the intended SQL query and retrieve multiple database records.

The exercise also highlighted the importance of parameterized queries, input validation, least-privilege database access, and secure application development.
