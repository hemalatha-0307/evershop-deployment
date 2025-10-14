##### **# Task 5 – Configure Route 53 with Custom Domain and SSL (ACM)**



##### **\*\*Domain Name:\*\* evershopintern.com**



###### **## Objective**

Configure a custom domain for the e-commerce application, enable secure HTTPS traffic using an SSL certificate, and ensure that all traffic is properly routed to the application hosted on AWS.





##### **## Steps Completed**



###### **### 1. Domain Setup**

\- A custom domain `evershopintern.com` was used for the application.

\- DNS management was configured using \*\*AWS Route 53\*\*, and a hosted zone was created for the domain.



###### **### 2. Requesting SSL Certificate (ACM)**

\- Navigated to \*\*AWS Certificate Manager (ACM)\*\*.

\- Requested a \*\*Public Certificate\*\* for the domain and `www.evershopintern.com`.

\- Selected \*\*DNS validation\*\* method.

\- Chose \*\*Disable Export\*\* for the private key (standard for AWS services).

\- Completed the validation process to issue the certificate.



###### **### 3. Certificate Issuance**

\- The ACM certificate was successfully issued and is ready for attachment to AWS services.



###### **### 4. Attaching SSL to Application Load Balancer**

\- Configured the \*\*Application Load Balancer (ALB)\*\* to handle HTTPS traffic on port 443.

\- Configured HTTP (port 80) → HTTPS (port 443) redirect to enforce secure connections.



###### **### 5. Route 53 Alias Record Configuration**

\- Created an \*\*A – Alias record\*\* pointing the custom domain to the ALB.

\- Ensured DNS is resolving correctly to the application.



###### **### 6. Testing HTTPS Access**

\- Verified that the application is accessible over HTTPS with proper SSL configuration.

\- All traffic is securely routed to the application via the custom domain.





##### **## Summary**

\- Custom domain `evershopintern.com` is fully configured with Route 53.

\- SSL certificate issued via ACM and attached to ALB for secure HTTPS traffic.

\- HTTP traffic is redirected to HTTPS to enforce security.

\- The application is fully prepared to serve traffic over a secure custom domain.



