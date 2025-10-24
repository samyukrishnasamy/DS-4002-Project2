# DS-4002-Project2
**Modeling UVA Tuition Trends (1970–2030) Using Time-Series Forecasting**
---

## Contents of Repository
This repository explores long-term trends in the University of Virginia’s tuition rates using time-series modeling techniques, including **Holt’s Linear Trend**, **ARIMA**, and **Prophet**. The project forecasts tuition gaps between in-state and out-of-state students through 2030, using historical data (1970–2024).

It contains:
- Source data and cleaned datasets  
- Jupyter Notebooks for each step of the workflow  
- Model outputs and forecast visualizations  
- Requirements file for dependency installation

---

## Section 1: Software and Platform  
### **Software**
Developed in **Python 3.11** using **Jupyter Notebook** for exploration, preprocessing, and model implementation.  

### **Key Libraries**
- **pandas** – for data cleaning, manipulation, and analysis  
- **numpy** – for numerical computation and array operations  
- **matplotlib / seaborn** – for data visualization and trend plots  
- **statsmodels** – for ARIMA and Holt’s Linear Trend implementation  
- **prophet** – for changepoint detection and forecasting  
- **itertools** – for parameter grid search (ARIMA tuning)  
- **os** – for file management and exporting model outputs

### **Platform**
- **Development Environment:** Jupyter Notebook on macOS  
- **Compatibility:** Runs on macOS, Windows, or Linux (requires listed packages)  

### **Installation**
Install all dependencies in a virtual environment:
#### macOS/Linux
``` bash 
python3 -m venv .venv
source .venv/bin/activate
```

#### Windows (PowerShell)
``` bash
py -m venv .venv
.venv\Scripts\Activate.ps1
```

# Install required packages
pip install -r requirements.txt

DS-4002-PROJECT2
├── DATA/                           # All datasets used in the study
│   ├── original_dataset/           # Raw UVA tuition data (1970–2024)
│   │   └── tuition_data_raw.csv
│   ├── clean/                      # Cleaned dataset (formatted for modeling)
│   │   └── tuition_clean.csv
│   └── splits/                     # Train/test splits
│       ├── train.csv
│       └── test.csv
│
├── OUTPUT/                         # Generated visualizations, forecasts, and reports
│   ├── 01_Exploratory_Plots/
│   │   ├── Tuition_Trend_1970_2024.png
│   │   └── Missing_Years_Check.png
│   ├── 02_Trend_Analysis/
│   │   ├── Rolling_Stats.png
│   │   ├── ACF_PACF.png
│   │   └── ADF_Results.csv
│   ├── 03_Holt_Linear_Trend/
│   │   ├── holt_test_predictions.csv
│   │   ├── holt_future_forecast_2030.csv
│   │   └── holt_gap_forecast.png
│   ├── 04_ARIMA_Forecast/
│   │   ├── arima_test_predictions.csv
│   │   ├── arima_future_forecast_2030_refit.csv
│   │   └── arima_gap_forecast_refit_vs_norefit.png
│   └── 05_Prophet/
│       ├── prophet_test_predictions.csv
│       ├── prophet_future_forecast_2030.csv
│       └── prophet_gap_forecast.png
│
├── SCRIPTS/                        # Jupyter Notebooks to reproduce workflow
│   ├── 01_exploratory_data_analysis.ipynb
│   ├── 02_trend_analysis.ipynb
│   ├── 03_holt_linear_trend.ipynb
│   ├── 04_arima_forecast.ipynb
│   └── 05_prophet_forecast.ipynb
│
├── requirements.txt                # Python dependencies
└── .gitignore                      # Ignore unnecessary files

### **Section 3: Instructions for Reproducing Results (run in this order)**
## Reproduction Steps (Run in Order)

### ** 01_exploratory_data_analysis.ipynb**
**What it does:**  
Performs EDA — line plots, missing year checks, and descriptive statistics.

**Outputs:**
OUTPUT/01_Exploratory_Plots/Tuition_Trend_1970_2024.png

### **02_trend_analysis.ipynb**
**What it does:**  
Conducts time-series diagnostics on tuition gap.  
Uses ADF test, rolling mean/variance, and ACF/PACF plots.

**Outputs:**
OUTPUT/02_Trend_Analysis/Rolling_Stats.png
OUTPUT/02_Trend_Analysis/ACF_PACF.png
OUTPUT/02_Trend_Analysis/ADF_Results.csv

### **03_holt_linear_trend.ipynb**
**What it does:**  
Fits Holt’s Linear Trend model (1970–2013 training window) and forecasts through 2030.

**Outputs:**
OUTPUT/03_Holt_Linear_Trend/holt_gap_forecast.png
OUTPUT/03_Holt_Linear_Trend/holt_future_forecast_2030.csv

### **04_arima_forecast.ipynb**
**What it does:**  
Performs grid search for ARIMA(p,d,q) → selects best model by AIC.  
Trains ARIMA(0,2,2) model and evaluates on 2014–2023 data.

**Outputs:**  
OUTPUT/04_ARIMA_Forecast/arima_gap_forecast_refit_vs_norefit.png
OUTPUT/04_ARIMA_Forecast/arima_future_forecast_2030_refit.csv

### **05_prophet_forecast.ipynb**
**What it does:**  
Implements Prophet model with automatic changepoint detection.  
Captures major shifts (e.g., 1988, 2003) and forecasts through 2030.

**Outputs:**
OUTPUT/05_Prophet/prophet_gap_forecast.png
OUTPUT/05_Prophet/prophet_future_forecast_2030.csv

