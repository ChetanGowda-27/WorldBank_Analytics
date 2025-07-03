

# 🌐 World Bank Analytics & Dashboard Project

Unlocking insights from global development data of the **G20 nations** using **World Bank Indicators**, **Python**, and **Tableau**.

---

## 📌 Project Objective

This project aims to:

* Analyze **key economic and social development indicators** for **G20 countries** between **2015 and 2020**.
* Extract and clean data directly from the **World Bank API**.
* Visualize trends and patterns through **interactive dashboards** using **Tableau**.
* Enable policy-relevant insights through data storytelling.

---

## 📈 Project Highlights

✅ Real-time data extraction using World Bank API
✅ Cleaned, transformed, and reshaped data using Python
✅ Key indicators such as GDP, life expectancy, FDI, inflation, and more
✅ Exported datasets for dashboard development
✅ Visualized with Tableau for actionable insights

---

## 🌍 G20 Countries Analyzed

| Country   | ISO Code |   | Country        | ISO Code |
| --------- | -------- | - | -------------- | -------- |
| Argentina | ARG      |   | Japan          | JPN      |
| Australia | AUS      |   | South Korea    | KOR      |
| Brazil    | BRA      |   | Mexico         | MEX      |
| Canada    | CAN      |   | Russia         | RUS      |
| China     | CHN      |   | Saudi Arabia   | SAU      |
| France    | FRA      |   | South Africa   | ZAF      |
| Germany   | DEU      |   | Turkey         | TUR      |
| India     | IND      |   | United Kingdom | GBR      |
| Indonesia | IDN      |   | United States  | USA      |
| Italy     | ITA      |   |                |          |

---

## 🧰 Tools & Technologies

| Tool/Tech                   | Purpose                                         |
| --------------------------- | ----------------------------------------------- |
| **Python**                  | Data extraction, cleaning, and transformation   |
| `wbdata`, `pandas`, `numpy` | API calls, data manipulation                    |
| `matplotlib`, `seaborn`     | Exploratory data visualization                  |
| **Jupyter Notebook**        | Interactive development environment             |
| **Excel**                   | Data formatting and export for Tableau          |
| **Tableau**                 | Final interactive dashboards and visualizations |
| **World Bank API**          | Primary source of development indicators        |

---

## 🧱 Indicators Used (Examples from 16+ Total)

| Indicator Name                  | Code                | Description                    |
| ------------------------------- | ------------------- | ------------------------------ |
| GDP per capita                  | `NY.GDP.PCAP.CD`    | National economic performance  |
| Life expectancy                 | `SP.DYN.LE00.IN`    | Healthcare and quality of life |
| Foreign Direct Investment (FDI) | `BX.KLT.DINV.CD.WD` | Economic openness              |
| Inflation, consumer prices      | `FP.CPI.TOTL.ZG`    | Price stability                |
| Urban population                | `SP.URB.TOTL.IN.ZS` | Urbanization trends            |
| CO₂ emissions                   | `EN.ATM.CO2E.KT`    | Environmental impact           |
| Population total                | `SP.POP.TOTL`       | Demographic size               |

> ✨ Full indicator list available in the notebook

---

## 📁 Project Workflow

### 1️⃣ Data Collection & Loading

```python
import wbdata
import pandas as pd
from datetime import datetime

# G20 country codes
g20_countries = [
    "ARG", "AUS", "BRA", "CAN", "CHN", "FRA", "DEU", "IND", "IDN",
    "ITA", "JPN", "KOR", "MEX", "RUS", "SAU", "ZAF", "TUR", "GBR", "USA"
]

# Time period
data_dates = (datetime(2015, 1, 1), datetime(2020, 12, 31))

# Selected indicators
indicators = {
    'NY.GDP.PCAP.CD': 'GDP_per_capita',
    'SP.DYN.LE00.IN': 'Life_expectancy',
    'BX.KLT.DINV.CD.WD': 'FDI',
    'FP.CPI.TOTL.ZG': 'Inflation',
    # ... additional indicators
}

# Fetch data
df = wbdata.get_dataframe(indicators, country=g20_countries, data_date=data_dates, convert_date=True)
df.reset_index(inplace=True)
df.rename(columns={"country": "Country", "date": "Year"}, inplace=True)
```

### 2️⃣ Data Cleaning

* Handle missing values
* Standardize formats
* Rename columns for clarity
* Group and aggregate where needed

### 3️⃣ Data Export

* Exported final DataFrame to Excel using `pandas.to_excel()`
* Structured format for Tableau compatibility

---

## 📊 Tableau Dashboards

Interactive dashboards include:

* 📈 **GDP vs CO₂ Emissions**: Economic growth vs environmental impact
* 🌍 **Life Expectancy Trends**: Across all G20 countries
* 💸 **FDI & Inflation Patterns**: Year-over-year changes
* 👥 **Population & Urbanization Growth**

> 🔗 *\[Insert your Tableau Public link here]*

---

## 📌 Key Insights

* Emerging economies showed stronger GDP per capita growth but higher volatility.
* Life expectancy improved steadily across most countries despite economic differences.
* Urbanization trends accelerated in developing G20 nations.
* High inflation and low FDI were observed in certain years due to global shocks.

---

## 🧭 How to Reproduce

1. Clone this repository
2. Install dependencies:

   ```bash
   pip install wbdata pandas numpy matplotlib seaborn openpyxl
   ```
3. Run the Jupyter Notebook:

   ```bash
   jupyter notebook world_bank_g20_analysis.ipynb
   ```
4. Open Tableau → Load the exported Excel file
5. Explore and customize dashboards

---

## 🚀 Future Improvements

* ✅ Add data for 2021–2024 as new data becomes available
* ✅ Automate Tableau export with live data pipeline
* ✅ Perform predictive modeling (e.g., future GDP forecasts)
* ✅ Enhance visualizations with animation and filters in Tableau

---

## 📚 References

* [World Bank Indicators API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation)
* [G20 Information - IMF](https://www.imf.org/en/About/Partners/Groups-of-Countries/G20)
* [Tableau Public](https://public.tableau.com/)

