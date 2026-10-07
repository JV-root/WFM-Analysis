# 📊 WFM Analysis – Call Center Performance (October 2020)

> 🌐 [Leia em português](readme-pt-br.md)

## 📌 Overview

This project presents an end-to-end data analysis of call center operations during October 2020, focusing on Service Level Agreement (SLA) performance, demand distribution, and customer experience.

The notebook has two parts. **Part 1** preserves the first analysis, with its conclusions exactly as they were written. **Part 2** submits each of those conclusions to statistical tests and rebuilds the diagnosis from the results.

---

## 🎯 Objectives

This analysis was designed to answer key operational questions:

- Where does the SLA stand, and how far is it from the target?
- Is the gap explained by any measurable dimension (call center, channel, reason or day of the week)?
- Does operational performance translate into customer experience?
- How is demand composed, and where are the levers to reduce it?
- What can this dataset **not** tell us, and what data would be needed?

---

## 📂 Dataset

- Source: call center data (simulated dataset, obtained from Kaggle)
- Period: October 2020, with 30 days analyzed (October 31 excluded for having only 1 record)
- Volume: 32,941 records, ~1,100 per day
- Key features:
  - SLA status (Within / Below / Above)
  - Call center location
  - Inbound channel (voice, chatbot, email, web)
  - Sentiment
  - CSAT score (covers 37.3% of contacts)
  - Call duration (AHT)
  - Contact reason (including service outages)

---

## 🧠 Analytical Approach

The analysis follows this structure:

1. **Data preparation**
2. **Part 1: original analysis, preserved**
3. **Part 2: review with hypothesis tests** (data quality audit, adherence, distribution, experience and the shape of the metrics)
4. **Recommendations**, split into what not to do and what to do with the available data
5. **Conclusion**, in layers: what the operation shows, what the dataset does not allow, and the ceiling of the diagnosis

The central rule of Part 2 is to test before concluding: every causal claim comes with the test that supports or refutes it.

---

## 🔎 Key Findings

- **The gap is a matter of level, not of event.** SLA adherence was 75.3%, 4.7pp below the 80% target, and the daily variation sits almost entirely within sampling noise.
- **No available dimension explains the gap.** Call center, channel, reason and day of the week are not significant at 5%.
- **SLA does not translate into experience.** CSAT within and outside the SLA is statistically identical (5.53 vs. 5.56).
- **Demand has a clear structure.** Billing questions make up 71.2% of the volume. Service outage, highlighted in Part 1 as the main driver, is the smallest of the three reasons (14.4%) and never arrives by voice.
- **The dataset has serious limits.** AHT follows a uniform distribution between 5 and 45 minutes, and there are no agents, schedules or hourly granularity. The capacity diagnosis cannot be closed with this data.

---

## 🛠️ Technical Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Statistical tests: chi-square, 95% confidence intervals and Student's t

---

## 📈 Visualization Standards

This project applies data visualization best practices:

- Time series normalization (complete date range)
- Percentage-based distributions for comparability
- 95% confidence intervals in group comparisons
- Highlight vs. secondary series styling
- Direct labeling on series (legends only for reference lines and categories)
- Minimalist design (no top/right borders)
- Executive-style titles and subtitles
- Explicit source and period annotation

---


## 👤 Author

**João Lima**

- Data Scientist | Performance & Operations
- Focus on WFM, SLA optimization, and operational analytics

---
