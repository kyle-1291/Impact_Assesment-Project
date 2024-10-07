# 📊 **Impact of net usage on dengue risk**

<style>
  h1, h2, h3 {
    color: #2A9D8F; 
  }
  .project-section {
    background-color: #F4F4F9;
    padding: 15px;
    border-radius: 5px;
  }
  .section-title {
    color: #264653; 
    font-size: 1.5em;
  }
  .highlight {
    color: #E76F51;
    font-weight: bold;
  }
</style>

<div class="project-section">

## 📝 **Project Overview**
This project aims to investigate whether using mosquito nets reduces the risk of contracting dengue among households in a district in India. The analysis is based on a dataset collected from **1,752 households**, containing variables related to environmental factors, individual health, and household characteristics.
## 🌍 **Research Context**
A special government program provides free mosquito nets to eligible households based on the following criteria:

- **Household Size:** More than 4 members.
- **Monthly Income:** Less than ₹7,000 per month.
  
# 📊 **Variable of Interest**

<style>
  .variable-list {
    padding: 15px;
    background-color: #F4F4F9;
    border-radius: 8px;
    margin-bottom: 20px;
  }
  .variable-item {
    padding: 10px;
    border-bottom: 1px solid #E0E0E0;
  }
  .variable-title {
    color: #2A9D8F; 
    font-weight: bold;
  }
  .note {
    color: #E76F51; 
    font-style: italic;
  }
</style>

<div class="variable-list">
  <div class="variable-item">
    <span class="variable-title">Dengue Risk (dengue_risk):</span>  
    The likelihood that someone in the household will be infected with dengue. Measured on a scale of 0–100, with higher values indicating higher risk.
  </div>

  <div class="variable-item">
    <span class="variable-title">Mosquito Net (net):</span>
    A binary variable indicating if the household used mosquito nets.
  </div>

  <div class="variable-item">
    <span class="variable-title">Mosquito Net Number (net_num):</span>
    Count of mosquito nets used in the house.
  </div>

  <div class="variable-item">
    <span class="variable-title">Income (income):</span>
    The household’s monthly income.  
    <span class="note">Note: Multiply the value by 10 to convert it to Indian Rupees.</span>
  </div>

  <div class="variable-item">
    <span class="variable-title">Eligible for Program (eligible):</span>  
    A binary variable indicating if the household is eligible for the free net program.  
    <span class="note">Note: Verify the eligibility column after making necessary adjustments for the income values.</span>
  </div>

  <div class="variable-item">
    <span class="variable-title">Nighttime Temperatures (temperature):</span>  
    The average temperature at night, in Celsius.
  </div>

  <div class="variable-item">
    <span class="variable-title">Health (health):</span>  
    Self-reported healthiness in the household. Measured on a scale of 0–100, with higher values indicating better health.
  </div>

  <div class="variable-item">
    <span class="variable-title">Number in Household (household):</span>  
    Number of people living in the household.
  </div>

  <div class="variable-item">
    <span class="variable-title">Insecticide Resistance (resistance):</span>  
    Some strains of mosquitoes are more resistant to insecticide, posing a higher risk of dengue infection. Measured on a scale of 0–100, with higher values indicating greater resistance.
  </div>
</div>


However, households are not automatically enrolled in the program, and participation is **voluntary**. As a result, there are discrepancies in net usage among eligible households. This scenario creates a natural observational setting where understanding causal relationships is challenging due to potential **self-selection bias** and **confounding factors**.

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
    - Construct a DAG to visually represent causal relationships.
    - Identify confounding variables and assess which paths need to be controlled for to achieve a valid causal estimate.

3. **Minimum Sufficient Adjustment Set:**
    - Based on the DAG, determine the variables that must be adjusted to isolate the causal effect of net usage on dengue risk.

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

This project is an excellent case study in handling **non-experimental data**, applying causal inference methods, and understanding the limitations of **observational studies**.

</div>
