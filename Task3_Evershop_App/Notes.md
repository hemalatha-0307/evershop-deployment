#### **# Task 3 - Implement S3 Bucket for Product Images**



###### **## Objective**

\- Store product images in AWS S3 bucket.

\- Modify e-commerce app to fetch images from S3 instead of local server.



###### **## Steps Performed**



1\. Created S3 bucket: *`evershop-product-images-internship`*

2\. Enabled public read access for all objects.

3\. Uploaded 4 sample product images:

&nbsp;  - product1.jpg

&nbsp;  - product2.jpg

&nbsp;  - product3.jpg

&nbsp;  - product4.jpg

4\. Updated PostgreSQL *`products`* table to point *`image`* column to S3 URLs.

5\. Verified in DB that all 4 products have correct S3 image URLs.

6\. Modified ***CollectionProductsWidget.resolvers.js*** to fetch S3 URLs for display in app.

7\. Restarted app container to apply changes.



###### **## Verification**

\- S3 bucket shows all 4 product images.

\- DB query `SELECT id, name, image FROM products;` shows correct S3 URLs.

\- Product images ready to be displayed in the app.

###### 

###### **## Notes**

\- Website display is optional; verification is via S3 + DB.

\- All commands were executed in Ubuntu root as per project setup.



