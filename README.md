# CustomerSatisfaction
#  Olist Logistics Optimization: A Causal Inference Approach

**Objective:** Isolate the true drivers of customer dissatisfaction in Brazilian E-Commerce to reduce churn.
**Role:** Data Analyst / Causal Inference Specialist
**Tools:** Python (DoWhy, Pandas, Seaborn), SQL, CausalML

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
*(Note: I recommend taking screenshots of your 2 best charts from the notebook and pasting them here!)*

**1. The Heterogeneity Analysis (VIP vs. Budget)**
> *[Insert your Bar Chart showing flat sensitivity across tiers]*
> *Insight: High-spending customers react to delays with the same intensity as budget shoppers.*

**2. The Geographic Risk Map**
> *[Insert your SP vs. RJ Bar Chart]*
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
| **1. Engineering** | `01_data_extraction.sql` | **Data Extraction:** Complex SQL queries to join Orders, Payments, and Geolocation data, creating a unified analytical view. |
| **2. Diagnostics** | `02_eda_diagnostics.ipynb` | **Exploratory Analysis:** Assessing data quality, handling missing values in the pre-2013 vintage, and identifying distribution errors. |
| **3. Preparation** | `03_feature_engineering.ipynb` | **Cleaning & Engineering:** Creating the "Treatment" (`is_late`) and "Confounders" (`distance_km`, `freight_ratio`) required for the Causal Model. |
| **4. Analysis** | `04_causal_inference.ipynb` | **Modeling & Storytelling:** Running the `DoWhy` Causal Model, calculating ATE (Average Treatment Effect), and generating the final business insights. |

---

##  Installation & Usage

1. Clone this repo.
2. Install requirements: `pip install seaborn pandas`
3. Run the notebooks in order.

---
*Author: [Your Name]*
*Connect on LinkedIn: [Your Link]*
