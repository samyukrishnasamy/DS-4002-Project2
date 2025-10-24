## Metadata

### Goal
Document the context, origin, structure, and limitations of the UVA tuition dataset so others can understand, reproduce, and ethically reuse the analysis. This reflects the most current cleaned/combined data used in the project.

---

## 1) Data Summary
This project analyzes annual tuition and required fees for **in-state** and **out-of-state** undergraduate students at the University of Virginia (UVA), spanning multiple academic years.  
Two source files (in-state and out-of-state) from UVA’s Institutional Research & Analytics (IRA) portal were cleaned and merged into a single combined file. A derived feature, `Tuition_Gap`, was created to quantify the difference between out-of-state and in-state tuition for each year.

**Files in this folder**
- `In_State_UVA_Tuition.csv` — source data (in-state)
- `Out_Of_State_UVA_tuition.csv` — source data (out-of-state)
- **`Combined_UVA_Tuition_Cleaned(in).csv` — final combined/cleaned file used for analysis**
- `tuition_growth_trend.png` — EDA plot (in-state vs out-of-state tuition over time)
- `tuition_gap_trend.png` — EDA plot (tuition gap over time)

---

## 2) Provenance
- **Source (public):** UVA Institutional Research & Analytics (IRA) – https://ira.virginia.edu/university-data-home  
- **Acquisition:** Both source CSVs were downloaded from the IRA website.
- **Processing overview:**
  1. Standardized column names and year formats in each source file.
  2. Merged the in-state and out-of-state tables on the matching academic year.
  3. Computed `Tuition_Gap = Tuition_OutState - Tuition_InState`.
  4. Removed duplicates and coerced numeric columns where needed.
- **Reproducibility:** The same steps can be re-run via scripts in the `SCRIPTS` folder to regenerate `Combined_UVA_Tuition_Cleaned(in).csv`.

---

## 3) License
Publicly available institutional data under UVA’s Open Data access policy. Reuse for education/research is permitted with attribution to UVA’s **Institutional Research & Analytics (IRA)**.

---

## 4) Ethical Statements
Data are aggregated at the institutional level and contain **no PII**. Handling follows UVA Responsible Data Use principles. No human subjects involvement.

---

## 5) Data Dictionary (for `Combined_UVA_Tuition_Cleaned(in).csv`)

| Column Name | Description | Type | Example |
|---|---|---|---|
| `Year_InState` | Academic year for the in-state record | string | 1970-71 |
| `Residency_InState` | Residency label for in-state students | string | In-State |
| `Totals_InState` | Total annual cost (tuition + required fees) for in-state students (USD) | float | 484 |
| `Required Fees_InState` | Mandatory annual fees for in-state students (USD) | float | 154 |
| `Tuition_InState` | Annual tuition for in-state students (USD) | float | 330 |
| `Year_Start` | Start year of the academic period | int | 1970 |
| `Year_OutState` | Academic year for the out-of-state record | string | 1970-71 |
| `Residency_OutState` | Residency label for out-of-state students | string | Out-of-State |
| `Totals_OutState` | Total annual cost (tuition + required fees) for out-of-state students (USD) | float | 1069 |
| `Required Fees_OutState` | Mandatory annual fees for out-of-state students (USD) | float | 154 |
| `Tuition_OutState` | Annual tuition for out-of-state students (USD) | float | 915 |
| `Tuition_Gap` | Difference in tuition (Out-of-State − In-State) in USD | float | 585 |

---

## 6) Explanatory Plots

**Figure 1. Tuition Growth at the University of Virginia (1970–2024)**  
In-state vs out-of-state tuition over time; illustrates steeper long-run increase for out-of-state.
  
<img width="2000" height="1200" alt="tuition_growth_trend" src="https://github.com/user-attachments/assets/dce0129d-b410-47ae-9a40-1ec35ec532a3" />


**Figure 2. Tuition Gap Between Out-of-State and In-State Students (1970–2024)**  
The widening difference `Tuition_OutState − Tuition_InState` across years.
  
<img width="2000" height="1200" alt="tuition_gap_trend" src="https://github.com/user-attachments/assets/f1b9d441-e0fe-4719-b7ad-9bf532f03181" />

**Figure 3. Distrubution of Tuition Growth at the University of Virginia (1970-2024)**
The varying distribution of In-State and Out-of-State Tution across years, illustrates widening disparities over time
!(../OUTPUT/01_exploratory_data_analysis/distribution_of_tuition.png)

---

### Special Note
This metadata file is regularly updated as the project progresses.  
It may differ from earlier versions because it reflects the most current data cleaning and analysis steps.

