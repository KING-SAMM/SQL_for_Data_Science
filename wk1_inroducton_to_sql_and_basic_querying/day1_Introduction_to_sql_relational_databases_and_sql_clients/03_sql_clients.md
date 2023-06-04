### Lesson 3 
# SQL Clients

## What are SQL clients?

SQL clients are software applications used to access and manage data in SQL databases. These clients provide a user-friendly interface for interacting with the database, executing SQL queries, and performing various database-related tasks.

## Popular SQL clients: 
    - MySQL Workbench, 
    - SQL Server Management Studio, 
    - PostgreSQL.

**a. MySQL Workbench**: MySQL Workbench is a visual database design tool and SQL client that enables users to manage, develop, and maintain MySQL databases. It is a cross-platform application that provides a graphical user interface for creating and managing databases, designing database schema, and executing SQL queries.

**b. SQL Server Management Studio**: SQL Server Management Studio (SSMS) is a Windows-based integrated development environment (IDE) for managing and administering SQL Server databases. It provides a comprehensive set of tools for creating, deploying, and monitoring databases, as well as debugging and tuning SQL queries.

**c. PostgreSQL**: PostgreSQL is a popular open-source relational database management system (RDBMS) that provides robust support for SQL. It is known for its reliability, scalability, and extensibility. There are several SQL clients available for PostgreSQL, including pgAdmin, DBeaver, and Navicat.

## Installing and configuring an SQL client.

***a. MySQL Workbench***: To install MySQL Workbench, [visit the MySQL website](https://dev.mysql.com/downloads/workbench/) and download the appropriate installer for your operating system. 

![MySQL Workbench download page](https://sqlfordatascience.com.ng/img/week1/mysql-workbench-download-page-md.png "MySQL Workbench download page") 

Follow the on-screen instructions to install the software. After installation, launch MySQL Workbench and configure a new connection by providing the necessary database credentials.

***b. SQL Server Management Studio***: SQL Server Management Studio is typically installed as part of the SQL Server installation process. If you do not have SQL Server installed, you can download SQL Server Management Studio separately from the Microsoft website. Once installed, launch SSMS and connect to a SQL Server instance by providing the server name and authentication details.

***c. PostgreSQL***: To install PostgreSQL, visit the PostgreSQL website and download the appropriate installer for your operating system. Follow the on-screen instructions to install the software. After installation, launch your preferred SQL client and configure a new connection by providing the necessary database credentials.

## Connecting to a database.

***a. MySQL Workbench***: To connect to a MySQL database with MySQL Workbench, launch the software and select "New Connection" from the "Database" menu. Enter the necessary database credentials, including the host name, port number, username, and password. Click "Test Connection" to ensure that the connection is successful, then click "OK" to save the connection details.

***via MySQL Commandline Client***: This CLI tool comes with the MySQL package when downloading and installing MySQL Server and Workbench. Search for it in the searchbox or start menu and launch it from there.

![MySQL Commandline Client](https://sqlfordatascience.com.ng/img/week1/mysql-clclient.png "MySQL Coomandline Client")

It opens with a prompt to enter a password. Provide the password you set while configuring MySQL Workbench and you will get a welcome message.

![MySQL Commandline Client welcome message](https://sqlfordatascience.com.ng/img/week1/mysql-clclient-welcome.png "MySQL Coomandline Client welcome message")

***Via MySQL Shell***This CLI tool comes with the MySQL package when downloading and installing MySQL Server and Workbench. It works and looks similar to MySQL Commandline Client with minor differences. Search for it in the searchbox or start menu and launch it from there.

![MySQL Shell welcome message](https://sqlfordatascience.com.ng/img/week1/mysql-shell-welcome.png "MySQL Shell welcome message")

Type ```\status``` to get the MySQL Shell version and connection status, which should be "Not Connected".

![MySQL Shell sql mode](https://sqlfordatascience.com.ng/img/week1/mysql-shell-sql.png "MySQL Shell mode")

By default the shell is in JS (JavaScript mode). Switch to SQL mode by typing ```\sql```.

![MySQL Shell connect to database](https://sqlfordatascience.com.ng/img/week1/mysql-shell-connect.png "MySQL Shell connect to database")

Connect to MySQL server by using the format: \connect username@servername:port:
```sql
\connect root@localhost:3308
```
and provide the password

***b. SQL Server Management Studio***: To connect to a SQL Server database with SSMS, launch the software and select "Connect" from the "Object Explorer" pane. Enter the necessary server and authentication details, including the server name, authentication method, username, and password. Click "Connect" to establish the connection.

***c. PostgreSQL***: To connect to a PostgreSQL database with your SQL client, launch the software and select "New Connection" or "New Query" from the file menu. Enter the necessary database credentials, including the host name, port number, username, and password. Click "Test Connection" to ensure that the connection is successful, then click "OK" to save the connection details.

|[< 2. Relational Databases](02_relational_databases.md)  |           | [4. Basic SQL Syntax >](04_basic_sql_syntax.md)|
|:-------------------------------------------------------:|:---------:|:----------------------------------------------:|