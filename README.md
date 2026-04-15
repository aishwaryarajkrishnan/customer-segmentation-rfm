# 🧠 Customer Segmentation using RFM Analysis

## 📌 Overview

In this project, I applied **RFM (Recency, Frequency, Monetary) analysis** on e-commerce transactional data to better understand customer behavior. The goal was to segment customers based on their purchasing patterns, identify those at risk of churn, and suggest actionable strategies to improve retention and revenue.

---

## 🎯 Business Problem

E-commerce businesses generate large volumes of transactional data but often lack clear visibility into customer value and engagement. Without this understanding, it becomes difficult to prioritize high-value customers, reduce churn, and allocate marketing efforts effectively.

Through this project, I aimed to use transactional data to segment customers, analyze churn risk, and derive insights that can support better business decisions.

---

## 📊 Dataset

The dataset contains online retail transaction data, including:

* Invoice details
* Product descriptions
* Quantity and price
* Customer IDs
* Transaction timestamps

Each row represents a single transaction line item, and customers can appear multiple times.

---

## ⚙️ Methodology

### 1. Data Cleaning

* Removed rows with missing `CustomerID` values
* Handled negative quantities (returns)
* Created a `TotalPrice` column (`Quantity × UnitPrice`)

---

### 2. RFM Feature Engineering

Customers were aggregated at the customer level, and the following metrics were calculated:

* **Recency**: Days since last purchase
* **Frequency**: Number of purchases
* **Monetary**: Total spend

---

### 3. RFM Scoring

* Used quantile-based scoring (`pd.qcut`)
* Assigned scores for Recency, Frequency, and Monetary
* Combined these into an overall **RFM score**

---

### 4. Customer Segmentation

Based on the RFM score, customers were grouped into:

* **High Value**
* **Medium Value**
* **Low Value**
* **At Risk**

---

### 5. Analysis & Visualization

I explored the segments using:

* Customer distribution across segments
* Revenue contribution by segment
* Frequency vs Monetary relationship
* Monetary distribution using boxplots
* Churn analysis based on recency

---

### 6. Churn Analysis

Customers with high recency (i.e., not having purchased recently) were flagged as likely churned.
This helped identify which segments were most at risk.

---

### 7. Segment-Level Insights

From the analysis:

* **High-value customers**:

  * Purchase frequently
  * Spend significantly more
  * Show very low churn

* **Low-value and at-risk customers**:

  * Have low engagement
  * Show high inactivity
  * Have significantly higher churn rates

---

### 8. Revenue Contribution

I found that:

* **High-value customers contribute ~74% of total revenue**

This indicates a strong concentration of revenue within a relatively small segment of customers.

---

### 9. Strategy Mapping

To make the analysis actionable, each segment was mapped to a business strategy:

| Segment      | Strategy                        |
| ------------ | ------------------------------- |
| High Value   | Retain with loyalty programs    |
| Medium Value | Upsell and cross-sell           |
| Low Value    | Increase engagement with offers |
| At Risk      | Re-engagement campaigns         |

---

## 🔍 Key Takeaways

* A large portion of revenue (~74%) comes from high-value customers
* Customer engagement (frequency) is strongly linked to spending
* Low-value and at-risk customers exhibit significantly higher churn rates
* High-value customers are stable and should be prioritized for retention

---

## 💡 Business Recommendations

* Focus on **retaining high-value customers** through loyalty and personalization
* **Upsell medium-value customers** to increase their contribution
* Use targeted campaigns to **re-engage at-risk customers**
* Improve engagement among low-value customers through offers and incentives

---

## 📈 Business Impact

From this analysis, businesses can:

* Identify their most valuable customers
* Reduce churn by targeting the right segments
* Allocate marketing efforts more efficiently
* Improve overall revenue stability

---

## ⚠️ Limitations

* Churn is inferred using recency and not actual churn labels
* The analysis does not include demographic or product-level features

---

## 🛠️ Tools Used

* Python (Pandas, NumPy)
* Matplotlib & Seaborn
* Jupyter Notebook

---

## 🚀 Conclusion

This project shows how RFM-based segmentation can be extended with churn analysis and strategy mapping to move beyond analysis and support real business decisions.

---
