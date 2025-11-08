# Casework 3: Task 2 Report - Finished Storage Capacity Plan

---

## 1. Objective

The goal of Task 2 is to develop a finished-goods storage capacity plan for the 20 parts produced by FeMoaSa in Year +1.

The plan determines how much storage should be kept in the factory outbound area, the near-client warehouse for Client A, and the near-client warehouse for Client B to ensure a 99.5 % On-Time-In-Full (OTIF) service level.

Client A is replenished every hour with a 4-hour autonomy, while Client B is replenished every four hours with a 12-hour autonomy. No automated storage systems are used.

## 2. Methodology

* **Demand transformation –** Product demand was converted into part-level weekly averages and standard deviations using the Product–Parts matrix.
* **Hourly demand conversion –** Weekly demand values were divided by 80 operating hours per week to obtain average and standard-deviation demand per hour.
* **99.5 % hourly demand –** Using a safety factor z = 2.58, the protected hourly demand was calculated as:
    * $D_{\text{hr\_99.5}} = \mu_{\text{hr}} + z \times \sigma_{\text{hr}}$
* **Safety stock by autonomy time –**
    * Client A (4 h autonomy): $S_A = D_{\text{hr\_99.5}} \times 4$
    * Client B (12 h autonomy): $S_B = D_{\text{hr\_99.5}} \times 12$
* **Volume, area, and cost –**
    * Total Volume = Inventory × Part Volume (ft³ per piece)
    * Floor Area = Total Volume / Usable Height (20 ft)
    * Building Cost = Floor Area × 200 \$/ft²
* **Factory outbound storage –**
    * The factory buffer follows a 2-week autonomy rule using the data in the “FeMoaSa Warehouse” sheet: 2-week inventory (units), 2-week space (ft³), and ratio of square footage (ft²).
    * These represent the quantity, volume, and area of outbound storage.

## 3. Key Formulas Used

**Average hourly demand**

$$
\text{Average hourly demand} = \frac{\text{Average weekly demand}}{80}
$$

**Std dev hourly demand**

$$
\text{Std dev hourly demand} = \frac{\text{Std dev weekly demand}}{\sqrt{80}}
$$

**Protected hourly demand (99.5 %)**

$$
\text{Protected hourly demand (99.5 \%)} = \text{Average hourly} + 2.58 \times \text{Std dev hourly}
$$

**Safety stock**

$$
\text{Safety stock} = \text{Protected hourly demand} \times \text{autonomy hours}
$$

**Total volume (ft³)**

$$
\text{Total volume (ft³)} = \text{Safety stock} \times \text{volume per piece}
$$

**Floor area (ft²)**

$$
\text{Floor area (ft²)} = \frac{\text{Total volume}}{20}
$$

**Building cost ($)**

$$
\text{Building cost (\$)} = \text{Floor area} \times 200
$$

## 4. Results

### 4.1 Factory Outbound Storage (2-week autonomy)

| Part | 2-Week Autonomy Inventory (units) | 2-Week Autonomy Space (ft³) | Square Footage (ft²) |
| :--- | :--- | :--- | :--- |
| P1 | 50065.27 | 2086.05 | 395.96 |
| P2 | 26632.52 | 3945.56 | 748.93 |
| P3 | 14563.37 | 1820.42 | 345.54 |
| P4 | 22492.72 | 3748.79 | 711.58 |
| P5 | 17749.07 | 1972.12 | 374.34 |
| P6 | 10161.75 | 564.54 | 107.16 |
| P7 | 34598.07 | 961.06 | 182.42 |
| P8 | 11248.30 | 416.60 | 79.08 |
| P9 | 22288.15 | 1238.23 | 235.03 |
| P10 | 11192.37 | 414.53 | 78.68 |
| P11 | 20323.50 | 1129.08 | 214.32 |
| P12 | 24549.56 | 2045.80 | 388.32 |
| P13 | 12274.78 | 340.97 | 64.72 |
| P14 | 43208.32 | 1200.23 | 227.82 |
| P15 | 5624.15 | 312.45 | 59.31 |
| P16 | 31265.19 | 1157.97 | 219.80 |
| P17 | 12274.78 | 340.97 | 64.72 |
| P18 | 28606.56 | 794.63 | 150.83 |
| P19 | 48125.22 | 1336.81 | 253.75 |
| P20 | 35939.83 | 998.33 | 189.50 |
| **Total** | **483183.00** | **26825.00** | **5091.81** |

### 4.2 Client A Near-Client Warehouse (4 h autonomy, 99.5 %)

| Part | Total Volume (ft³) | Square Footage (ft²) |
| :--- | :--- | :--- |
| P1 | 33.48 | 6.36 |
| P2 | 65.64 | 12.46 |
| P3 | – | – |
| P4 | 65.85 | 12.50 |
| P5 | 43.90 | 8.33 |
| P6 | 2.98 | 0.56 |
| P7 | 14.98 | 2.84 |
| P8 | – | – |
| P9 | 26.33 | 5.00 |
| P10 | 7.15 | 1.36 |
| P11 | 5.95 | 1.13 |
| P12 | 17.85 | 3.39 |
| P13 | 2.98 | 0.56 |
| P14 | 19.09 | 3.62 |
| P15 | – | – |
| P16 | 27.24 | 5.17 |
| P17 | 2.98 | 0.56 |
| P18 | 7.55 | 1.43 |
| P19 | 21.95 | 4.17 |
| P20 | 17.42 | 3.31 |
| **Total** | **383.31** | **72.76** |

### 4.3 Client B Near-Client Warehouse (12 h autonomy, 99.5 %)

| Part | Total Volume (ft³) | Square Footage (ft²) |
| :--- | :--- | :--- |
| P1 | 10.64 | 2.02 |
| P2 | 16.09 | 3.05 |
| P3 | 31.91 | 6.06 |
| P4 | 18.10 | 3.44 |
| P5 | – | – |
| P6 | 11.00 | 2.09 |
| P7 | 11.00 | 2.09 |
| P8 | 8.04 | 1.53 |
| P9 | – | – |
| P10 | 2.01 | 0.38 |
| P11 | 22.00 | 4.18 |
| P12 | 32.99 | 6.26 |
| P13 | 5.50 | 1.04 |
| P14 | 6.82 | 1.30 |
| P15 | 6.03 | 1.15 |
| P16 | – | – |
| P17 | 5.50 | 1.04 |
| P18 | 11.00 | 2.09 |
| P19 | 7.09 | 1.35 |
| P20 | 4.52 | 0.86 |
| **Total** | **210.24** | **39.91** |

## 5. Conclusion

At a 99.5 % service level, the factory outbound area (2-week autonomy) requires 26 825 ft³ of space and 5 091.81 ft² of floor area.

Client A’s near-client warehouse (4 h autonomy) requires 383.31 ft³ / 72.76 ft², while Client B’s (12 h autonomy) requires 210.24 ft³ / 39.91 ft².

This allocation balances responsiveness and robustness: high-frequency, small-volume parts are stored at the factory to ensure quick replenishment, whereas large-volume or lower-frequency parts are positioned in near-client warehouses to minimize in-plant congestion.

Together, the three facilities achieve the 99.5 % OTIF target and provide a solid capacity foundation for subsequent layout and cost analysis in Task 3.
