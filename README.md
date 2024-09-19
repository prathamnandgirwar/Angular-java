Tech Stack
•	Frontend:Angular,Nodejs
•	Backend:Java-Springboot
•	Database:Mariadb
•	Cloud:AWS:ec2,s3,cloudfront,rds,route-53

Summary:
•	Launch 3 ec2 instances for Frontend,Backend, and Databases respectively
•	step 1:set up Database instance
•	step 2:set up Backend
•	step 3:set up Frontend

Installing MariaDB, Setting Password, and Importing Database on Ubuntu Linux
Create RDS Instance.

sudo apt update
sudo apt install mariadb-server
sudo systemctl start mariadb
sudo systemctl enable mariadb

 Take access of RDS.
 
sudo mysql -h database-1.ctce6osqiqv4.eu-west-1.rds.amazonaws.com -u admin –pPratham123

Create Database and give privileges to User.

CREATE DATABASE springbackend;
GRANT ALL PRIVILEGES ON springbackend.* TO 'username'@'localhost' IDENTIFIED BY 'your_password';
Put Schema into Database Which we created above.(Note :- keep springbackend.sql file at same place where we have use command)

Import Database from SQL File

sudo mysql  -h < your RDS endpoint > -u username -p springbackend < springbackend.sql
sudo mysql –h <ypur RDS endpoint > -u –p 

Check Database here.

show databases;
use springbackend;

Check Table here

show tables;
select * from tbl_workers;


You have to give your RDS endpoint, user and password in below file
Vim ./spring-backend/src/main/resources/application.properties

