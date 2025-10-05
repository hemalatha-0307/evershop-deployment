#### **# Task 2 – Evershop Deployment on EC2**





###### **## Step 1: EC2 Web Server Setup**

&nbsp;- Connected to the Web Server EC2 instance via SSH:

&nbsp;     *ssh -i <keyfile.pem> ubuntu13.233.173.114*

      *sudo su*

&nbsp;- Purpose: Prepare the instance for Evershop deployment.





###### **## Step 2: Docker Container Deployment**

&nbsp;- Started Docker containers for the application and PostgreSQL database.

&nbsp;- Verified container status with:

&nbsp;     *docker ps*

&nbsp;- Purpose: Ensure both app and database containers are running correctly.





###### **## Step 3: Port Configuration and Accessibility**

&nbsp;- Configured app container to forward internal port 3000 to external port 80.

&nbsp;- Ensured WebTier security group allows inbound rules such as:
     Type: HTTP, TCP, Port: 80, Source: Internet (0.0.0.0/0)

&nbsp;    Type: HTTP, TCP, Port: 80, Source: Internet-facing LB security group

&nbsp;- Verified Evershop application is accessible via the EC2 public IP:

&nbsp;    *http://13.233.173.114*

&nbsp;- Purpose: Allow access to the Evershop web application from the internet and load balancer.

###### 

&nbsp;                        
**## Step 4: Database Verification**
---

&nbsp;- Accessed PostgreSQL container and confirmed schema with:

&nbsp;    *sudo docker exec -it task2\_evershop\_app\_database\_1 psql -U postgres*

     *\\dt*

&nbsp;- Purpose: Ensure the database tables are present and correctly configured for the application.





###### **## Step 5: Validation of Deployment**

&nbsp;- Verified that:

&nbsp;    Web application runs successfully on the public IP.

&nbsp;    Application communicates with PostgreSQL container without errors.

&nbsp;    All required ports and security groups are correctly configured.

