
# A/B Testing: Free Trial Screener Experiment

This project analyzes the effectiveness of a reminder popup on a "Start Free Trial" button for an educational content platform. The goal was to improve user experience and reduce customer churn by helping users make more informed choices.

---

## Experiment Overview

**Control Group**  
- Homepage shows two buttons:  
  - “Start Free Trial” → requires credit card and auto-billing after 14 days  
  - “Access Materials” → gives partial free access  

**Experiment Group**  
- Clicking “Start Free Trial” triggers a popup suggesting “Access Materials” as a free alternative.

### Hypothesis
Clearer expectations will reduce churn and improve satisfaction without significantly impacting payment conversion.

---

## Metrics Defined

### Invariant Metrics (for sanity checks)
- Unique cookies to view page per day  
- Unique clicks on “Start Free Trial”  
- Click-Through Probability (CTP)

### Evaluation Metrics
| Metric              | Formula                       | Baseline  | Min Detectable Effect |
|---------------------|-------------------------------|-----------|------------------------|
| **Gross Conversion** | Enrollments / Clicks           | 20.63%    | 1%                     |
| **Net Conversion**   | Payments / Clicks              | 10.93%    | 0.75%                  |
| **Retention**        | Payments / Enrollments         | 53%       | 1%                     |

---
## Metric Calculations & Evaluation

### Standard Deviation Estimates
- **Gross Conversion:** `0.0143`
- **Net Conversion:** `0.0110`
- **Retention:** `0.0389`

---

## Sample Size & Duration Calculation

Using α = 0.05 and β = 0.2:

| Metric            | Required Clicks | Required Pageviews | Duration (50% traffic) |
|-------------------|------------------|----------------------|--------------------------|
| Gross Conversion  | 25,835           | 645,868              | ~33 days                 |
| Net Conversion    | 27,413           | 685,336              | ~35 days                 |
| Retention         | 39,087 enrolled  | 4,737,771            | ~118 days (excluded)  |

**Retention metric was dropped** due to the long required test duration.

---

## Data Summary

### Experimental Group
- Average Pageviews/day: **9315**
- Average Clicks/day: **766**
- Enrollments/day: **~149**
- Payments/day: **~85**

### Control Group
- Average Pageviews/day: **9340**
- Average Clicks/day: **767**
- Enrollments/day: **~165**
- Payments/day: **~88**

---

## Sanity Checks

| Metric     | Control   | Experiment |
|------------|-----------|------------|
| Pageviews  | 345,543   | 344,660    |
| Clicks     | 28,378    | 28,325     |
| CTP        | 8.21%     | 8.22%      |

**Sanity checks passed** — both groups are balanced and comparable.

---

## Evaluation Results

### Gross Conversion

GC_diff = -0.0206
95% CI = [-0.0291, -0.0120]
p-value = 2.57e-06

**Statistically and practically significant decrease** in Gross Conversion in the experiment group.

### Net Conversion
NC_diff = -0.0049
95% CI = [-0.0116, 0.0019]
p-value = 0.1558

**Not statistically significant** — experiment did not meaningfully affect final payments.

