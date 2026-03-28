# Case 3: Automated Reporting & Data Insights (Python + Pandas)

!!! abstract "Client Brief (Simulation)"
    **Niche:** Large eCommerce Project (Multi-channel traffic).
    **Problem:** The marketing team spends 10-15 hours a week manually consolidating data from Google Ads, Meta Ads, CRM, and Google Analytics into massive Excel spreadsheets. Human error frequently occurs, and decisions are made with delays.
    **Task:** Automate the data collection process, build end-to-end analytics, and find hidden patterns (insights) that are not visible in standard ad account reports.

---

## 🔍 Stage 1: The Problem with Manual Data Processing

During the reporting process audit, I discovered:
* **Data Silos:** Meta Ads shows one number of conversions, Google Ads shows another, and the CRM has completely different figures. There is no single "source of truth."
* **Inability to do Cohort Analysis:** Manually calculating the LTV (Lifetime Value) of clients who came from a specific ad campaign six months ago was practically impossible.
* **Time Waste:** Instead of optimizing campaigns, specialists were busy copy-pasting.

---

## 🛠 Stage 2: Python-Powered Solution

To eliminate these issues, I applied a Data Science approach by writing an automation script:

### 1. Data Aggregation via API
Wrote a Python script that automatically pulls Raw Data via API from Google Ads, Facebook Graph API, and the Shopify platform.

### 2. Data Wrangling (Cleaning & Merging)
Used the **Pandas** library to process data arrays. The script removes duplicates, normalizes UTM parameters, and merges ad spend with actual CRM revenue based on unique user or transaction IDs.

```python
# Pandas data processing logic snippet
import pandas as pd

# Load raw data
ads_data = pd.read_csv('export_ads.csv')
crm_data = pd.read_csv('export_crm.csv')

# Merge data based on UTM campaigns and dates
merged_df = pd.merge(ads_data, crm_data, on=['date', 'utm_campaign'], how='left')

# Calculate actual ROAS and CPA
merged_df['real_cpa'] = merged_df['spend'] / merged_df['crm_approved_leads']
merged_df['real_roas'] = (merged_df['crm_revenue'] / merged_df['spend']) * 100

# Find the most profitable days of the week
insights = merged_df.groupby('day_of_week')['real_roas'].mean().sort_values(ascending=False)

3. Telegram Alerts Setup
Added a notification function to the script. Now, if a specific campaign's ROAS drops below a critical level (e.g., <150%) for 24 hours, the script automatically sends an alert to the team's Telegram chat.

!!! success "Business Impact"
* Time Saved: A process that took 15 hours a week is now executed automatically in 2 minutes every morning.
* Data-Driven Insights: Analysis of the datasets showed that users acquired through night-time campaigns on Meta Ads have a 40% higher LTV. The budget was reallocated, resulting in a +18% increase in overall profit for the quarter.
* Transparency: The client received fully transparent end-to-end analytics, clearly showing the actual return on every invested dollar.
