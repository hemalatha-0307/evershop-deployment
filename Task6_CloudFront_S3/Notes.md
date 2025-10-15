#### **Task 6 – Integrate CloudFront with S3 for Faster Content Delivery**



In this task, I connected my S3 bucket that stores product images with Amazon CloudFront to improve image loading speed and security. The goal was to deliver static content faster through CloudFront’s global network and prevent direct public access to the S3 bucket.



---



##### **## Steps Followed**



1. ###### **Created CloudFront Distribution**

&nbsp;  - Opened AWS CloudFront and created a new web distribution.

&nbsp;  - Selected the existing S3 bucket `evershop-product-images-internship` as the \*\*origin\*\*.

&nbsp;  - Set the Origin Path to `/product-images`.

&nbsp;  - Enabled Origin Access Control (OAC) so only CloudFront can access the bucket.

&nbsp;  - Created the distribution and waited for it to become active.



&nbsp;  CloudFront Domain Name:  

&nbsp;  `https://d2p220o01to8sh.cloudfront.net`

###### 

###### **2. Updated S3 Bucket Policy**

&nbsp;  - Removed the old public-read policy.

&nbsp;  - Added a new policy allowing access only to CloudFront (through OAC) using its distribution ARN.

&nbsp;  - This ensured that users can no longer directly open S3 URLs.



###### **3. Verified Access Restriction**

&nbsp;  - Tried accessing an image using its S3 object URL and got the expected Access Denied message.  

&nbsp;    Example (blocked):  

&nbsp;    `https://evershop-product-images-internship.s3.amazonaws.com/product-images/product1.jpg`

###### 

###### **4. Tested CloudFront Access**

&nbsp;  - Accessed the same image using the CloudFront domain, and it loaded successfully:  

&nbsp;    `https://d2p220o01to8sh.cloudfront.net/product-images/product1.jpg`



&nbsp;  - This confirmed that the CloudFront distribution was correctly linked with the S3 bucket and delivering content securely.



###### **5. Performed Cache Invalidation**

&nbsp;  - Created an invalidation for `/*` to clear old cached versions and test updated files.

&nbsp;  - Verified that updated images reflected immediately after invalidation.



---



##### **## Comparison: Direct S3 vs CloudFront Load Times**
**Performance Comparison**

After testing both URLs, here are the main observations:

**1. Loading Speed**
Direct S3: Took around 1 – 2 seconds to load each image.
CloudFront: Loaded almost instantly (< 1 second) due to caching at nearby edge locations.

**2. Latency**
Direct S3: Slight delay noticed when fetching from the Mumbai region directly.
CloudFront: Reduced latency as content was served from edge servers closer to the user.

**3. Security & Access Control**
Direct S3: Bucket had to be public to serve images (less secure).
CloudFront: Allowed private S3 bucket while still delivering content securely over HTTPS.

**4. Overall Performance Impact**
CloudFront not only improved speed but also reduced data transfer cost for repeated requests and provided global scalability.

Summary: CloudFront provided faster, more secure, and more scalable delivery compared to direct S3 access.



---



###### **## Screenshots Summary**



1\. AccessDenied\_S3  = Confirms that direct S3 access was successfully blocked.  

2\. CloudFront\_Create\_Distribution  =Shows the setup process linking S3 as the origin.  

3\. CloudFront\_Distribution\_Active  = Confirms that the CloudFront distribution was successfully created and deployed.  

4\. CloudFront\_Image\_Loaded  = Proves that the image loads correctly via the CloudFront domain.  

5\. S3\_BucketPolicy\_Updated  =Displays the final policy allowing only CloudFront to access bucket objects.



---

###### 

###### **## Final Note:** 

This task successfully integrated CloudFront with the S3 bucket for secure and faster image delivery. Direct S3 access was restricted, and CloudFront improved performance and global accessibility.



