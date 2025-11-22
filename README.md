# CustomerSatisfaction
#  Olist Logistics Optimization: A Causal Inference Approach

**Objective:** Isolate the true drivers of customer dissatisfaction in Brazilian E-Commerce to reduce churn.
**Role:** Data Analyst / Causal Inference Specialist
**Tools:** Python (EconPandas, Seaborn), SQL, CausalML(EconML)

---

## Executive Summary
In e-commerce, it is easy to confuse correlation with causation. Does a customer give a bad review because shipping was expensive, or because it was late?

Using **Causal Inference** (to control for confounders like Price, Freight, and Distance), this project quantified the exact "Cost of Lateness."

### Key Findings
* **The Cost of Delay:** Late delivery is the single largest driver of churn, causing a **42 percentage point increase** in the probability of a negative review.
* **The "Universal" Expectation:** Analysis debunked the hypothesis that VIP customers are "pickier." Sensitivity to delays is **homogeneous** across all spending tiers—reliability is a universal requirement, not a luxury perk.
* **The Rio Paradox:** The **Sao Paulo $\to$ Rio de Janeiro** route (short distance) suffers from a disproportionately high failure rate due to urban friction, not geographic distance.

---

##  Visual Insights


**1. The Heterogeneity Analysis (VIP vs. Budget)**
> <img width="846" height="548" alt="Untitled" src="https://github.com/user-attachments/assets/cdeedac2-ea18-4f55-a5ac-32ec8967e265" />

> *Insight: High-spending customers react to delays with the same intensity as budget shoppers.*

**2. The Geographic Risk Map**
> <img width="846" height="661" alt="Untitled" src="https://github.com/user-attachments/assets/0ddcba47-6e9f-4bc8-9175-c7b8165bac7f" />
<img width="700" height="463" alt="Untitled" src="https://github.com/user-attachments/assets/6e9fbc74-784e-4ada-aa2f-f176047fc878" />


> *Insight: Urban congestion in Rio drives higher dissatisfaction than long-distance shipping to remote regions.*

---

##  Strategic Recommendations

Based on the causal analysis, I proposed a 3-point action plan to stakeholders:

1.  **Product (Algorithmic Padding):** Update the ETA prediction engine to add a **+2 Day Safety Buffer** specifically for the Rio de Janeiro capital region to align customer expectations with operational reality.
2.  **Operations (Last Mile):** Diversify the carrier mix for "Urban Hell" zones, shifting volume from trucks to motorcycle couriers to bypass congestion.
3.  **Strategy (Universal Standard):** Abandon the proposed "Tiered VIP Shipping" program and reallocate resources to systemic fixes, as data proves reliability is a hygiene factor for all segments.

---

##  Project Structure & Workflow

This repository is organized into 4 logical steps, mirroring the data pipeline:

| Step | Notebook/File | Description |
| :--- | :--- | :--- |
| **1. Engineering** | `1.Engineering_data.ipynb` | **Data Extraction:** Complex SQL queries to join Orders, Payments, and Geolocation data, creating a unified analytical view. |
| **2. EDA** | `2_EDA.ipynb` | **Exploratory Analysis:** Assessing data quality and identifying distribution errors. |
| **3. Preparation** | `3_Cleaning_data_&&_feature_engineering.ipynb` | **Cleaning & Engineering:** Creating the "Treatment" (`is_late`) and "Confounders" (`distance_km`) required for the Causal Model. |
| **4. Analysis** | `4_Casual_inference_&&_data_storytelling.ipynb` | **Modeling & Storytelling:** Running the `DoWhy` Causal Model, calculating ATE (Average Treatment Effect), and generating the final business insights. |

---

##  Installation & Usage

1. Clone this repo.
2. Run the notebooks in order.

---
*Author: Ngô Thị Ánh Dương*
