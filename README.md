# Patient Support Program Analytics Dashboard
### Power BI · Healthcare Analytics · Pharma Operations

> **Dataset:** Synthetic CY2024 data modeled on real-world PSP operations. Drug names reflect actual J&J/Janssen products; all patient and case records are fictional and generated for analytical demonstration purposes.

---

## What This Project Is

This is a five-page Power BI dashboard built to analyze the end-to-end operational performance of a pharmaceutical Patient Support Program. PSPs are the hub-based programs drug manufacturers run to help patients navigate insurance, access specialty pharmacies, and afford high-cost specialty medications.

The dataset spans **500 enrollment cases**, **750 dispense records**, **400 prior authorization events**, and **26 weeks of launch tracking** for two oncology products. The analysis surfaces bottlenecks, benchmarks performance, and produces actionable recommendations across each operational domain.

---

## Business Questions This Dashboard Answers

- Where are patients dropping out of the enrollment funnel, and why?
- Which enrollment channels process patients fastest, and by how much?
- Are specialty pharmacies delivering consistent service levels across fill volume, delivery speed, and patient cost?
- How are newly launched drugs ramping compared to expected trajectory?
- Which payers are denying the most prior authorizations, and are we appealing aggressively enough?
- What is the financial journey of a typical dispense — from plan cost to patient out-of-pocket?

---

## Dashboard Pages

### `Page 1` — Enrollment Journey & Operational Efficiency

Tracks patient progression from intake through verified shipment, with a focus on identifying where and why drop-off occurs.

**Key findings:**
- End-to-end intake-to-ship averages **16.53 days**, with meaningful variation by enrollment channel
- The PA clearance stage is the primary funnel drop — **309 of 500 patients** (38% loss) clear PA
- HCP Portal processes patients **2.3 days faster** than phone/fax channels on average
- Active patient rate of **26.4%** signals a retention problem downstream of first fill

**Visuals:** KPI cards, enrollment funnel, horizontal bar by channel, drug × quarter heat map, payer/hub/status donut charts

---

### `Page 2` — Monthly KPI Trends & Benchmarking

Month-over-month performance tracking with therapeutic area breakdowns and cross-drug benchmarking.

**Key findings:**
- Processing speed stays **stable across volume fluctuations** (14–20 days), indicating hub capacity is not the constraint
- 6-month adherence rate of **70.55% trails the 80% target** — a meaningful gap for chronic therapy drugs
- Scatter plot quadrant analysis (PA approval rate × first fill rate) identifies which drugs have access issues vs. fulfillment issues vs. both
- July enrollment dip of ~20% warrants investigation for seasonal or field force causes

**Visuals:** Combo chart (volume + processing speed), multi-line therapeutic area trend, PA vs. first fill scatter plot, copay assistance bar chart

---

### `Page 3` — Dispense Analytics & SP Performance

Specialty pharmacy scorecard with financial flow analysis and drug/formulation volume breakdown.

**Key findings:**
- Volume is evenly distributed across 10 SPs (range: 65–92 fills), reducing single-point dependency risk
- **42% of dispenses are not using copay assistance** despite likely eligibility — automatic eligibility checks at intake could recover these
- Average patient OOP after copay assistance: **$276.82** on a $14,730 average plan-paid fill
- Delivery times range from **1.35 to 2.02 days** across pharmacies — actionable for SP tiering strategy

**Visuals:** SP bar chart, SP scorecard matrix, drug × formulation treemap, financial waterfall chart

---

### `Page 4` — New Drug Launch Performance

26-week launch ramp analysis for AKEEGA and CARVYKTI, two newer oncology products.

**Key findings:**
- Week-over-week enrollment growth of **11.54%** — healthy trajectory
- Enrollment-to-dispense conversion at **15.37%** is well below benchmark, primarily driven by PA delays early in launch
- Average days to first dispense is improving (**~28 days → ~17 days** over 26 weeks) but still above the 14-day target
- SP network grew from 3 to 9 pharmacies onboarded by Week 26, a critical operational enabler

**Visuals:** Toggle gauge set (WoW growth, PA rate, conversion), dual-axis launch ramp chart, time-to-first-dispense trend with regression line, stacked area pipeline status, SP/call volume/HCP portal line charts

---

### `Page 5` — PA & Denial Deep Dive

Root cause analysis of the prior authorization bottleneck that surfaces across every other page.

**Key findings:**
- **66.75% PA approval rate** — approximately 1 in 3 PAs are denied on first submission
- Appeal overturn rate of **40.85%** is strong, but only **53.38% of denials are being appealed** — leaving an estimated 60+ patients per year without access they could have obtained
- No payer is meeting the 7-day turnaround target; Kaiser Permanente and Centene are the slowest
- Non-Formulary is the top denial reason for Commercial plans; Out of Network dominates Medicare Part B — each requiring a different response strategy

**Visuals:** KPI cards, avg calendar days to decision bar chart (by payer), denial reason × payer type heat map, interactive decomposition tree (PA count → denial reason → drug → region)

---

## Summary Metrics

| KPI | Value |
|-----|-------|
| Total Enrollments | 500 |
| Avg Days — Intake to Ship | 16.53 days |
| PA Approval Rate | 64.17% |
| Active Patient Rate | 26.40% |
| Total Dispenses | 750 |
| Avg Plan Paid per Fill | $14,730 |
| Avg Patient OOP (post copay assist) | $276.82 |
| Copay Assist Utilization | 58.00% |
| First Fill Rate | 80.26% |
| 6-Month Adherence Rate | 70.55% |
| Appeal Overturn Rate | 40.85% |
| Denial Appeal Rate | 53.38% |

---

## Technical Details

**Tool:** Microsoft Power BI Desktop

**Data model:** Star schema — enrollment fact table joined to dispense, PA, and launch dimension tables across patient, drug, payer, and specialty pharmacy keys

**DAX measures include:**
- Rolling averages and period-over-period comparisons
- Funnel conversion rates at each pipeline stage
- Weighted averages for OOP and plan cost calculations
- Dynamic quadrant classification for scatter plot benchmarking

**Visualization types used:**
Funnel · Waterfall · Scatter plot · Heat map · Treemap · Decomposition tree · Stacked area · Dual-axis combo chart · Gauge · Donut · Matrix scorecard · KPI cards

---

## Domain Knowledge Applied

This project required working understanding of how PSPs actually operate:

- **Hub operations** — enrollment intake, benefits investigation, PA submission and appeal workflows
- **Specialty pharmacy** — SP network structure, days supply conventions, return-to-stock dynamics
- **Prior authorization** — payer-specific denial patterns, appeal processes, turnaround benchmarks
- **Copay assistance programs** — eligibility logic, utilization tracking, financial waterfall modeling
- **Drug launch analytics** — ramp curve expectations, conversion benchmarks, pipeline stage tracking
- **Adherence metrics** — first fill rate, 6-month persistence, patient status segmentation

---

## Files

| File | Description |
|------|-------------|
| `psp_dashboard.pdf` | Full dashboard export — all 5 pages |
| `PSP_Dashboard_Report.docx` | Accompanying written analysis with findings and recommendations per page |
