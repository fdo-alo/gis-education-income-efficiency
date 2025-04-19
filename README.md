# 🌍 Education Efficiency & Income in California (2019–2023)

This repository explores how educational attainment (bachelor’s degree or higher) translates into household income across California counties using spatial analysis and LISA clustering (Local Indicators of Spatial Association).

## 🔍 Key Question
> Where in California does education **actually pay off** — and where does it **not**?

Using data from 2019–2023, this project investigates:
- How much median income counties generate **per percentage of educated population**
- Where education has **high or low returns**
- Which counties are **statistical outliers** compared to their neighbors

---

## 📊 Main Visualizations

### 1. Histogram: Education Efficiency Index
Shows the distribution of how efficiently counties convert education into income.
![Histogram](img/histogram_edu_efficiency_index.png)

### 2. Scatterplot: Median Income vs Efficiency Index
Highlights how some low-education counties (like San Benito) appear to perform well economically, while others do not.
![Scatterplot](img/scatter_income_vs_index.png)

### 3. Interactive Folium Map
Multiple layers to explore:
- Bachelor's Degree %
- Median Income ($)
- Income per % Educated
- LISA Clusters (High-High, Low-Low, etc.)

---

## 🎓 Education Efficiency Index
Defined as:
```python
income_edu_ratio = median_income / % with bachelor’s
divided by
income_unedu_ratio = median_income / % without bachelor’s
```

So:
```python
education_efficiency_index = income_edu_ratio / income_unedu_ratio
```

Interpretation:
- **>1**: Income is more concentrated in the **educated** population
- **<1**: Income is more concentrated in the **uneducated**
- **≈1**: Parity

---

## 🏛️ Spatial Analysis (LISA)
We used PySAL to detect counties that are:
- **High-High**: Efficient + surrounded by efficient
- **Low-Low**: Inefficient + surrounded by inefficient
- **High-Low**: Doing better than neighbors (e.g., San Benito)
- **Low-High**: Underperforming vs neighbors (e.g., Del Norte)

---

## 🧹 Key Findings
- Only ~6 counties truly benefit from education in income terms
- A large number of counties show **flat or no income difference** regardless of education
- In some counties, **uneducated populations generate more income per capita** than educated ones

> This helps explain why many people question the value of higher education: the data often supports their concern.

---

## 🔍 Data Sources
- Income & Education data (2019–2023): [NIMHD HDPulse - Minority Health and Health Disparities Indicators](https://hdpulse.nimhd.nih.gov/)
- California County Boundaries (GeoJSON): [Click That 'Hood](https://raw.githubusercontent.com/codeforgermany/click_that_hood/refs/heads/main/public/data/california-counties.geojson)

---

## 🚀 Tools Used
- Python
- GeoPandas
- PySAL
- Folium
- Seaborn / Matplotlib

---

## 🌟 Author
- Fernando Alonso (2025)

---

## 🚨 License
This project is open source and available under the MIT License.
