### Dataset Source: https://support.google.com/analytics/answer/3437719?hl=en
### Table Schema

| Field Name                               | Data Type | Description |
|------------------------------------------|-----------|-------------|
| `fullVisitorId`                          | STRING    | The unique visitor ID. |
| `date`                                   | STRING    | The date of the session in YYYYMMDD format. |
| `totals`                                 | RECORD    | This section contains aggregate values across the session. |
| `totals.bounces`                         | INTEGER   | Total bounces (for convenience). For a bounced session, the value is 1, otherwise it is null. |
| `totals.hits`                            | INTEGER   | Total number of hits within the session. |
| `totals.pageviews`                       | INTEGER   | Total number of pageviews within the session. |
| `totals.visits`                          | INTEGER   | The number of sessions (for convenience). This value is 1 for sessions with interaction events. The value is null if there are no interaction events in the session. |
| `totals.transactions`                    | INTEGER   | Total number of ecommerce transactions within the session. |
| `trafficSource.source`                   | STRING    | The source of the traffic source. Could be the name of the search engine, the referring hostname, or a value of the utm_source URL parameter. |
| `hits`                                   | RECORD    | This row and nested fields are populated for any and all types of hits. |
| `hits.eCommerceAction`                   | RECORD    | This section contains all of the ecommerce hits that occurred during the session. This is a repeated field and has an entry for each hit that was collected. |
| `hits.eCommerceAction.action_type`       | STRING    | The action type. Click through of product lists = 1, Product detail views = 2, Add product(s) to cart = 3, Remove product(s) from cart = 4, Check out = 5, Completed purchase = 6, Refund of purchase = 7, Checkout options = 8, Unknown = 0. <br><br> **Example query to calculate number of products in list views:**  <br>`SELECT COUNT(hits.product.v2ProductName)` <br>`FROM [foo-160803:123456789.ga_sessions_20170101]` <br>`WHERE hits.product.isImpression == TRUE` <br><br> **Example query to calculate number of products in detailed view:**  <br>`SELECT COUNT(hits.product.v2ProductName)` <br>`FROM [foo-160803:123456789.ga_sessions_20170101]` <br>`WHERE hits.eCommerceAction.action_type = '2' AND (BOOLEAN(hits.product.isImpression) IS NULL OR BOOLEAN(hits.product.isImpression) == FALSE)` |
| `hits.product`                           | RECORD    | This row and nested fields will be populated for each hit that contains Enhanced Ecommerce PRODUCT data. |
| `hits.product.productQuantity`           | INTEGER   | The quantity of the product purchased. |
| `hits.product.productRevenue`            | INTEGER   | The revenue of the product, expressed as the value passed to Analytics multiplied by 10^6 (e.g., 2.40 would be given as 2400000). |
| `hits.product.productSKU`                | STRING    | Product SKU. |
| `hits.product.v2ProductName`             | STRING    | Product Name. |
