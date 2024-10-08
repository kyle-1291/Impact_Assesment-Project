# 📊 **Impact of net usage on dengue risk** 
<br>

## 📝 **Project Overview**
<p style="background-color:Tomato;">This project aims to investigate whether using mosquito nets reduces the risk of contracting dengue among households in a district in India. The analysis is based on a dataset collected from **1,752 households**, containing variables related to environmental factors, individual health, and household characteristics.</p>

### Data_Set : [mosquito_net.csv](https://github.com/kyle-1291/Impact_Assesment-Project/blob/8d54ade7169eb4f15e0e0b28f88f404edd50421c/Project_1-Impact_of_net_usage_on_dengu_risk/dengue_nets.csv)

---

## 🌍 **Research Context**
A special government program provides free mosquito nets to eligible households based on the following criteria:

- **Household Size:** More than 4 members.
- **Monthly Income:** Less than ₹7,000 per month.

However, households are not automatically enrolled in the program, and participation is **voluntary**. As a result, there are discrepancies in net usage among eligible households. This scenario creates a natural observational setting where understanding causal relationships is challenging due to potential **self-selection bias** and **confounding factors**.

---
  
## 📊 **Variable of Interest**
<div class="variable-list">
  <div class="variable-item">
    <span class="variable-title"><b>Dengue Risk</b> <sub>(dengue_risk)</sub> :</span>  
    The likelihood that someone in the household will be infected with dengue. Measured on a scale of 0–100, with higher values indicating higher risk.
  </div>
  <br>

  <div class="variable-item">
    <span class="variable-title"><b>Mosquito Net</b> <sub>(net)</sub> :</span>
    A binary variable indicating if the household used mosquito nets.
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Mosquito Net Number</b> <sub>(net_num)</sub> :</span>
    Count of mosquito nets used in the house.
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Income</b><sub>(income)</sub> :</span>
    The household’s monthly income.  
    <span class="note">Note: Multiply the value by 10 to convert it to Indian Rupees.</span>
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Eligible for Program</b> <sub>(eligible)</sub> :</span>  
    A binary variable indicating if the household is eligible for the free net program.  
    <span class="note">(Note: Verify the eligibility column after making necessary adjustments for the income values.)</span>
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Nighttime Temperatures</b> <sub>(temperature)</sub> :</span>  
    The average temperature at night, in Celsius.
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Health</b> <sub>(health)</sub> :</span>  
    Self-reported healthiness in the household. Measured on a scale of 0–100, with higher values indicating better health.
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Number in Household</b> <sub>(household)</sub> :</span>  
    Number of people living in the household.
  </div>
<br>
  <div class="variable-item">
    <span class="variable-title"><b>Insecticide Resistance</b> <sub>(resistance)</sub> :</span>  
    Some strains of mosquitoes are more resistant to insecticide, posing a higher risk of dengue infection. Measured on a scale of 0–100, with higher values indicating greater resistance.
  </div>
</div>
<br>

---

## ❓ **Research Question**
### **Primary Research Question:**  
Does using mosquito nets decrease an individual’s risk of contracting dengue?

The outcome variable is **dengue_risk**, measured on a scale of 0 to 100, with higher values indicating a greater risk. The treatment variable is **net**, indicating whether a household uses a mosquito net. Alternatively, we can use **net_num** to assess the intensity of net usage (number of nets in the household).

---

## 🔍 **Project Steps**
1. **Naive Model Analysis:**
    - Build a naive model to estimate the baseline relationship between net usage and dengue risk.
    - This step will help establish initial associations but will not yield a causal estimate due to potential confounding.
    
2. **Directed Acyclic Graph (DAG):**
    - Construction of  DAG to visually represent causal relationships.
    - Identify confounding variables and assess which paths need to be controlled for to achieve a valid causal estimate.

3. **Minimum Sufficient Adjustment Set:**
    - Based on the DAG, determine the variables that must be adjusted to isolate the causal effect of <strong>net usage</strong> on <strong>dengue risk</strong>.

4. **Comparing Binary vs. Count Treatment Variables:**
    - Explore whether using **net** (binary) or **net_num** (count) as the treatment variable influences the results.
    - Discuss the implications of different treatment variable specifications.

5. **Causal Estimate and Interpretation:**
    - Use causal inference methods such as **Matching** or **Difference-in-Differences (DiD)** to estimate the treatment effect.
    - Interpret the results and provide policy recommendations.

---

## 🗝️ **Key Considerations**
- **Selection Bias:** Households decide whether to participate in the free net program or buy their own nets, introducing potential selection bias.
- **Confounding Variables:** Variables like income, health, and insecticide resistance can confound the relationship between net usage and dengue risk.
- **Program Eligibility Check:** Adjust the dataset to ensure that the **eligible** variable correctly reflects program criteria after necessary income transformations.

---

## Software and libraries
- ![Python](https://img.shields.io/badge/python-3670A0?style=flat&logo=python&logoColor=ffdd54) :
numpy ;pandas; seaborn; statsmodels; combinations;  matplotlib; sklearn; r2py
- ![R](https://img.shields.io/badge/r-%23276DC3.svg?style=flat&logo=r&logoColor=white)  :
utils; ggdag; tidyverse; matchit; jtool; huxtable; daggity

This project is an excellent case study in handling **non-experimental data**, applying causal inference methods, and understanding the limitations of **observational studies**.

</div>
