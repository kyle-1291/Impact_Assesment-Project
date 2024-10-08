# 📊 **Impact of Workers' Compensation Policy Changes on Benifit Duration** 
<br>

## 📝 **Project Overview**
<p>This project aims to evaluate the effect of a policy change on the duration of workers’ compensation benefits in a specific state. In July 1980, the state of Kentucky raised the cap on weekly earnings covered by workers' compensation, impacting high-income workers by increasing their benefits. This study uses a Difference-in-Differences (DiD) approach to compare the duration of benefits for high-income (treatment group) and low-income workers (control group) before and after the policy change.</p>

---

## 🌍 **Research Context**
The impact of a policy change increasing the maximum covered weekly earnings on the duration of workers' compensation benefits for high-income workers.

---

## 📄 **Research Question**
Policy Effect on Benefit Duration: Does the new policy increase the time high-income workers stay on workers' compensation?
Impact on Log Duration: How does the policy affect the log-transformed duration of benefits, considering the skewness in the data?

---

## 💼 **Dataset Information**
The dataset contains 7,150 observations with 30 variables describing worker characteristics, injury types, and compensation amounts.
### Data_Set : [`injury.csv`](https://github.com/kyle-1291/Impact_Assesment-Project/blob/866f40c86f503821b25e9866ee6d7973d5e50069/Project_2-Impact%20of%20Workers'%20Compensation%20Policy%20Change%20on%20Benefit%20Duration/INJURY.DTA)

| **Variable**          | **Description** |
|-----------------------|-----------------|
| `durat`               | Duration of benefits (weeks) |
| `afchnge`             | = 1 if after policy change (post-1980) |
| `highearn`            | = 1 if high earner |
| `male`                | = 1 if male |
| `married`             | = 1 if married |
| `hosp`                | = 1 if hospitalization required |
| `indust`              | Industry of employment |
| `injtype`             | Type of injury |
| `age`                 | Age at the time of injury |
| `prewage`             | Previous weekly wage (1982 $) |
| `totmed`              | Total medical costs (1982 $) |
| `injdes`              | 4 digit injury description|
| `benefit`             | Real dollar value of benefit |
| `ky`                  | = 1 for Kentucky (0 for other states) |
| `mi`                  | = 1 for Michigan |
| `ldurat`              | Log-transformed duration of benefits |
| `afhigh`              | Interaction term (`afchnge` * `highearn`) |
| `lprewage`            | log(wage) |
| `lage`                | log(age) |
|`ltotmedd`             | log(`totmed`); = 0 `if totmed < 1`
| `head`                | = 1 if head injury |
| `neck`                | = 1 if neck injury |
| `upextr`              | = 1 if upper extremities injury |
| `trunk`               | = 1 if trunk injury |
| `lowback`             | = 1 if lower back injury |
| `lowextr`             | = 1 if lower extremities injury |
| `occdis`              | = 1 if occupational disease |
| `manuf`               | = 1 if manufacturing industry |
| `construc`            | = 1 if construction industry |
| `highlpre`            | (`highearn` * `lprewage`) |

---

## 🧪 Study Design
- **Treatment Group:**  
  High-income workers (for whom the pre-policy cap was binding).

- **Control Group:**  
  Low-income workers (not affected by the policy change).

- **Outcome Variables:**  
  - `durat`: Benefit duration in weeks  
  - `ldurat`: Log-transformed benefit duration

- **Key Interaction Term:**  
  `afhigh` = `afchnge` * `highearn`, indicating high-income workers post-policy change.

---

## 🛠️ **Methodology**
1. **Difference-in-Differences (DiD) Analysis**:
   Calculate the policy effect on durat and ldurat using DiD by manually constructing groups (before_treatment, after_treatment, before_control, after_control) and then running regression analyses.

2. **Regression Analysis without Controls**:
Estimate the impact of the policy change using a simple regression model without adjusting for any other variables.

3. **Regression with Controls**:
Include covariates such as `age`, `marital status`, `industry type`, and `injury severity` to isolate the effect of the policy change on `benefit duration`.

4. **Robustness Check with Other States**:
Use data from Michigan (MI) as an additional comparison group to validate results.

---

## Software and libraries
- ![R](https://img.shields.io/badge/r-%23276DC3.svg?style=flat&logo=r&logoColor=white)  :
`utils`; `tidyverse`; `broom`; `readr`; `stargazer`; `haven`; `ggplot`;`modelsummary`;`foreign`;`scales`

<p>This project provides insights into the unintended consequences of policy changes in workers' compensation benefits, balancing concerns between adequate compensation and potential moral hazard.</p>



