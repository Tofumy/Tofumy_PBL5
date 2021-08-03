
# **IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).**

## This to demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS)

### Step 1

Created and configured two Linux-based virtual servers (EC2 instances in AWS). and named them as below:
- Server A name - `MySQL Server`
- Server B name - `MySQL Client`


### Step 2

Installed the mysql server using the below code:

`sudo apt mysql_server`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/install-mysqlserver.png)

`sudo mysql_secure_installation`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/sudo-mysql-secure-installation.png)

Then used the below to confirm mysql has been installed well on the server:

`sudo mysql`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/sudo-mysql.png)


On mysql client Linux Server install MySQL Client software

`sudo apt install mysql-client`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/install-mysqlclient.png)


Created an inbound rule in the MySQL Server EC2 instance to allow only the Private IP address of the MySQL client to connect

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/inboundrule.PNG)


On the EC2 instance where we have MySQL server installed, we created a DB user and a DATABASE and then granted full permission for the user on the DB

``` mysql

CREATE USER 'db-user'@'%' IDENTIFIED WITH mysql_native_password BY '@Password18';

CREATE DATABASE Test_DB2;

GRANT ALL ON Test_DB2.* TO 'db-user'@'%' WITH GRANT OPTION;

```

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/mysql-creation.PNG)


We then configured MySQL server to allow connections from remote hosts:

`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

We then changed the binding address in the config file from ext ‘127.0.0.1’ to ‘0.0.0.0’ ext

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/binding-change.PNG)



From the EC2 instance where we have the mysql client installed we then try to connect to the MySQL server using the below:

`mysql -u db-user -h 172.31.14.6 -p`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/login-success.PNG)

We then ran to confirm we are seeing the DATABASE:

`SHOW DATABASES;`

![screenshot](https://github.com/Tofumy/Tofumy_PBL5/blob/main/show-db.PNG)
