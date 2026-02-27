# Cohort Retention & Churn Analytics for SaaS Subscription

## 🧠 Project Overview

This project applies cohort retention analysis to a SaaS subscription dataset to measure customer retention trends and identify churn risk factors. Insights are used to support data-driven strategies for improving subscription growth and reducing churn.

An end-to-end analytics workflow was perfotmed:
- Data Cleaning & Processing
- Cohort Retention Matrix
- Revenue Retention Trends
- Retention Comparison by billing frequency and plan tier
- Strategic recommendations for improving activation and reducing churn
- Interactive Dashboard (Google Looker Studio)


---

## 📥 Dataset Description

**The dataset spans 5 CSV files:**

- accounts.csv – customer metadata
- subscriptions.csv – subscription lifecycles and revenue
- feature_usage.csv – daily product interaction logs
- support_tickets.csv – support activity and satisfaction scores
- churn_events.csv – churn dates, reasons, and refund behaviors

**Row Volume:**

- accounts – 500
- subscriptions – 5,000
- feature_usage – 25,000
- support_tickets – 2,000
- churn_events – 600

---

## 🛠 Data Processing & Feature Engineering

Key steps performed:

- Make new function `build_retention` for retention table based on monthly cohort:
  - Converted `start_date` and `end_date` to datetime
  - Group customers by month of joining (cohort)
  - Calculate how long they have been active
  - Create a retention matrix
  - Generate retention rates per cohort
- Compare retention rate: combination of annual + monthly, monthly only, and annual only
- Make retention rate heatmap (cohort table): combination of annual + monthly, monthly only, and annual only
- Compare revenue retention: combination of annual + monthly, monthly only, and annual only
- Make revenue retention heatmap (cohort table): combination of annual + monthly, monthly only, and annual only
- Compare retention by `plan_tier`
- Export csv for dashboard

---

## 📊 Key Findings

1. **Customer Retention**
   - Month 1 Retention: 99.78%
   - Month 6 Retention: 96.70%
   - Month 12 Retention: 92.61%
   - Overall Churn Rate: 9.72%
   Retention remains strong with no significant early-lifecycle drop. Churn appears gradual rather than activation-driven.

2. **Revenue Retention**
   - **Month 6 Revenue Retention: 95.46%**

     Revenue retention closely mirrors customer retention, suggesting limited downgrade behavior within the pilot cohort. Minor softness appears around Months 8–12, potentially linked to renewal cycles.

3. **Billing Frequency Comparison**
     Retention differences between monthly and annual subscriptions were minimal during the first 6 months. This indicates billing frequency is not the primary churn driver within this dataset.

4. **Plan Tier Analysis**
   Churn rates across tiers were relatively similar (~9-10%)

   However:
   - Enterprise accounts have significantly higher avg MRR
   - Revenue exposure risk is concentrated in high-tier customers
  
   Implication:
   - Retention management for Enterprise accounts is strategically critical despite similar churn rates.

---

## 🧩 Strategic Insights

1. **Pilot Retention May Be Inflated**
   - Controlled cohort may not represent public launch performance
   - Risk of overstimating LTV
2. **Mid-lifecycle Engagement Decay**
   - Gradual retention decline between Months 6-12
   - Opportunity for value reinforcement before renewal cycle
3. **Revenue Risk Concentration**
   - Enterprise churn has disproportionate revenue impact

---

## 🚀 Strategic Recommendations

- Implement mid-lifecycle engagement nudges before Month 6
- Develop renewal risk monitoring for high-MRR accounts
- Focus on expansion triggers instead of discount-heavy tactics
- Monitor seat reduction and downgrade signals proactively

---

## 📈 Interactive Dashboard

The Dasboard was built using **Google Looker Studio** to visualize:

**Included Views**
- KPI retention
- Customer retention curve
- Revenue retention curve
- 12-month cohort heatmap
- Plan tier churn comparison

🔗 **Live Dashboard Link:**  
https://lookerstudio.google.com/reporting/176c3a04-dc59-40a4-bdb2-578d304ba972

Screenshots available in the `/images` folder.

---

## 🧰 Tools Used

- Python (Pandas, NumPy)
- Google Colab
- Google Looker Studio
- GitHub

