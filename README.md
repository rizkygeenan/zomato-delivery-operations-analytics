# 🛵 Zomato Delivery Operations Analytics & Service Efficiency Optimization

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Power BI](https://img.shields.io/badge/Power_BI-Dashboard-yellow.svg)
![Google Colab](https://img.shields.io/badge/Google_Colab-EDA%20%26%20Hypothesis%20Testing-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

## 📌 Project Overview
This project is an operational analytics study focusing on identifying the key factors influencing food delivery duration, testing operational hypotheses, and formulating data-driven strategies to improve delivery SLA efficiency for **Zomato**.

Delivery duration directly impacts customer satisfaction, driver ratings, and user retention. By leveraging exploratory data analysis (EDA) and statistical hypothesis testing (t-tests, ANOVA, and two-way ANOVA), this project addresses operational bottlenecks caused by traffic congestion, weather anomalies, vehicle types, and regional disparities across ~45K transactional records.

- **Dataset:** Zomato Delivery Operations (~45K orders)
- **Tools Used:** Python (Pandas, NumPy, SciPy, Seaborn), Power BI (Interactive Operations Dashboard), Google Colab

---

## 🎯 Key Objectives
1. Identify primary bottlenecks affecting food delivery times across different urban areas and time windows.
2. Statistically validate operational hypotheses regarding weather, driver demographics, traffic density, vehicle types, and holiday/festival surges.
3. Build an interactive Power BI dashboard for real-time fleet management and operational decision-making.
4. Formulate actionable business recommendations to reduce delivery times, optimize driver allocation, and mitigate SLA breach rates.

---

## 📊 Key Findings & Analytical Insights

### 1. Key Operational Metrics
- **Total Orders Analyzed:** 29.505K
- **Average Delivery Time:** 26.25 minutes
- **SLA Breach Rate:** 3.04%
- **Average Speed:** 21.86 km/h (Over-speeding Rate: 3.12%)
- **Average Customer Rating:** 4.66 / 5.00

### 2. Primary Bottlenecks & Influencing Factors
- **Festival / Holiday Impact:** Delivery times surge by **+75%** during festival periods (45.36 minutes) compared to non-festival days (25.92 minutes).
- **Traffic & Peak Hours:** Traffic jams increase delivery times to 31.02 minutes (+46% slower than low traffic). Peak bottleneck hours consistently occur between **19:00 - 21:00** (peaking at ~32 minutes on Wednesdays and Fridays).
- **Weather Conditions:** Foggy and Cloudy weather conditions experience the longest delivery durations (~29 minutes), approximately **36% slower** than clear/sunny conditions (21.23 minutes).
- **Regional Bottlenecks:** Semi-urban areas record the longest delivery time (49.37 minutes) due to severe courier under-allocation (only 85 drivers, ~3.8% of the total fleet), whereas Urban areas maintain the highest efficiency (23.03 minutes with 1,033 drivers).
- **Multiple Deliveries Correlation:** The number of stacked orders per delivery (`multiple_deliveries`) shows the highest positive correlation with delivery time (r = +0.39).

---

## 🧪 Statistical Hypothesis Testing (Validation)

| Hypothesis | Test Method | Key Finding | Statistical Conclusion |
| :--- | :--- | :--- | :--- |
| **H1: Higher Courier Rating = Faster Delivery** | Two-sample t-test | High-rated couriers significantly reduce average delivery time. | H0 Rejected |
| **H2: Weather Condition Effect** | ANOVA | Adverse weather (Fog/Cloudy) significantly slows down delivery. | H0 Rejected |
| **H3: Courier Age Disparity** | Two-sample t-test | Younger couriers (<30 years) deliver significantly faster (22.99 min vs 29.32 min for 30+). | H0 Rejected |
| **H4: Traffic Density Impact** | ANOVA | Heavy traffic density directly increases delivery delays. | H0 Rejected |
| **H5: Festival Surge Impact** | Two-sample t-test | Festival days dramatically increase delivery times (45.36 min). | H0 Rejected |
| **H6: Vehicle Type Efficiency** | ANOVA | Delivery times differ significantly across vehicle types. | H0 Rejected |
| **H7: City Type Variation** | ANOVA | Semi-urban areas require significantly more delivery time than urban areas. | H0 Rejected |
| **H8: Peak Hours Spike** | Two-sample t-test | Peak hour delivery times are significantly higher than off-peak hours. | H0 Rejected |
| **H9: Peak Hours × Order Type Interaction** | Two-way ANOVA | No significant interaction effect; peak traffic impacts all order types equally. | H0 Accepted |

---

## 🖥️ Dashboard Overview

The **Zomato Delivery Operations Dashboard** built in Power BI provides full operational visibility and real-time filtering capabilities:

### ⚙️ Interactive Slicers & Global Controls
* **Period Filter:** Date range selection (e.g., `2/11/2022 - 4/6/2022`).
* **City Filter:** Multi-tier filtering across Metropolitan, Urban, and Semi-Urban zones.
* **Festival Filter:** Dynamic toggle between Festival (`Yes`) and Non-Festival (`No`) operational modes.

### 📈 Executive KPI Strip
* **Total Orders:** `29.505K`
* **Average Delivery Time:** `26.25 min`
* **SLA Breach Rate:** `3.04%`
* **Average Speed:** `21.86 km/h`
* **Over-speeding Rate:** `3.12%`
* **Average Customer Rating:** `4.66 / 5.00`

### 📊 Visual Layout & Components
1. **Weather Impact Analysis:** Combined column & line chart comparing order volume (`Count of id`) vs. average delivery duration across weather types (*Fog, Stormy, Cloudy, Windy, Sandstorms, Sunny*).
2. **Road Traffic Density Analysis:** Evaluates delivery delays across traffic congestion levels (*Low, Jam, Medium, High*).
3. **Festival Impact Bar Chart:** Side-by-side comparison illustrating the sharp increase in transit time during festival seasons (`Yes` vs. `No`).
4. **Vehicle Type & Peak Hours Matrix:** Analyzes delivery speed variations across transport types (*Motorcycle, Electric Scooter, Scooter*) during peak vs. off-peak windows.
5. **Regional Driver Allocation & Transit:** Visualizes total active drivers vs. average delivery time across city classifications (*Metropolitan, Urban, Semi-Urban*).
6. **Courier Age Demographics:** Breakdown of delivery efficiency categorized by driver age bins (*30-34, 35+, 25-29, 20-24*).

<img width="862" height="490" alt="zomato-dashboard" src="https://github.com/user-attachments/assets/b3e5d12f-44ac-4971-8224-0c969d644bc7" />


---

## 💡 Actionable Business Recommendations

1. **Dynamic Weather SLA Adjustment:** Automatically adjust estimated delivery SLAs during adverse weather conditions, deploy rainy-weather courier incentives, and provide standard safety equipment.
2. **Festival & Peak Hour Fleet Scaling:** Implement surge pricing during peak hours (19:00 - 21:00) to regulate order spikes, introduce pre-order scheduling features, and recruit temporary delivery staff during festival seasons.
3. **Semi-Urban Logistics Hubs:** Establish intermediary micro-fulfillment hubs in semi-urban regions to cut down the current 49.37-minute average transit time and rebalance driver distribution.
4. **Smart Vehicle & Order Allocation:** Prioritize electric scooters for short-range urban deliveries during off-peak hours, restrict stacked order quotas (`multiple_deliveries`) per courier, and assign younger driver cohorts to express commercial orders.

---

## 📂 Deliverables & Repository Structure

```text
├── dataset/
│   └── zomato_deliveries_cleaned.csv          # Processed transactional delivery data
├── notebooks/
│   └── zomato_eda_and_hypothesis_testing.ipynb  # Python notebook for Data Preprocessing, EDA & Hypothesis Testing
├── dashboard/
│   └── Zomato_Delivery_Operations.pbix        # Power BI Interactive Dashboard
├── reports/
│   └── Zomato_Delivery_Operations_Presentation.pdf # Presentation slides submitted for Exam
└── README.md                                  # Project documentation
