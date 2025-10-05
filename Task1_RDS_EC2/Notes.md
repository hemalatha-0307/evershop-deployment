#### **# Task 1 – RDS MySQL Setup and Connection from EC2**



###### **## Step 1: Create RDS MySQL Database**

\- Database Name: evershop-task1

\- Engine: MySQL 8.0

\- Instance Type: db.t3.micro

\- VPC: evershop-project-vpc

\- Subnet Group: evershop-db-subnet

\- Public Access: No

\- Security Group: RDSSG

\- Availability Zone: ap-south-1a

\- Purpose: Create a MySQL database inside our VPC for the Evershop project.

###### 

###### **## Step 2: Configure Security Group (RDSSG)**

\- Deleted default IP-based rule

\- Added inbound rule:

  - Type: MySQL/Aurora

  - Port: 3306

  - Source: AppTierSG (EC2 instance)

\- Purpose: This allows only the EC2 instance from AppTierSG to connect to the RDS database securely.



###### **## Step 3: Install MySQL Client on EC2**

\- Commands used:

    sudo apt update

    sudo apt install mysql-client -y

\- Purpose: Install the MySQL client so that EC2 can communicate with the RDS database.


###### **## Step 4: Connect to RDS from EC2**

\- Command:

    mysql -h evershop-task1.c18qiuusgpak.ap-south-1.rds.amazonaws.com -u admin1 -p

\- Enter the RDS password when prompted

\- Purpose: Test connection from EC2 to the RDS database, ensuring network and security group configuration is correct.



###### **## Step 5: Verify Database Operations**

\- Commands Used:

    SHOW DATABASES;

    CREATE DATABASE testdb;

    USE testdb;

    CREATE TABLE sample\_table (id INT PRIMARY KEY, name VARCHAR(20));

    INSERT INTO sample\_table VALUES (1, 'Hema');

    SELECT \* FROM sample\_table;

\- Purpose: Confirm that the database is working correctly by creating a test database and table, inserting data, and reading it successfully.

