# 🌆 London Air Quality Forecasting: NO₂ & PM₂.₇ Analysis with Prophet

A time-series analysis and forecasting project examining nitrogen dioxide ($\text{NO}_2$) and fine particulate matter ($\text{PM}_{2.5}$) levels at the Kensington and Chelsea (North Kensington) monitoring site in London (2010–2023).

This project leverages **Facebook Prophet** to model multi-year trends, weekly and yearly seasonality, and the impact of key external factors—such as Bank Holidays, Bonfire Night, and additional pollutant regressors.

---

## 📌 Project Overview

* **Target Variable:** $\text{NO}_2$ levels (`no2_level`)
* **Additional Regressor:** $\text{PM}_{2.5}$ levels (`pm25_level`)
* **Location:** Kensington and Chelsea - North Ken
* **Time Range:** 2010 – 2023
* **Model:** Facebook Prophet with custom holiday effects & external regressor integration

### Key Features
- **Data Cleaning & Preprocessing:** Linear interpolation and backward filling for missing sensor readings.
- **Time-Series Train-Test Split:** Chronological 80/20 train-test split to prevent temporal data leakage.
- **Custom Holiday Windows:** Incorporation of official UK/England Bank Holidays alongside custom multi-day windows for Bonfire Night ($\text{PM}_{2.5}$ smoke lingering effects).
- **Multivariate Forecasting:** Incorporating $\text{PM}_{2.5}$ as an extra regressor alongside $\text{NO}_2$ target modeling.

---

## 📊 Key Findings & Insights

* **Overall Trend:** $\text{NO}_2$ concentrations show a significant long-term decline from 2010 (~34) down to 2023 (~19), with a notable plateau around 2015–2017 before dropping sharply from 2018 onward.
* **Weekly Seasonality:** Air pollution consistently peaks mid-week (Wednesday) and bottoms out on Sundays due to traffic volume changes.
* **Impact of Regressors:** Including $\text{PM}_{2.5}$ as an external regressor captures shared environmental and meteorological variations, refining the underlying trend trajectory compared to univariate models.

---

## 🛠️ Project Structure

```text
├── data/
│   └── london_air_quality_2010_2023_top5_sites.csv   # Raw dataset
├── notebook.ipynb                                    # Main analysis & Prophet pipeline
├── README.md                                         # Project documentation
└── requirements.txt                                  # Python dependencies
