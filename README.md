# Health Operations Analytics — Power BI Case Studies

Two Power BI dashboards built for the **Allianz Partners Health Operations Data Reporting & Analytics** assessment:

1. **[Helpline Performance Dashboard](#1-helpline-performance-dashboard)**: call-center KPIs, SLA tracking and abandonment drivers
2. **[Claims Analysis Dashboard](#2-claims-analysis-dashboard)**: claims drivers and exceptions

> The assessment data is not included in this repository. Only screenshots and a write-up are shared.

---

## 1. Helpline Performance Dashboard

**Goal:** give operations managers one view of helpline performance across 3 hotlines and 2 queues (Member Line, Payer Line), and show *why* calls are being abandoned.

### Pages

**Helpline Performance Overview**: headline KPIs, daily call volume vs. abandonment rate, call outcome split, and a performance table by hotline and queue.

![Helpline Overview](Helpline%20Screenshots/Helpline%20Overview.png)

**Hotline & Queue Deep-Dive**: a drill-down tree for *"What drives abandonment?"* (by call outcome, hotline and day part), a hotline comparison chart, and an agent productivity table (handled calls, AHT, hold rate per agent extension).

![Hotline & Queue Deep-Dive](Helpline%20Screenshots/Hotline%20and%20Queue%20Deep-Dive.png)

**Time Analysis**: call patterns over time.

![Time Analysis](Helpline%20Screenshots/Time%20Analysis.png)

### KPIs defined

| KPI | Definition |
|---|---|
| Total / Handled Calls | All calls received / calls answered by an agent |
| Abandonment Rate | Abandoned calls ÷ total calls |
| Service Level % | Share of calls answered within the SLA threshold (adjustable, default 10 sec) |
| ASA | Average Speed of Answer, in seconds |
| AHT | Average Handle Time, in seconds |
| Hold Rate | Share of handled calls placed on hold |

### Key findings (1–9 Jan 2023)

- **36,991 calls**, of which **78.35% were handled** and **21.65% abandoned**. Service level was **55.29%** against a 10-second threshold.
- **IVR abandonment is the main driver**: 6,162 of 8,008 abandoned calls (**77%**) dropped in the IVR, before reaching a queue. Fixing the IVR flow has more impact than adding agents.
- **Hotline #3 is the weakest line**: 33.35% abandonment and 49.76% service level, compared with 19.40% and 56.11% on Hotline #1.
- **Hotline #1 carries most of the volume**: 30,918 calls, or 84% of the total.
- Agent workload is evenly balanced (about 225–265 handled calls per extension, AHT 195–224 sec), so the service gap is about routing and IVR, not individual agents.

---

## 2. Claims Analysis Dashboard

**Goal:** show what is driving health-insurance claims cost and utilization, and flag unusual claims, frequent claimants and data gaps for review. Amounts are in AED.

### Pages

**Cost Driver**: KPIs (total cost, insured members, claims, claims per member, average cost per claim, cost per member), plus cost by cause, the top 10 diagnoses (ICD codes) and cost per member by dependency. You can filter by year, benefit, network, claim type and dependency.

![Cost Driver](Claims%20Screenshots/Claims%20Drivers%202024.png)

**Exceptions**: the 20 highest-value claims and the 10 most frequent claimants, for follow-up and fraud/abuse review.

![Exceptions](Claims%20Screenshots/Claims%20Exceptions.png)

**Data model**: a Claims fact table linked to Members, Membership, Providers, Calendar and Underwriting Year (UWY) tables.

![Data model](Claims%20Screenshots/Claims%20Data%20Model.png)

### Key findings

- **2024:** 27M in claims cost across about 3K insured members and 54K claims, which works out to **17 claims per member**, an average of **496 per claim**, and about **9K per member**.
- **Physical illness drives most of the cost**, far ahead of dental, optical and maternity.
- **The most common diagnoses are low back pain (M54.5) and neck pain (M54.2)**. Both are high-volume, lower-cost conditions where wellness or physiotherapy programs could cut claim frequency.
- **Spouses cost the most per member, and children the least.**
- **Exceptions:** the 10 most frequent claimants filed **3,090 claims costing 1.33M**, and the highest-value claims are mostly cardiac and cancer cases. Both groups are candidates for case management.

---

## Tools & techniques

`Power BI` · `Power Query` · `DAX` · `Data Modeling` · `Decomposition Tree` · `Adjustable SLA threshold` · `KPI Design`

---

**Ahmed Khaled** · Data Analyst · [LinkedIn](https://linkedin.com/in/ahmed-khaled-347711287) · [GitHub](https://github.com/ahmed-dataanalystt)
