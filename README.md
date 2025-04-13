# Customer Segmentation with RFM and Agglomerative Clustering

##  Overview

This project performs **customer segmentation** using **RFM analysis** (Recency, Frequency, Monetary) combined with **Agglomerative Clustering** to uncover behavioral patterns among customers. The goal is to help businesses better understand their customer base and implement data-driven marketing strategies for improved engagement and retention.


## Objective

- Calculate **RFM scores** for each customer based on transaction data.
- Create a **composite score** ('RFM_Score_Sum') to rank customer value.
- Apply **hierarchical clustering** (Agglomerative) to identify similar customer segments.
- Visualize the clusters and relationships between RFM metrics.
- Derive actionable insights for **targeted marketing** and **loyalty programs**.


## Dataset
The dataset is available at [Download here](https://archive.ics.uci.edu/dataset/502/online+retail+ii). 
The dataset consists of retail transaction data with the following columns:

- Invoice: Unique invoice number (indicating a transaction)
- StockCode: Product/item code
- Description: Description of the product (some missing values)
- Quantity: Number of units purchased
- InvoiceDate: Date and time of the transaction
- Price: Price per unit
- Customer ID: Unique identifier for the customer (contains missing values)
- Country: Country where the transaction took place

From this data, the following metrics were computed:
- **Recency**: Days since the customer’s last purchase  
- **Frequency**: Number of transactions made  
- **Monetary**: Total amount spent by the customer


## Results

### RFM Scoring

- Each metric (R, F, M) was binned into quartiles using `pd.qcut`.
- Scores were assigned (1–5 scale) with higher scores indicating better customer behavior.
- A **combined score** (`RFM_Score_Sum`) was created to rank overall customer value.

### Visualizations

- **Heatmap** of R vs F scores revealed customer concentration areas.
- **Correlation matrix** showed strong relationships between R, F, M, and the combined score.
- **Agglomerative Clustering** (4 clusters) visually separated customer segments based on behavior patterns.

### Clusters Identified

- **Cluster 0**: Low Recency, High Frequency/Monetary → Loyal Champions  
- **Cluster 1**: Medium Recency and Frequency → Potential Loyalists  
- **Cluster 2**: High Recency (inactive customers) → At-Risk Customers  
- **Cluster 3**: Low Frequency/Monetary → New or One-Time Buyers  

## Conclusion

This analysis demonstrates how RFM and hierarchical clustering can:

- Segment customers by value and behavior
- Highlight high-value vs. at-risk customers
- Provide a foundation for personalized marketing strategies
- Encourage data-driven decisions for customer retention

