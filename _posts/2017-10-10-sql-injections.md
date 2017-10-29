---
layout: post
title: "Introduction To Defensive Databasing"
date: 2017-10-10T07:52:43-07:00
author: RetroMe
summary: >
  Introduction To Defensive Databasing is a two hour course focused on
  developing the skills necessary to understand best practices for protecting
  again SQL injection as well as other database related vulnerabilities.
categories: computers
thumbnail: fa-desktop
tags:
 - software
 - attacks
 - exploits
 - best practices
 - phoenix linux users group
 - SQL
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify the five most popular data base engines.
2. Identify two ways that data base engines can differ.
3. Identify what SQL injection is.
4. Identify one tool used in PHP to prevent SQL injection.
5. Identify an organization that teaches about SQL injection.

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/y2_aWjLpsbs"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject" }
</div>

## Introduction

Many modern breaches involve databases. We regularly hear about leaks, vulnerable software, and companies who were not following best practices being hit by such a basic hack. Why? What kind of software is being written that includes SQLi vulnerabilities?

A Small List from 2017 -

1. [WordPress Plugins (300,000+ sites)](http://archive.is/r51QA)
2. [Illinois State Board Of Elections (Voter Registration System)](http://archive.is/HJW0Z)
3. [Joomla](http://archive.is/DgzTR)
4. [Web Forums (65000+ Accounts at an Airsoft site alone)](http://archive.is/Yqxb5)
5. [Moodle](http://archive.is/SUu4g)
6. [McAfee ePolicy Admin Console](http://archive.is/0c787)
7. [US Election Commision Voting Machines](http://archive.is/5qrcA)

Also check out [the wall of shame](http://codecurmudgeon.com/wp/sql-injection-hall-of-shame/) for
more interesting mistakes.

## Servers

The most popular SQL servers are -

1. [Oracle](https://www.oracle.com/database/index.html)
2. [MySQL or MariaDB](https://mariadb.org/)
3. [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016)
4. [PostgreSQL](https://www.postgresql.org/)
5. [IBM DB2](https://www.ibm.com/analytics/us/en/db2/)

It is very important that you figure out which server is being employed by your
target. This should be one of your top goals as you begin the process of
executing an attack. Each server will have both minor as well as major
differences in syntax and function that will require specific changes in
behavior when attempting to exploit flaws. We must also keep in mind
some of the differences in license we can run into as well.

## Risks

SQL injection is a code technique that can be used to cause unwanted
behavior in your application. Some of the results of an SQL injection attack
include the following -

1. Destruction of data.
2. Breach of privacy.
3. Access control loss.

## Avoidance

Avoiding SQL injection is often possible through the use of one or more
methods. Each of these methods will require some effort by the programmer
working on the application. It should be understood however that many modern
frameworks now provide many of these tools as baked in tools. While it is
possible to simply pass a raw SQL query without any form of parameterization,
it can now require more effort to do it wrong than right.

A [cheat sheet](https://www.owasp.org/index.php/SQL_Injection_Prevention_Cheat_Sheet)
is available for anyone interested in learning more about SQL injection. The 
[Open Web Application Security Project](https://www.owasp.org/index.php/Main_Page)
is a great tool for learning about cyber security.

### Parameterized Queries

A prepared statement with parameterized queries allows the developer to bind a
variable. You must first define your SQL code and then you pass in each
parameter later. Even if a user were to try to inject 'userid = tom; or 1=1'
then the query will see a literal string and look instead for the userid of
'tom' or '1=1' as a string. It prevents interpretation of input by the
database.

#### PHP Example of Prepared Statement

```
// prepare and bind
$stmt = $conn->prepare("INSERT INTO MyGuests (firstname, lastname, email) VALUES (?, ?, ?)");
$stmt->bind_param("sss", $firstname, $lastname, $email);

// set parameters and execute
$firstname = "John";
$lastname = "Doe";
$email = "john@example.com";
$stmt->execute();
```

### Stored Procedures

A stored procedue is an alternative to prepared statements. A user would store
an SQL query in the database, call it, and then pass a variable to it before
execution. You are setting the SQL query and not making any changes beyond
passing a variable.

### White List Input Validation

You can white list certain variables like table names or column names, however,
if you are using a white list, there is a good chance you should be able to
rewrite your code to not need it. You should not be allowing a user to pass a
table name, column name, or other database related information from input.

### Escaping

Escaping content, such as replacing all single quotes with double quotes is an
iffy proposition and not recommended as a replacement for prepared statements.
You should perform some form of input validation, provide a whitelist of
acceptable content, and never use string concantentation. This is not
replacement for prepared statements or stored procedures.

### Least Privilege

Do not allow your application to connect to your database using the root user.
Least privilege includes user rights, resource permissions, and privilege
elevation mitigation. You should carefully map out your application and
understand what rights and tools are necessary and then only white list those
aspects of the application. If your middleware only needs access to a single
database, then it should only have access to that single database and no more.

You must pay attention to what is used and what is necessary to prevent a
system or aspect of the application possibly becoming a vector to intrusion.

## Code Review

Review your code. Peer review, automted or tool assisted review, or pair
programming are all viable methods to get more eyes on code. Each of these
options increases the development time, but when properly implemented, will
greatly reduce the amount of time spent on trying to fix code after it has
already been deployed.

## Testing

Automated testing is far superior to manual inspection.

Tools include N-Stealth, Web Vulnerability Scanner, SPI Web Inspect, and Nikto.
These are just a handful of tools that can be used to automate the testing of
your application. It is also possible to create a testing path that is used in
conjunction with continous integration to automatically monitor for
vulnerabilities every time you push the application an update.

1. [N-Stealth](https://www.nstalker.com/products/editions/free/)
2. [Nikto](https://github.com/sullo/nikto)
3. [Web Inspect](http://searchsecurity.techtarget.com/magazineContent/SPI-Dynamics-WebInspect-61-Product-Review)
4. [CI](http://archive.is/Ym0fT)

## Answers

1. Oracle, MySQL, Microsoft SQL, PostreSQL, and IBM DB2 are the five most
   popular data base engines.

2. Query Syntax and Stored Function/Procs Language Choice are two ways they
   differ.

3. SQL Injection is the result of running unvalidated SQL queries through an
   application by the use of exploits or with the help of poorly designed
   interfaces.

4. Prepared statements or parameterized queries can help defend against SQL
   injection.

5. OWASP ( Open Web Application Security Project )

## Conclusion

Breaches happen to the best prepared. It is inevitable that someone could
potentially find some kind of vulnerability in your application or project. It
is not an excuse or a blessing that allows a developer to ignore best
practices. You must develop your software in the most secure method possible
while using all the tools available to mitigate the threat. You should not
ignore security just because it is an up hill battle.

## Final Recommendations

1. Use Linux! 

2. Review code and foster a positive environment for improvement. No bruised egos.

3. Set metrics and perform testing. Example: Reduce calls for service by 12%.

4. Encourage all team members to think security.

5. Perform automated security reviews. Consider creating a CI toolset.

## Glossary

1. SQL - Structured Query Language. A language for interacting with relational
   databases

2. MariaDB - An open source tool that fulfills the same functionality of MySQL.

3. CI - Continous Integration. The practice of integrating code into a shared
   repository several times a day.
