
# **IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).**

## This to demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS)

### Step 1

Created and configured two Linux-based virtual servers (EC2 instances in AWS). and named them as below:
- Server A name - `MySQL Server`
- Server B name - `MySQL Client`


### Step 2

Installed the mysql server using the below code:

`sudo apt mysql_server`

![screenshot](https://github.com/Tofumy/Tofumy-PBL5/blob/main/install-mysqlserver.PNG)

`sudo mysql_secure_installation`

![screenshot](https://github.com/Tofumy/Tofumy-PBL5/blob/main/sudo-mysql-secure-installation.PNG)

Then used the below to confirm mysql has been installed well on the server:

`sudo mysql`

![screenshot](https://github.com/Tofumy/Tofumy-PBL5/blob/main/sudo-mysql.PNG)



On mysql client Linux Server install MySQL Client software

`sudo apt install mysql-client`

![screenshot](https://github.com/Tofumy/Tofumy-PBL5/blob/main/install-mysqlserver.PNG)
