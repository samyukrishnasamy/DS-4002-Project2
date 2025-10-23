## Metadata

### Goal
This section documents the context, origin, and structure of the UVA Tuition dataset used in this project.  
It ensures the dataset is transparent, reproducible, and ethically sourced, so others can interpret the analysis correctly.  
The information below describes how the in-state and out-of-state tuition data were obtained, processed, and combined to create the cleaned dataset used for analysis.

---

### 1. Data Summary
The dataset contains annual tuition and fee information for both **in-state** and **out-of-state** undergraduate students at the **University of Virginia**.  
It spans multiple academic years and provides a quantitative basis for analyzing tuition growth and cost disparities between Virginia residents and non-residents.  

After downloading the two datasets from UVA’s Institutional Research & Analytics (IRA) portal, the data were merged and cleaned to produce a single, consistent file.  
A new variable, `Tuition_Gap`, was created to represent the **difference between out-of-state and in-state tuition** for each academic year.  
This transformation enables clearer visualization of long-term affordability trends and institutional pricing policies.

---

### 2. Provenance
- **Source:** [UVA Institutional Research & Analytics (IRA)](https://ira.virginia.edu/university-data-home)  
- **Files Used:**  
  - `clean_in_state_tuition.csv` (In-state tuition and fees)  
  - `clean_out_state_tuition.csv` (Out-of-state tuition and fees)  
- **Access:** Publicly available under UVA’s Open Data Access policy.  
- **Processing Steps:**  
  1. Downloaded both datasets directly from the IRA website.  
  2. Cleaned column names and standardized year formats.  
  3. Merged the two datasets on matching academic years.  
  4. Computed `Tuition_Gap = Tuition_OutState - Tuition_InState`.  
  5. Verified numeric accuracy and removed duplicate records.

---

### 3. License
The data are publicly available through UVA’s **Open Data Access Policy**.  
Reuse and analysis for educational or research purposes are permitted with attribution to the University of Virginia’s **Institutional Research & Analytics (IRA)**.

---

### 4. Ethical Statements
This dataset includes only aggregated institutional data and contains **no personally identifiable information (PII)**.  
All data handling followed UVA’s Responsible Data Use principles.  
The dataset poses no ethical or privacy concerns.

---

### 5. Data Dictionary

| Column Name | Description | Type | Example |
|--------------|-------------|------|----------|
| `Year_InState` | Academic year corresponding to the in-state tuition record | String | 1970-71 |
| `Residency_InState` | Residency category for in-state students | String | In-State |
| `Totals_InState` | Total annual cost (tuition + required fees) for in-state students (USD) | Float | 484 |
| `Required Fees_InState` | Mandatory annual fees for in-state students (USD) | Float | 154 |
| `Tuition_InState` | Annual tuition cost for in-state students (USD) | Float | 330 |
| `Year_Start` | Starting year of the academic period | Integer | 1970 |
| `Year_OutState` | Academic year corresponding to the out-of-state tuition record | String | 1970-71 |
| `Residency_OutState` | Residency category for out-of-state students | String | Out-of-State |
| `Totals_OutState` | Total annual cost (tuition + required fees) for out-of-state students (USD) | Float | 1069 |
| `Required Fees_OutState` | Mandatory annual fees for out-of-state students (USD) | Float | 154 |
| `Tuition_OutState` | Annual tuition cost for out-of-state students (USD) | Float | 915 |
| `Tuition_Gap` | Difference between out-of-state and in-state tuition (USD) | Float | 585 |

---

### Exploratory Plots

#### Figure 1. Tuition Growth at the University of Virginia (1970–2024)
This line plot compares the historical increase in **in-state** and **out-of-state tuition** at UVA.  
It clearly illustrates how both have risen over time, with a sharper incline for out-of-state tuition, indicating a growing affordability gap.

![Tuition Growth Trend](tuition_growth_trend.png)

---

#### Figure 2. Tuition Gap Between Out-of-State and In-State Students (1970–2024)
This plot shows the **tuition gap** (out-of-state minus in-state tuition) over the same time period.  
The widening red curve highlights the growing difference in tuition costs between residency types, especially in the past two decades.

![Tuition Gap Trend](tuition_gap_trend.png)

