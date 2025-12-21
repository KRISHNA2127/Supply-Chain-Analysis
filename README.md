# 📦 End-to-End Supply Chain Optimization (Olist)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Libraries](https://img.shields.io/badge/Library-Pandas%20%7C%20Seaborn%20%7C%20Matplotlib-orange)
![Domain](https://img.shields.io/badge/Domain-Supply%20Chain%20%26%20Logistics-green)

## 📌 Project Overview
This project performs a comprehensive analysis of the **Olist E-commerce Supply Chain**, simulating a real-world "Control Tower" environment. By integrating disparate datasets (Orders, Payments, Reviews, Geolocation), the project moves beyond descriptive analytics to provide **prescriptive strategic recommendations**.

The analysis identifies critical bottlenecks in the Brazilian logistics network, quantifies the impact of lead times on customer sentiment, and proposes a decentralization strategy to fix a **97% customer churn rate**.

---

## 💼 Business Problem
Olist operates in Brazil, a country with continental dimensions and complex logistics challenges. The central business questions addressed in this project are:
1.  **Logistics:** Where are the bottlenecks in the distribution network?
2.  **Inventory:** Which products drive revenue, and how should they be stocked (ABC Analysis)?
3.  **Customer Experience:** Does a delay in delivery mathematically correlate with negative reviews?
4.  **Retention:** Why is the customer retention rate so low, and how can Supply Chain improvements fix it?

---

## 📂 The Dataset
The analysis utilizes the **Brazilian E-Commerce Public Dataset by Olist** (Relational Schema):
* `orders.csv`: Timestamp data for the order lifecycle.
* `order_items.csv`: SKU-level details, price, and freight costs.
* `products.csv` & `translations.csv`: Product dimensions and categories.
* `customers.csv` & `sellers.csv`: Geospatial data (Origin & Destination).
* `reviews.csv`: Sentiment data (1-5 stars) and text comments.
* `payments.csv`: Transactional data and payment methods.

---

## 🛠️ Tech Stack
* **Python:** Core programming language.
* **Pandas:** ETL, Data Cleaning, and Feature Engineering.
* **Matplotlib & Seaborn:** Data Visualization (Heatmaps, Bar Charts, Time Series).
* **Numpy:** Numerical operations for KPI calculation.

---

## 🚀 Project Roadmap (9 Phases)

### Phase 1-2: ETL & Data Cleaning
* Ingested 8+ relational tables.
* Standardized timestamps for Lead Time calculations.
* Performed Master Data Management (MDM) to translate product categories from Portuguese to English.

### Phase 3: Supply Chain Feature Engineering
* Calculated **Actual Lead Time** vs. **Estimated Lead Time**.
* Engineered the **OTD (On-Time Delivery)** binary metric.
* Created "Delivery Variance" to measure risk (Promise vs. Reality).

### Phase 4: ABC Analysis (Inventory Optimization)
* Applied the **Pareto Principle (80/20 Rule)**.
* **Finding:** A small subset of 5 categories (e.g., Bed Bath Table, Health & Beauty) drives the majority of revenue. These are classified as **Class A** stock requiring "Never-Out-of-Stock" protection.

### Phase 5: Logistics & Network Design (Lane Analysis)
* Mapped **Origin (Seller)** to **Destination (Customer)** routes.
* **Visual:** Heatmap of Lead Times by State.
* **Finding:** Massive regional disparity.
    * **South/Southeast (Local):** ~8-10 Days Lead Time.
    * **North/Northeast (Remote):** ~20+ Days Lead Time.

### Phase 6: Strategic Optimization
* Simulated the business case for **Decentralization**.
* Quantified the "Opportunity Cost" of serving remote regions from the Sao Paulo Hub.

### Phase 7: Service Quality & Sentiment Analysis (NLP)
* Correlated `actual_lead_time_days` with `review_score`.
* **Text Mining:** 40%+ of negative reviews explicitly mention "Delay" or "Delivery."
* **Insight:** "Speed = Satisfaction." Review scores drop precipitously after a 2-week wait.

### Phase 8: Financial & Operational Dashboard
* Analyzed Seasonality (Black Friday spikes).
* Identified weekly demand peaks (Mondays) for warehouse labor planning.

### Phase 9: RFM Analysis (Customer Retention)
* Segmented customers by **Recency, Frequency, and Monetary** value.
* **Critical Discovery:** **96.9%** of customers are "One-Time Buyers."
* **Conclusion:** High lead times in remote areas are causing high churn.

---

## 📊 Key Results & Visuals

1.  **The Inequality of Logistics:** The Heatmap revealed that Sao Paulo is an overloaded hub, causing delays for 25% of the country.
2.  **The Churn Crisis:** RFM analysis showed less than 1% of customers are "Champions/VIPs."
3.  **The Cost of Delay:** Customers waiting >15 days are almost guaranteed to leave a detractor score (<3 stars).

---

## 💡 Strategic Recommendations

Based on the data, the following roadmap is proposed to Olist leadership:

1.  **Open a Northeast Distribution Center (DC):**
    * Target Location: Bahia (BA) or Pernambuco (PE).
    * **Goal:** Cut lead times in the "Red Zone" by 50% (from 20 days to 10 days).

2.  **Launch "Olist Prime" Loyalty Program:**
    * Target the "New/Active" segment identified in Phase 9.
    * Incentive: Fast shipping (enabled by the new DC) to convert one-time buyers into repeat loyalists.

3.  **Inventory Rationalization:**
    * Liquidate "Class C" inventory to free up working capital.
    * Reinvest capital into Class A stock depth for the holidays.

---

## 💻 How to Run This Project
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
3.  Ensure the dataset files (`orders.csv`, `items.csv`, etc.) are in the root directory.
4.  Run the Jupyter Notebook: `Olist_Supply_Chain_Optimization.ipynb`.

---

**Author:** Gokul Krishnan
**Role:** Supply Chain Analyst
