# POPULATION INSIGHTS
### India & World Population Analysis and Visualization
**Subject:** Data Visualization using Python  
**Core Libraries:** Pandas · NumPy · Matplotlib  
**Project Type:** Comprehensive Data Analysis, Visualization, and Interactive Application  

---

## 📖 Executive Summary
This project investigates global and Indian demographic dynamics using real-world datasets sourced from the **World Bank**, the **Office of the Registrar General & Census Commissioner of India**, and the **United Nations World Population Prospects (UN WPP)**.

It demonstrates end-to-end data manipulation and visualization workflows:
1. **Pandas** for ingestion, handling missing values, pivoting, and tabular aggregation.
2. **NumPy** for vectorized percentage growth calculations, population changes, and Compound Annual Growth Rates (CAGR).
3. **Matplotlib** for generating all 7 required publication-grade visual charts with clean labeling, custom styling, annotations, and evidence-based insights.
4. **Streamlit** for an interactive web dashboard providing dynamic demographic explorations.

---

## 📂 Project Architecture

```
population_dvup/
│
├── data/                                  # Cleaned authentic datasets
│   ├── world_population_historical.csv    # World Bank annual series (1960 - 2024)
│   ├── world_population_wide.csv          # Pivoted wide format
│   ├── india_census_states.csv            # Official Census of India 2011 state data
│   ├── india_age_sex_structure.csv        # 5-year age cohorts by sex (Pyramid data)
│   └── global_density_growth.csv          # 20+ countries land area, density & decadal growth
│
├── src/                                   # Core reusable Python modules
│   ├── data_loader.py                     # Pandas data cleaning & validation
│   └── growth_calculator.py               # NumPy-vectorized Population Growth Calculator
│
├── charts/                                # Individual visualization scripts
│   ├── chart_01_line_chart.py             # Viz 1: Multi-year line chart (plt.plot)
│   ├── chart_02_pie_chart.py              # Viz 2: Population share pie chart (plt.pie)
│   ├── chart_03_horizontal_bar_chart.py   # Viz 3: Indian states ranking (plt.barh)
│   ├── chart_04_population_pyramid.py     # Viz 4: Age-sex demographic pyramid (plt.barh)
│   ├── chart_05_scatter_plot.py           # Viz 5: Population vs. Density (plt.scatter)
│   ├── chart_06_heatmap.py                # Viz 6: Decadal growth rate heatmap (plt.imshow)
│   └── chart_07_growth_rate_bar.py        # Viz 7: Cumulative growth bar chart (plt.bar)
│
├── outputs/                               # High-resolution (300 DPI) generated figures
│   ├── 01_line_chart.png
│   ├── 02_pie_chart.png
│   ├── 03_bar_chart_states.png
│   ├── 04_population_pyramid.png
│   ├── 05_scatter_plot.png
│   ├── 06_heatmap.png
│   └── 07_bonus_growth_bar.png
│
├── app.py                                 # Interactive Streamlit Web Dashboard
├── population_insights.ipynb              # Complete Jupyter Notebook for submission
├── generate_all_visualizations.py         # Master runner generating all charts in seconds
└── README.md                              # Complete academic documentation & viva guide
```

---

## 🛠️ How the Python Libraries are Applied

| Library | Role & Specific Functions Used |
|---|---|
| **Pandas** | `pd.read_csv()`, `df.pivot()`, `df.isna().sum()`, `df.sort_values()`, `df.describe()`, filtering year ranges and state subsets. |
| **NumPy** | `np.divide()` for rate calculations, `np.subtract()`, `np.power()` for CAGR, `np.mean()`, `np.sum()`, `np.interp()`, and vectorized arrays for high performance. |
| **Matplotlib** | `plt.plot()`, `plt.pie()`, `plt.barh()`, `plt.scatter()`, `plt.imshow()`, `plt.bar()`, `plt.annotate()`, custom colorbars, and subplots. |

---

## 📊 The 7 Visualizations & Evidence-Based Insights

### 1. Line Chart: Population Trajectory (India, China, USA)
- **Matplotlib Method:** `plt.plot()`
- **Output:** `outputs/01_line_chart.png`
- **Key Findings:**
  - In 1960, China led with ~667M, India had ~451M, and the USA had ~181M.
  - **The 2023 Demographics Pivot:** India surpassed China in 2023 with ~1.43 Billion people.
  - China's population has begun declining due to low fertility and rapid aging, while India maintains replacement fertility.

### 2. Pie Chart: Proportional Share of Combined Population (2024)
- **Matplotlib Method:** `plt.pie()` with `explode=[0.08, 0.05, ...]`
- **Output:** `outputs/02_pie_chart.png`
- **Key Findings:**
  - India (~32.6%) and China (~31.9%) together command **~64.8%** of the combined population of the top 10 nations.
  - The remaining 8 countries (USA, Indonesia, Pakistan, Nigeria, Brazil, Bangladesh, Russia, Japan) share the remaining ~35.2%.

### 3. Horizontal Bar Chart: Ranking Indian States by Population (Census 2011)
- **Matplotlib Method:** `plt.barh()`
- **Output:** `outputs/03_bar_chart_states.png`
- **Key Findings:**
  - **Uttar Pradesh** ranks #1 with **199.8 Million** residents (16.5% of India's population), rivaling Brazil.
  - The top 5 states (Uttar Pradesh, Maharashtra, Bihar, West Bengal, Madhya Pradesh) account for over **47%** of India's total populace.

### 4. Demographic Population Pyramid (India Age-Sex Structure)
- **Matplotlib Method:** Back-to-back `plt.barh()` with negative left axis and positive right axis.
- **Output:** `outputs/04_population_pyramid.png`
- **Key Findings:**
  - India displays a classical **Demographic Dividend** structure: a massive working-age bulge in the **15–39** age brackets.
  - The dependency ratio is favorably low, creating a productive workforce advantage.

### 5. Scatter Plot: Population Size vs. Population Density Across Regions
- **Matplotlib Method:** `plt.scatter()` with log-scale Y-axis and bubble sizing by $\sqrt{\text{Area}}$.
- **Output:** `outputs/05_scatter_plot.png`
- **Key Findings:**
  - **Bangladesh** is an extreme density outlier (>1,180 people/km²).
  - Continental giants like **Canada** and **Australia** maintain densities under 5 people/km².
  - Logarithmic scaling is essential to reveal clustering without distorting extreme outliers.

### 6. Heatmap: Annual Population Growth Rates Matrix (1980 – 2024)
- **Matplotlib Method:** Native `plt.imshow()` with `cmap='YlOrRd'`, colorbar, and cell text overlays.
- **Output:** `outputs/06_heatmap.png`
- **Key Findings:**
  - Shows the global demographic transition: almost every nation transitioned to paler hues (slower growth) over four decades.
  - **Sub-Saharan Africa** (Nigeria, Ethiopia) maintains the highest sustained fertility (>2.3% per year).
  - **Japan (-0.52%)**, **China (-0.10%)**, and **Russia (-0.19%)** have entered negative growth regimes.

### 7. Bonus Bar Chart: Cumulative Population Growth Comparison (2000 – 2024)
- **Matplotlib Method:** `plt.bar()` with green/blue for growth and red for decline.
- **Output:** `outputs/07_bonus_growth_bar.png`
- **Key Findings:**
  - **Nigeria** expanded by **+89.4%** in 24 years.
  - **India** expanded by **+36.45%**, adding **385 Million** people (more than the total US population).
  - **Japan** contracted by **-2.44%** (-3.09 Million people).

---

## 🧮 Bonus Feature: Population Growth Calculator

Implemented using vectorized NumPy math:

```python
import numpy as np

# Absolute Change
absolute_change = np.subtract(current_population, previous_population)

# Percentage Growth
growth_rate = np.multiply(
    np.divide(current_population - previous_population, previous_population),
    100.0
)

# Average Annual Change
annual_change = np.divide(current_population - previous_population, years_elapsed)

# Compound Annual Growth Rate (CAGR)
cagr = (np.power(np.divide(current_population, previous_population), 1.0 / years_elapsed) - 1.0) * 100.0
```

### Running the Calculator in CLI:
```bash
python src/growth_calculator.py
```

---

## 🚀 How to Run the Project

### 1. Generate All 7 High-Resolution Charts at Once:
```bash
python generate_all_visualizations.py
```
*Outputs are saved to `/outputs/` in 300 DPI PNG format.*

### 2. Launch the Interactive Streamlit Web Application:
```bash
streamlit run app.py
```
*Opens an interactive browser dashboard with filtering, dynamic calculations, and gallery views.*

### 3. Run Individual Charts:
```bash
python charts/chart_01_line_chart.py
python charts/chart_02_pie_chart.py
python charts/chart_03_horizontal_bar_chart.py
python charts/chart_04_population_pyramid.py
python charts/chart_05_scatter_plot.py
python charts/chart_06_heatmap.py
python charts/chart_07_growth_rate_bar.py
```

### 4. Interactive Jupyter Notebook:
Open `population_insights.ipynb` in VS Code or Jupyter Lab to run each cell interactively.

---

## 🎓 Viva Voce & Technical Exam Preparation

1. **Q: Why use `np.divide` instead of the `/` operator in Python?**  
   *A:* `np.divide` allows explicit handling of arrays and broadcasting, integrates safely with NumPy ufuncs, and handles division-by-zero rules (generating `inf` or `nan` instead of throwing unhandled exceptions).
2. **Q: How does `plt.imshow` generate a heatmap without Seaborn?**  
   *A:* `plt.imshow()` interprets a 2D numerical matrix as raster pixel data, interpolates colors through a colormap (`cmap`), and integrates with `plt.colorbar()` to produce native heatmaps without external dependencies.
3. **Q: How do you construct a Population Pyramid using `plt.barh`?**  
   *A:* By plotting two series sharing the same categorical y-axis (age groups). Male quantities are given negative values to grow leftward, and female quantities are positive to grow rightward. Custom tick formatters with `abs(x)` hide the negative signs on the x-axis.
4. **Q: What is the significance of applying a log scale on the scatter plot y-axis?**  
   *A:* Densities span from <5 people/km² (Australia, Canada) to >1,180 people/km² (Bangladesh). A linear scale collapses 90% of countries to the baseline; a log scale reveals relative proportional differences across all orders of magnitude.
