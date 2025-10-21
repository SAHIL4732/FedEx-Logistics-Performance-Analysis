# FedEx-Logistics-Performance-Analysis


***

# 📦 FedEx Logistics Performance Analysis: Optimizing the Global Supply Chain

## 🎯 Project Overview

This project is an **Exploratory Data Analysis (EDA)** capstone focused on optimizing the complex global supply chain managed by FedEx Logistics. The primary goal is to analyze a dataset detailing shipments of pharmaceuticals (specifically HIV test kits) to identify key cost drivers, bottlenecks, and optimization opportunities.

### Business Objective
The core business objective is to **streamline FedEx's logistics operations** by identifying inefficiencies in shipment modes, delays, and costs to ultimately **reduce operational expenses**, **improve on-time delivery rates**, and **enhance overall supply chain efficiency**.

***

## 📊 Data & Methodology

### Data Description
The dataset contains **10,324 records** across **33 columns** capturing granular details of individual shipments. Key variables analyzed include:
* **Shipment Details:** Country, Shipment Mode, Vendor, and Manufacturing Site.
* **Product Information:** `Product Group` (e.g., ARV, HRDT), `Sub Classification`, and `Dosage`.
* **Financial & Logistical Metrics:** `Line Item Quantity`, `Line Item Value`, `Weight (Kilograms)`, and `Freight Cost (USD)`.

### Data Wrangling and Preparation
The raw data required significant cleaning to handle missing values and non-numeric entries:

1.  **Non-Numeric Cleaning:** Non-numeric entries (e.g., 'Weight Captured Separately', 'Freight Included in Commodity Cost') in columns like `Weight (Kilograms)` and `Freight Cost (USD)` were converted to numeric type (`np.nan`).
2.  **Imputation:** Missing numerical values (`Weight (Kilograms)`, `Freight Cost (USD)`, etc.) were filled using the **median**. Missing categorical values (`Dosage`, `Shipment Mode`) were filled using the **mode**.
3.  **Feature Engineering:** A crucial new column, **`Delay (Days)`**, was engineered by calculating the difference between the `Delivered to Client Date` and the `Scheduled Delivery Date`.
4.  **Analysis Approach:** Univariate, Bivariate, and Multivariate (UBM) analysis was performed using visualization and correlation techniques to uncover relationships.

***

## 💡 Key Findings and Insights

### 🌍 Regional Focus and Demand
* **Geographic Concentration:** Shipments are heavily concentrated in **Nigeria (23%)** and **Vietnam (15%)**, indicating these are high-demand priority regions for the logistics operation.
* **Delay Hotspot:** The country with the **highest median delivery delay (7 days)** is Nigeria.

### ✈️ Shipment Mode & Cost Drivers
* **Dominant Mode:** **Air shipments** dominate the transport mix (accounting for **70%** of shipments), suggesting a strong preference for speed due to the time-sensitive nature of medical goods.
* **Cost Variance:** Air shipments have a significantly **higher median freight cost (~$3,000)** compared to Truck shipments (~$1,000).
* **Cost-Weight Correlation:** A **positive correlation (0.4)** was found between `Freight Cost (USD)` and `Weight (Kilograms)`, confirming that heavier shipments generally cost more, though there is high variance for lower-weight items.
* **Delay-Cost Relationship:** Delays correlate positively with freight costs (0.35 correlation), suggesting that the costlier, faster modes (Air) tend to be more punctual.

### 💊 Product & Vendor Analysis
* **Product Importance:** **ARV products** (Antiretrovirals) account for **80% of all shipments** and represent the highest total line item value, identifying them as the most critical and expensive items in the supply chain.
* **Vendor Concentration:** **Aurobindo Pharma** is a single largest vendor, supplying **25%** of items, highlighting a critical supplier relationship.

***

## 📈 Recommendations for Optimization

Based on the EDA, the following data-driven actions are recommended to optimize FedEx's logistics performance:

1.  **Freight Cost Optimization:**
    * **Action:** Implement a policy to strategically shift non-urgent and low-value shipments from **Air to Truck/Sea**.
    * **Expected Impact:** Potential reduction in overall freight costs by **15-20%**.

2.  **Delay Mitigation in Critical Regions:**
    * **Action:** Immediately investigate and address the logistical bottlenecks, customs issues, or coordination failures specifically in **Nigeria**, which shows the highest median delay of 7 days.
    * **Expected Impact:** Implement better scheduling and local coordination to reduce the average delay in high-delay regions to **<3 days** to improve customer satisfaction and prevent potential client loss.

3.  **Strategic Vendor Management:**
    * **Action:** Leverage the high volume supplied by key vendors (like Aurobindo Pharma) to **negotiate favorable pricing and Service Level Agreements (SLAs)**, including volume discounts and stricter fulfillment timelines.

4.  **Premium Logistics for High-Value Goods:**
    * **Action:** Ensure the highest level of premium logistics service and prioritized tracking for **high-value ARV products** to safeguard this crucial revenue stream.
    * **Action:** Focus on packaging optimization for heavier shipments to capitalize on the cost-weight correlation, reducing overall freight expenses.

***

## 🛠️ Technologies Used

* **Python**
* **Pandas** (Data Manipulation and Wrangling)
* **NumPy** (Numerical Operations)
* **Matplotlib** (Static Visualization)
* **Seaborn** (Statistical Visualization)
* **Plotly Express** (Interactive Visualization)
