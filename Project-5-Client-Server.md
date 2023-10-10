# **CLIENT-SERVER ARCHITECTURE WITH MYSQL**

## In this project, we demonstrated implementatation of client-server connection using Ubuntu instance.

## Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another.

## In their communication, each machine has its own role: the machine sending requests is usually referred as “Client” and the machine responding (serving) is called “Server”.

# Real example of LAMP website
## In Project 1, we implemented a LAMP STACK website.
## let us take an example of commercially deployed LAMP     website – *www.propitixhomes.com.*

![curl -Iv www.propitixhomes.com](images/curl-propitixhomes.com)

## Self Study 

1. Self study is requred to read about *ping* and *traceroute* network diagnostic utilities. This will allow us to be more familiar with the tools.

[Traceroute](https://en.wikipedia.org/wiki/Traceroute)

[Ping](https://en.wikipedia.org/wiki/Traceroute)

2. Refresh your knowledge of basic SQL commands, be able to perform simple **SHOW**, **CREATE**, **DROP**, **SELECT** and **INSERT SQL** queries.

[Basic my sql command](https://www.w3schools.com/sql/)
# IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

## A Client Server Architecture is implemented using MySQL Database Management System (DBMS).

## Find below steps taken to implement the project
1. ### Two Ubuntu Linux-based virtual servers (EC2 instances in AWS) was Created and configured.

2. ### On mysql server Linux Server I installed MySQL Server software using commands below:

- ## sudo apt install mysql-server

*run*
- **sudo apt updaate -y** 
- **sudo apt install mysql-server**

![sudo apt install mysql-server](images/Sudo-apt-install-mysql-server.PNG)

- ## sudo mysql_secure_installation
**sudo mysql_secure_installation**

![sudo mysql secure installation](images/sudo-mysql-secure-installation.PNG)

- ## sudo mysql

![run sudo mysql](images/sudo-mysql.PNG)

**CREATE USER 'remote_user'@'%'IDENTIFIED WITH mysql_native_password BY *'password'*;**
- ## Create REMOTE_USER to use mysql_native_password

- ## Create DATABASE *test_db*

**CREATE DATABASE test_db;**
- ## GRANT ALL ON *test_db*

**GRANT ALL ON test_db TO 'remote_user'@'%'WITH GRANT OPTION;**

- ## FLUSH PRIVILEGES

**FLUSH PRIVILEGES;**

[sudo CREATE USER](images/create-user-create-database-grant-privileges.PNG)
3. ## configure MySQL server to allow connections from remote hosts.
 Change **bind IP Address** for remote user to connect.

**sudo vi .etc/mysql/mysql.conf.d/mysqld.cnf**

![sudo CREATE USER](images/bind-address.PNG)

**sudo systemctl restart mysql**

4. ## sudo apt install mysql-client

*run*
- **sudo apt updaate -y** 
- **sudo apt install mysql-clien**

![sudo apt install mysql-client](images/sudo-apt-install-mysql-client.PNG)

## View client private IP adrress and add to exception address to access mysql sever through security group

5. ## connect to **database server** from client and login with password created.

![remote to server from client](images/sudo-mysql-u-remote-user-h-ipaddress-p.PNG)

## after successfully connected to the server then, we run below command to access the *database*.

**Show DATABASES;**

![remote to server from client](images/show-databases.PNG)

## In conclusion, we are able to successfully connect to the DB Server from Client and can equally view the database table.

*Thank you*