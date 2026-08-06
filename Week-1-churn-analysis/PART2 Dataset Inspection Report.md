# PART 2: DATASET INSPECTION REPORT
## ABC Communications Ltd - Telco Customer Churn Dataset

**Report Date:** August 5, 2026  
**Analyst:** AnalystLab Africa - Data Analytics Internship  
**Dataset:** WA_Fn-UseC_-Telco-Customer-Churn.csv

---

## EXECUTIVE SUMMARY

The ABC Communications telco customer dataset contains **7,032 customer records** (after cleaning) with **21 attributes** tracking demographics, services, contracts, and churn status. The dataset is **high quality** with minimal data quality issues and is **ready for analysis**.

---

## 1. DATASET OVERVIEW

### 1.1 Size & Structure

| Metric | Value |
|--------|-------|
| **Total Records** | 7,032 customers |
| **Total Columns** | 21 attributes |
| **Date Range** | Historical snapshot (no time series) |
| **Data Quality** | GOOD (11 rows removed due to missing TotalCharges) |

### 1.2 Column Listing

| # | Column Name | Data Type | Description |
|---|---|---|---|
| 1 | customerID | Text | Unique customer identifier |
| 2 | gender | Text | Male / Female |
| 3 | SeniorCitizen | Numeric | 0=No, 1=Yes |
| 4 | Partner | Text | Yes / No |
| 5 | Dependents | Text | Yes / No |
| 6 | tenure | Numeric | Months as customer (1-72) |
| 7 | PhoneService | Text | Yes / No |
| 8 | MultipleLines | Text | Yes / No / No phone service |
| 9 | InternetService | Text | DSL / Fiber optic / No |
| 10 | OnlineSecurity | Text | Yes / No / No internet service |
| 11 | OnlineBackup | Text | Yes / No / No internet service |
| 12 | DeviceProtection | Text | Yes / No / No internet service |
| 13 | TechSupport | Text | Yes / No / No internet service |
| 14 | StreamingTV | Text | Yes / No / No internet service |
| 15 | StreamingMovies | Text | Yes / No / No internet service |
| 16 | Contract | Text | Month-to-month / One year / Two year |
| 17 | PaperlessBilling | Text | Yes / No |
| 18 | PaymentMethod | Text | Electronic check / Mailed check / Bank transfer / Credit card |
| 19 | MonthlyCharges | Numeric | USD per month |
| 20 | TotalCharges | Numeric | Total lifetime charges (USD) |
| 21 | Churn | Text | Yes / No |

---

## 2. DATA QUALITY ASSESSMENT

### 2.1 Missing Values

| Column | Missing Count | Missing % | Status |
|--------|-------|-------|--------|
| **TotalCharges** | 11 | 0.16% | ⚠️ REMOVED |
| **All Other Columns** | 0 | 0% | ✅ COMPLETE |

**Action Taken:** Removed 11 rows with missing TotalCharges values. Final dataset: 7,032 rows

### 2.2 Duplicate Records

✅ **No duplicate customerIDs found** - Each customer appears exactly once

### 2.3 Data Type Validation

✅ **All columns have correct data types:**
- Text columns: gender, Partner, Dependents, PhoneService, InternetService, Contract, PaymentMethod, Churn
- Numeric columns: SeniorCitizen, tenure, MonthlyCharges, TotalCharges

### 2.4 Outliers & Invalid Values

✅ **No obvious data errors found:**
- Tenure ranges from 1-72 months (valid)
- Monthly charges range from $18.25-$118.75 (reasonable)
- Total charges align with tenure × monthly charges
- No negative or impossible values

---

## 3. DEMOGRAPHIC ANALYSIS

### 3.1 Gender Distribution

| Gender | Count | Percentage |
|--------|-------|-----------|
| Male | 3,549 | 50.4% |
| Female | 3,483 | 49.6% |

✅ **Nearly perfect gender balance** - No bias in dataset

### 3.2 Life Status

| Attribute | Yes | No | % Yes |
|-----------|-----|-----|-------|
| Senior Citizen | 1,142 | 5,890 | 16.2% |
| Has Partner | 3,393 | 3,639 | 48.3% |
| Has Dependents | 2,099 | 4,933 | 29.8% |

**Insight:** 
- Majority are younger/middle-aged customers (83.8%)
- Nearly half have partners
- ~30% have family dependents

---

## 4. TENURE ANALYSIS

### 4.1 Tenure Statistics

| Metric | Value |
|--------|-------|
| **Minimum Tenure** | 1 month |
| **Maximum Tenure** | 72 months (6 years) |
| **Average Tenure** | 32.42 months (~2.7 years) |
| **Median Tenure** | 29 months (~2.4 years) |
| **Std Deviation** | 24.56 months |

### 4.2 Tenure Distribution

```
Tenure Ranges:
  0-12 months:   2,186 customers (31.1%)
  12-24 months:  1,522 customers (21.6%)
  24-36 months:  1,254 customers (17.8%)
  36-48 months:    903 customers (12.8%)
  48-60 months:    718 customers (10.2%)
  60-72 months:    449 customers (6.4%)
```

**Finding:** High concentration of new customers (1-12 months) - early churn is a risk

---

## 5. SERVICE UTILIZATION

### 5.1 Phone & Internet Services

| Service | Yes | No | % with Service |
|---------|-----|-----|--------|
| **Phone Service** | 6,361 | 671 | 90.5% |
| **Internet Service** | 5,512 | 1,520 | 78.4% |

### 5.2 Internet Type (for those with internet)

| Type | Count | Percentage |
|------|-------|-----------|
| Fiber Optic | 3,096 | 44.0% |
| DSL | 2,416 | 34.4% |
| No Internet | 1,520 | 21.6% |

### 5.3 Add-on Services Adoption

| Service | Customers | % Adoption |
|---------|-----------|-----------|
| OnlineSecurity | 2,015 | 28.7% |
| OnlineBackup | 2,425 | 34.5% |
| DeviceProtection | 2,418 | 34.4% |
| TechSupport | 2,040 | 29.0% |
| StreamingTV | 2,703 | 38.4% |
| StreamingMovies | 2,731 | 38.8% |

**Finding:** Entertainment services (Streaming) are most popular, less than 30% have security/backup

### 5.4 Services Bundle Analysis

```
Distribution by Number of Add-on Services:
  0 services: 2,213 customers (31.5%)
  1 service:    966 customers (13.7%)
  2 services: 1,033 customers (14.7%)
  3 services: 1,117 customers (15.9%)
  4 services:   850 customers (12.1%)
  5 services:   569 customers (8.1%)
  6 services:   284 customers (4.0%)
```

---

## 6. CONTRACT & BILLING ANALYSIS

### 6.1 Contract Type Distribution

| Contract Type | Count | Percentage |
|---------------|-------|-----------|
| Month-to-month | 3,875 | 55.1% |
| One year | 1,472 | 20.9% |
| Two year | 1,685 | 23.9% |

**Finding:** Majority (55%) are on flexible month-to-month contracts

### 6.2 Payment Method Distribution

| Payment Method | Count | Percentage |
|----------------|-------|-----------|
| Electronic Check | 2,365 | 33.6% |
| Mailed Check | 1,604 | 22.8% |
| Bank Transfer (Auto) | 1,542 | 21.9% |
| Credit Card (Auto) | 1,521 | 21.6% |

### 6.3 Paperless Billing

| Type | Count | Percentage |
|------|-------|-----------|
| Yes | 4,171 | 59.3% |
| No | 2,861 | 40.7% |

**Finding:** Majority prefer digital billing

### 6.4 Charges Analysis

#### Monthly Charges
| Metric | Value |
|--------|-------|
| Minimum | $18.25 |
| Maximum | $118.75 |
| Average | **$64.80** |
| Median | **$70.35** |
| Std Dev | $30.09 |

#### Total Charges
| Metric | Value |
|--------|-------|
| Minimum | $18.80 |
| Maximum | $8,684.80 |
| Average | $2,283.30 |
| Median | $1,440.55 |

**Finding:** Significant price range - some customers pay 5X more than others

---

## 7. CHURN ANALYSIS

### 7.1 Overall Churn Metrics

| Metric | Value |
|--------|-------|
| **Total Customers** | 7,032 |
| **Churned** | 1,869 |
| **Retained** | 5,163 |
| **Churn Rate** | **26.58%** |
| **Retention Rate** | **73.42%** |

**Critical Finding:** 1 in 4 customers churn - significant business risk

### 7.2 Churn by Key Dimensions

#### By Contract Type
```
Month-to-month:  42.71% churn (1,655 of 3,875)
One year:        11.28% churn (166 of 1,472)
Two year:        2.85% churn (48 of 1,685)
```
**⚠️ CRITICAL:** Month-to-month customers are 15X more likely to churn!

#### By Internet Service
```
Fiber Optic:     41.89% churn (1,297 of 3,096)
DSL:             19.00% churn (459 of 2,416)
No Internet:     7.43% churn (113 of 1,520)
```
**⚠️ CRITICAL:** Fiber optic has 2.2X higher churn than DSL

#### By Payment Method
```
Electronic Check:        45.29% churn (1,071 of 2,365)
Mailed Check:            19.20% churn (308 of 1,604)
Bank Transfer (Auto):    16.73% churn (258 of 1,542)
Credit Card (Auto):      15.25% churn (232 of 1,521)
```
**⚠️ WARNING:** Electronic check users have 3X higher churn

#### By Services Count
```
0 services:  21.5% churn
1 service:   45.8% churn (PEAK RISK!)
2 services:  35.8% churn
3 services:  27.4% churn
4 services:  22.4% churn
5 services:  12.5% churn
6 services:  5.3% churn (LOWEST RISK)
```
**KEY INSIGHT:** Customers with 1 service are highest risk; those with 5-6 services are very loyal

#### By Gender
```
Male:     26.80% churn
Female:   26.35% churn
```
**No significant difference between genders**

### 7.3 Churn-Retained Charge Comparison

| Metric | Churned | Retained | Difference |
|--------|---------|----------|-----------|
| Avg Monthly | $74.44 | $61.27 | +$13.17 ↑ |
| Avg Total | $1,532.33 | $2,555.79 | -$1,023.46 ↓ |

**Finding:** Churned customers paid MORE per month but left quickly (lower total lifetime value)

---

## 8. SUMMARY STATISTICS TABLE

### Numeric Variables Summary
```
Tenure (months):
  Count:  7,032
  Mean:   32.42
  Std:    24.56
  Min:    1
  Max:    72

Monthly Charges ($):
  Count:  7,032
  Mean:   64.80
  Std:    30.09
  Min:    18.25
  Max:    118.75

Total Charges ($):
  Count:  7,032
  Mean:   2,283.30
  Std:    2,282.30
  Min:    18.80
  Max:    8,684.80
```

---

## 9. DATA QUALITY CONCLUSION

### ✅ STRENGTHS
1. **Complete:** No significant missing values (0.16%)
2. **Unique:** No duplicate records
3. **Valid:** All values within expected ranges
4. **Balanced:** Good gender distribution
5. **Diverse:** Wide range of service types and contracts

### ⚠️ OBSERVATIONS
1. **Imbalanced services:** Most customers (31.5%) have zero add-on services
2. **Early churn concentration:** 31% of customers are newer than 12 months
3. **High churn segment:** Month-to-month contracts show dangerously high churn (42.71%)
4. **Payment risk:** Electronic check users are high churn risk (45.29%)

### 🔍 DATA QUALITY SCORE: **95/100** ✅

**Recommendation:** Dataset is **EXCELLENT** for analysis. Proceed with confidence to data analysis phase.

---

## 10. NEXT STEPS

The clean dataset is ready for:
✅ Exploratory data analysis  
✅ Visualization creation  
✅ Statistical hypothesis testing  
✅ Churn pattern identification  
✅ Business insight generation  
✅ Recommendation development  

**Cleaned dataset saved:** `/home/claude/telco_data_clean.csv`

---

**Report Prepared By:** AnalystLab Africa  
**Data Quality Certified:** ✅ APPROVED FOR ANALYSIS
