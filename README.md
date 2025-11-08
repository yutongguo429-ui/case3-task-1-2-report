# Casework 3: Task 1 Report - Demand Fulfillment Capacity Plan

---

## 1. Objective

[cite_start]The objective of Task 1 is to develop a "demand fulfillment capacity plan" for each of the 20 parts (P1-P20) for the Year +1 horizon[cite: 132].

This plan is not based on simple averages. [cite_start]It is a statistically derived capacity target designed to **robustly** meet the client's mandatory **99.5% on-time in-full (OTIF) replenishment service level**[cite: 41]. The final output of this task is the minimum weekly production capacity required to achieve this service level.

## 2. Methodology

To create a robust plan that accounts for demand uncertainty, we cannot simply plan for the average demand. We must plan for the average demand *plus* a "safety capacity" to cover fluctuations.

The governing formula for this plan is:
**Capacity Plan = Average Demand + Safety Capacity**

Our four-step methodology was as follows:

1.  [cite_start]**Calculate Part-Level Weekly Average Demand ($\mu_{\text{part}}$):** We first calculated the weekly average demand for each part by multiplying the **Product-Parts Matrix** (Bill of Materials) [cite: 38] [cite_start]by the **Year +1 Weekly Demand Forecast for Each Product**[cite: 32].

2.  **Calculate Part-Level Weekly Standard Deviation ($\sigma_{\text{part}}$):** This is the most critical step for managing variability.
    * [cite_start]First, we calculated the weekly standard deviation for each **product** ($\sigma_{\text{prod}}$) using its average demand and its Coefficient of Variation (CV)[cite: 32, 33].
    * Second, we used the principle of variance aggregation. The demand variance for a single part is the sum of the variances from all products that use it. This was calculated using matrix multiplication.

3.  **Determine Z-Score (Safety Factor):** The 99.5% service level was converted into a statistical safety factor (Z-score) using the inverse normal distribution.

4.  **Calculate Final Capacity Plan (CPD):** We combined the components to find the required capacity. This result was rounded **up** to the nearest integer (using `CEILING` or `ROUNDUP`), as it is impossible to provision fractional capacity.

## 3. Key Formulas Used

The following formulas were used to execute the methodology. (Note: These are written in LaTeX and will render correctly in a GitHub `.md` file).

**1. Product Weekly Standard Deviation ($\sigma_{\text{prod}}$):**
$$
\sigma_{\text{prod}} = \mu_{\text{prod, weekly}} \times CV_{\text{prod}}
$$

**2. Part Weekly Standard Deviation ($\sigma_{\text{part}}$):**
*Calculated by aggregating the variances from each product.*
$$
\sigma_{\text{part}} = \sqrt{\sum_{\text{prod}} (N_{\text{part\_in\_prod}}^2 \times \sigma_{\text{prod}}^2)}
$$

**3. Z-Score for 99.5% Service Level:**
$$
Z = \text{NORM.S.INV}(0.995) \approx 2.576
$$

**4. Final Capacity Planning Demand (CPD):**
$$
\text{CPD} = \text{CEILING}(\mu_{\text{part, weekly}} + (Z \times \sigma_{\text{part, weekly}}))
$$

| Part | Weekly Avg Demand ($\mu_{\text{weekly}}$) | Weekly Std Dev ($\sigma_{\text{weekly}}$) | **Capacity Planning Demand (CPD) (Units/Week)** |
| :--- | :--- | :--- | :--- |
| P1 | 20,962 | 2,235.16 | **26,719** |
| P2 | 11,156 | 1,187.38 | **14,212** |
| P3 | 6,154 | 619.25 | **7,749** |
| P4 | 9,231 | 1,106.63 | **12,081** |
| P5 | 6,923 | 1,071.41 | **9,683** |
| P6 | 4,038 | 572.17 | **5,513** |
| P7 | 13,844 | 1,895.50 | **18,729** |
| P8 | 4,616 | 553.92 | **6,042** |
| P9 | 8,846 | 1,261.61 | **12,096** |
| P10 | 4,616 | 538.52 | **6,002** |
| P11 | 8,076 | 1,144.35 | **11,025** |
| P12 | 10,000 | 1,248.76 | **13,217** |
| P13 | 5,000 | 624.38 | **6,609** |
| P14 | 18,076 | 1,936.48 | **23,065** |
| P15 | 2,308 | 276.96 | **3,021** |
| P16 | 11,923 | 2,036.64 | **17,169** |
| P17 | 5,000 | 624.38 | **6,609** |
| P18 | 11,923 | 1,306.65 | **15,289** |
| P19 | 20,000 | 2,230.50 | **25,745** |
| P20 | 14,808 | 1,736.16 | **19,280** |

## 5. Conclusion

The "Capacity Planning Demand (CPD)" column is the definitive result of Task 1. It provides a robust, statistically-backed target for weekly production. These CPD figures, not the average demand, will serve as the direct input for all subsequent calculations, including equipment requirements (Task 3) and storage planning (Task 2).
