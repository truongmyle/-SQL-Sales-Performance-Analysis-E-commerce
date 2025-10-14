# [SQL] Sales Performance Analysis | E-commerce
# 📊 Project Title: Sales Performance Analysis  
Author: Truong My Le  
Date: 2025-05-12  
Tools Used: SQL  

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### Objective:
### 📖 What is this project about? What Business Question will it solve?

This project uses **SQL on Google BigQuery** to analyze the **eCommerce data from  Google Analytics** in the **E-commerce industry**, aiming to:

✔️Understand user behavior and sales performance across different traffic sources.

✔️Identify conversion patterns from product views → add to cart → purchase.

✔️Provide insights to improve marketing efficiency and customer engagement.   

### 👤 Who is this project for?  

✔️ Data analysts & business analysts 

✔️ Marketing teams & decision-makers  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: [Google Analytics Sample Dataset (via Google BigQuery)](https://console.cloud.google.com/bigquery?referrer=search&hl=vi&project=rugged-memory-456417-v2&ws=!1m5!1m4!4m3!1sbigquery-public-data!2sgoogle_analytics_sample!3sga_sessions_20170801) 
- Size: 2,556 rows and 70+ columns (including nested fields such as totals, trafficSource, device, geoNetwork, and hits)  
- Format: Structured table stored in Google BigQuery
### 📌 Dataset Acess
To access the dataset, follow these steps:

- Log in to your Google Cloud Platform account and create a new project.
- Navigate to the BigQuery console and select your newly created project.
- In the **Explorer** panel, type **“ga_session”** into the search bar
- Enable **"Search all projects"** (toggle it on)
- Click on the **"ga_sessions_"** table to open it.

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
- **Table:** `ga_sessions_20170801`  
- The dataset contains **one main table** with multiple **nested and repeated fields** (e.g., `totals`, `trafficSource`, `device`, `geoNetwork`, `hits`). 

#### 2️⃣ Table Schema & Data Snapshot  

<details>
<summary>🧩 View Key Columns</summary>

| Column Name | Data Type | Description |  
|--------------|------------|-------------|  
| `fullVisitorId` | STRING | Unique visitor ID per session |  
| `date` | STRING | Session date (YYYYMMDD) |  
| `totals.visits` | INTEGER | Number of sessions (1 per active session) |  
| `totals.pageviews` | INTEGER | Total pageviews per session |  
| `totals.transactions` | INTEGER | Total completed transactions |  
| `totals.bounces` | INTEGER | Bounce indicator (1 if no interaction) |  
| `trafficSource.source` | STRING | Source of website traffic (e.g., google, youtube, direct) |  
| `hits.eCommerceAction.action_type` | STRING | Type of eCommerce action (e.g., view, add_to_cart, purchase) |  
| `hits.product.v2ProductName` | STRING | Product name viewed or purchased |  
| `hits.product.productRevenue` | INTEGER | Revenue generated from the product |  

</details>


---

## ⚒️ Main Process

## Task 1: Calculate total visit, pageview, transaction for Jan, Feb and March 2017 (order by month)
Analyze traffic trends (visits, pageviews, transactions) over Q1 2017 to assess website growth and marketing campaign performance across time.

📖SQL code:

  <img width="667" height="194" alt="C1" src="https://github.com/user-attachments/assets/82622b9a-ba42-4bf1-9188-57b2ba20ecc0" />

✅Result:
  

🎯Observations:

- **March** recorded the **highest number** of visits, pageviews, and transactions, suggesting stronger marketing performance or seasonal traffic growth.
- **February** experienced a slight dip in visits, but transactions still rose, indicating improved **conversion efficiency** despite lower traffic.
- Overall, the trend shows **positive** user engagement and growth momentum

## Task 2: Bounce rate per traffic source in July 2017
Bounce rate represents the percentage of website sessions where users visit only one page and leave without interacting further with the site. Bounce rate helps identify which channels attract high-quality visitors and which need optimization.

📖SQL code:

  <img width="690" height="162" alt="C2" src="https://github.com/user-attachments/assets/4ade25c0-1217-4c51-a1cb-87ba2b5c5e3c" />

✅Result:

  <img width="788" height="269" alt="R2" src="https://github.com/user-attachments/assets/da9c0cad-3cb0-41a1-85f2-cadfbc3efcfd" />

🎯Observations:

- Top traffic sources: Google (38.4K) and Direct (19.9K).
- YouTube and Facebook have high bounce rates (>60%).
-> Organic and direct channels drive the most visits, while social media traffic tends to be less engaged.
  
## Task 3: Revenue by traffic source by week, by month in June 2017
Evaluate how each marketing channel contributes to total revenue by week and month, supporting better budget allocation and campaign focus.

📖SQL code:
  
<img width="727" height="662" alt="C3" src="https://github.com/user-attachments/assets/27f65664-78fd-42e2-bfb2-8817ce2c05cb" />

✅Result:
  
<img width="981" height="405" alt="R3" src="https://github.com/user-attachments/assets/ac13e03e-2dc0-4ed4-836f-b86001534872" />

🎯Observations:

**Direct traffic** is the **main driver of revenue**, suggesting strong brand recognition or returning users. Google-related channels serve as steady contributors supporting overall revenue flow.

## Task 4: Average number of pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017
Compare browsing behavior between purchasers and non-purchasers to see how engagement impacts the chance of buying.

📖SQL code:

<img width="841" height="663" alt="C4" src="https://github.com/user-attachments/assets/7dea9e07-d22b-4da5-8306-213839ff0347" />

✅Result:

<img width="636" height="100" alt="R4" src="https://github.com/user-attachments/assets/7a1757eb-5ddb-4776-a266-22878ce28047" />

🎯Observations:

- Both groups show **an increase** in average pageviews from June (201706) to July (201707).
- Non-purchase users consistently view more pages than purchase users (≈3x higher).

## Task 5: Average number of transactions per user that made a purchase in July 2017
Identify customer repurchase behavior by calculating the average number of transactions per active buyer, indicating loyalty strength.

📖SQL code:
  

✅Result:
  
<img width="586" height="63" alt="R5" src="https://github.com/user-attachments/assets/8d458f09-70f5-4e90-8e6e-dce20536b4dc" />
  
🎯Observations:

A relatively high transaction rate per user suggests **strong customer engagement** or **repeat purchase behavior** during this period.

## Task 6: Average amount of money spent per session. Only include purchaser data in July 2017
Measure the average purchase value per session to estimate session profitability and marketing ROI.

📖SQL code:
  
<img width="824" height="201" alt="C6" src="https://github.com/user-attachments/assets/9424ed1a-58a3-4c7b-abb2-9147018e74e2" />

✅Result:

<img width="559" height="67" alt="R6" src="https://github.com/user-attachments/assets/f586a6e2-f497-482a-96c9-dbccc26f9fb7" />

🎯Observations:

A strong average revenue per visit indicates **high-quality traffic and effective conversion** in July 2017

## Task 7: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered
Discover product bundling and cross-selling patterns by finding items frequently purchased together.

📖SQL code:
  
<img width="733" height="469" alt="C7" src="https://github.com/user-attachments/assets/d686066c-4b06-4104-ac73-e9591592d448" />

✅Result:

<img width="482" height="235" alt="R7" src="https://github.com/user-attachments/assets/12a953f0-cd6a-46df-8b63-7ceda1be8dd4" />

🎯Observations:

Customers who purchased YouTube Men’s Vintage Henley tend to buy **Google-branded fashion and lifestyle accessories**.

## Task 8: Calculate cohort map from product view to addtocart to purchase in Jan, Feb and March 2017. For example, 100% product view then 40% add_to_cart and 10% purchase
Analyze the conversion funnel to see where users drop off between viewing, adding to cart, and purchasing — helping identify stages that need conversion improvement.

📖SQL code:
  
<img width="1071" height="484" alt="C8" src="https://github.com/user-attachments/assets/1f1a9f66-68d0-4b82-a5d1-9f2bf153b480" />

✅Result:
  
<img width="1101" height="133" alt="R8" src="https://github.com/user-attachments/assets/b3e76703-dbc8-4aec-9fd1-6eb978793733" />

🎯Observations:

Both **engagement and conversion efficiency improved** over time, indicating successful optimizations in the sales funnel or promotional efforts in Jan, Feb and March 2017.

## 🔎Conclusion 
By exploring eCommerce dataset:
-  I have gained **valuable information** about visits, pageviews, transactions, bounce rate by traffic source, revenue patterns, user behavior differences,… providing a full view of both **user engagement** and **sales performance**.
-  I gained a better understanding of **SQL techniques** such as data manipulation, aggregation, and window functions, which improved my ability to **analyze business performance** more effectively and **draw meaningful insights** from large datasets.
