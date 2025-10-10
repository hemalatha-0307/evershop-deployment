##### **# Task 4 Notes - Auto Scaling and Load Balancing**



###### **1. Created Launch Template: evershop-launch-template**

&nbsp;  - Ubuntu 22.04 LTS (t2.micro)

&nbsp;  - IAM Role: evershop-AutoScaleRole

&nbsp;  - AppTier Security Group attached



###### **2. Created Auto Scaling Group: evershop-AS**G

&nbsp;  - Minimum: 1, Maximum: 3, Desired: 1

&nbsp;  - Target tracking scaling policy configured



###### **3. AppTier Target Group attached to internal Load Balancer**

&nbsp;  - Health check: HTTP, port 80, path "/"

&nbsp;  - Initial instances: some draining/unhealthy, auto-healing



###### **4. Verified functionality**

&nbsp;  - Curl test from Ubuntu instance (internal LB) → app page displayed

&nbsp;  - Load Balancer DNS (Internet-facing) → e-commerce platform accessible

&nbsp;  - Free Tier compliant (t2.micro, max 3 instances)



