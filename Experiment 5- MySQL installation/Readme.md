## AIM: Installation of Mysql in Ubuntu.
 
 ### 1.1 OBJECTIVE:
 
 MySQL is a fast, easy to use relational database. It is currently the most popular opensource database. It is very commonly used in conjunction with PHP scripts to create 
powerful and dynamic server-side applications.

MySQL is used for many small and big businesses. It is developed, marketed and 
supported by MySQL AB, a Swedish company. It is written in C and C++.

### Relational Database Management System (RDBMS): 
MySQL is a relational database management system.

- Easy to use: MySQL is easy to use. You have to get only the basic knowledge of 
SQL. You can build and interact with MySQL with only a few simple SQL 
statements.
- It is secure: MySQL consist of a solid data security layer that protects sensitive 
data from intruders. Passwords are encrypted in MySQL.
-  Client/ Server Architecture: MySQL follows a client /server architecture. There is a 
database server (MySQL) and arbitrarily many clients (application programs), 
which communicate with the server; that is, they query data, save changes, etc.
- Free to download: MySQL is free to use and you can download it from MySQL 
official website.
- It is scalable: MySQL can handle almost any amount of data, up to as much as 50 
million rows or more. The default file size limit is about 4 GB. However, you can 
increase this number to a theoretical limit of 8 TB of data.
Installation of Mysql. In this week you will learn creating databases. How to create table,
altering the database, dropping table and databases if not required. You will also try 
truncate, rename commands etc…
 

### 1.2 RESOURCE:

Ubuntu (Linux) / My Sql database

### 1.3 PROCEDURE:

#### Installation of MySql:

Follow these steps on to install MySql in Ubuntu:

1. Open Terminal and run below command.

``` 
sudo apt-get install mysql-server
```
2. Give the root password.

3. Wait for the installation to finish.

4. The installer itself start the MySql server. To check whether MySql server is running or not, run 
below command.

```
sudo netstat-tap | grep mysql
```

5. To make sure. Your MySql installation works fine with Apache and PHP, run below command. 
It will install necessary modules to connect to a MySql database through PHP using Apache.
```
sudo apt-get install libapache2-mod-auth-mysql php5-mysql 
```

6. Installation is completed.

#### SQL
- SQL stands for Structured Query Language. It is used for storing and managing data in 
relational database management system (RDMS).
- It is a standard language for Relational Database System. It enables a user to create, 
read, update and delete relational databases and tables.
- All the RDBMS like MySQL, Informix, Oracle, MS Access and SQL Server use SQL 
as their standard database language.
