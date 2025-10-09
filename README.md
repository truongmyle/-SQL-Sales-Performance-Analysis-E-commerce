# User Behavior & Sales Performance Analysis | E-commerce | SQL (BigQuery)
## **I. Introduction**

This project uses the public Google Analytics eCommerce dataset to explore and analyze user activities and sales performance using SQL in Google BigQuery. The dataset includes session-level information from users visiting an eCommerce website.

## **II. Requirements**

- [Google Cloud Platform account](https://cloud.google.com/)
- Project on Google Cloud Platform
- [Google BigQuery API](https://cloud.google.com/bigquery/docs/enable-transfer-service#:~:text=Enable%20the%20BigQuery%20Data%20Transfer%20Service,-Before%20you%20can&text=Open%20the%20BigQuery%20Data%20Transfer,Click%20the%20ENABLE%20button.) enabled
- [SQL query editor](https://cloud.google.com/monitoring/mql/query-editor)

## **III. Dataset Access**

This project uses the **Google Analytics Sample Dataset** provided by Google, which is publicly available on BigQuery. 

To access the dataset, follow these steps:

- Log in to your Google Cloud Platform account and create a new project.
- Navigate to the BigQuery console and select your newly created project.
- In the **Explorer** panel, type **“ga_session”** into the search bar
- Enable **"Search all projects"** (toggle it on)
- Click on the **"ga_sessions_"** table to open it.

## **IV. Exploring the Dataset**

In this project, I will write 08 query in Bigquery base on Google Analytics dataset

### **Query 01: Calculate total visit, pageview, transaction for Jan, Feb and March 2017 (order by month)**

- SQL code
<img width="844" height="224" alt="image" src="https://github.com/user-attachments/assets/c50f5868-f0b3-4844-b5eb-8e2e3d0316c1" />

- Query result
<img width="788" height="130" alt="image" src="https://github.com/user-attachments/assets/c924ffc7-ce32-4102-9ae6-ec508748e7bc" />

### **Query 02: Bounce rate per traffic source in July 2017**

- SQL code
<img width="680" height="164" alt="image" src="https://github.com/user-attachments/assets/6e024ba5-143f-4098-be24-4e09a1c2a80d" />

- Query result
<img width="730" height="603" alt="image" src="https://github.com/user-attachments/assets/9ea2e33d-5958-4f86-a545-42cb76c3ecc3" />

### **Query 03: Revenue by traffic source by week, by month in June 2017**

- SQL code
<img width="721" height="666" alt="image" src="https://github.com/user-attachments/assets/b0b6d273-55cc-4232-871d-ae928e58199a" />

- Query result
<img width="977" height="540" alt="image" src="https://github.com/user-attachments/assets/7db4ff09-417e-4b4f-8edf-39ba0b3308a9" />

### **Query 04: Average number of pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017.**

- SQL code
<img width="848" height="665" alt="image" src="https://github.com/user-attachments/assets/1bb2b76a-244d-4bce-aff0-e5599ec9c7fa" />

- Query result
<img width="764" height="98" alt="image" src="https://github.com/user-attachments/assets/43ac4b1a-966a-4d0e-95b5-ba1ab04ceb9e" />

### **Query 05: Average number of transactions per user that made a purchase in July 2017**

- SQL code
<img width="871" height="202" alt="image" src="https://github.com/user-attachments/assets/00417478-28de-444c-af24-ea84607c9146" />

- Query result
<img width="580" height="74" alt="image" src="https://github.com/user-attachments/assets/1c4cab41-6919-4a27-aeae-9dce77b96df5" />

### **Query 06: Average amount of money spent per session. Only include purchaser data in July 2017**

- SQL code
<img width="843" height="203" alt="image" src="https://github.com/user-attachments/assets/3ee20b39-91bc-4620-81ed-5e2f04bbf007" />

- Query result
<img width="560" height="63" alt="image" src="https://github.com/user-attachments/assets/09488836-f9ff-48d9-a7b4-aced6d208aa7" />

### **Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.**

- SQL code
<img width="722" height="445" alt="image" src="https://github.com/user-attachments/assets/2783c552-c85a-420b-aef9-9bb0400e69ff" />

- Query result
<img width="478" height="570" alt="image" src="https://github.com/user-attachments/assets/55c2b9c3-cc5b-4940-a6c5-14299f8b4647" />

### **Query 08: Calculate cohort map from product view to addtocart to purchase in Jan, Feb and March 2017. For example, 100% product view then 40% add_to_cart and 10% purchase.**

- SQL code
<img width="1306" height="401" alt="image" src="https://github.com/user-attachments/assets/83988b42-63ae-481f-b768-71403b429a0f" />

- Query result
<img width="1098" height="133" alt="image" src="https://github.com/user-attachments/assets/dece4685-f9ed-497b-bb5d-317c814a96a5" />

## **V. Conclusion**

- In this project, I explored the Google Analytics eCommerce dataset using SQL on Google BigQuery, which revealed several interesting insights.
- By exploring eCommerce dataset, I have gained valuable information about visits, pageviews, transactions, bounce rate by traffic source, revenue patterns, user behavior differences,… providing a full view of both user engagement and sales performance.
- This useful insights for business can be further developed with data visualization tools like Power BI or Tableau.
