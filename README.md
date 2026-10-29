# POPULATION INSIGHTS
### India & World Population Analysis and Visualization

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-013243.svg)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-11557c.svg)](https://matplotlib.org/)

**Subject:** Data Visualization using Python  
**Core Libraries:** Pandas · NumPy · Matplotlib  
**Project Type:** Comprehensive Demographic Analysis & Jupyter Notebook  

---

## 📖 Executive Summary

This project conducts an in-depth empirical investigation of global and Indian demographic trends using authentic datasets sourced from the **World Bank**, the **Office of the Registrar General & Census Commissioner of India**, and the **United Nations World Population Prospects (UN WPP 2024)**.

The entire workflow is packaged into an end-to-end, reproducible **Jupyter Notebook (`population_insights.ipynb`)** supported by benchmark CSV datasets in the `data/` folder:

1. **Pandas:** Utilized for data ingestion, cleaning, tabular reshaping, pivoting, group-by aggregations, and demographic summarization.
2. **NumPy:** Powers high-performance vectorized operations for percentage growth rates, absolute population changes, and Compound Annual Growth Rates (CAGR).
3. **Matplotlib:** Employs core Matplotlib plotting interfaces (`plt.plot`, `plt.pie`, `plt.barh`, `plt.scatter`, `plt.imshow`, `plt.bar`) to generate 7 publication-grade demographic charts with custom color palettes, annotations, and statistical insights.

---

## 📂 Repository Architecture

This repository is streamlined to contain the core analytical notebook and all raw benchmark datasets:

```
population_dvup/
│                                 
├── world_population_historical.csv    # World Bank annual time series (1960 – 2024)
├── world_population_wide.csv          # Pivoted wide-format country-by-year matrix
├── india_census_states.csv            # Census of India 2011 state-level demographic records
├── india_age_sex_structure.csv        # 5-year age cohorts divided by sex (Pyramid data)
├── global_density_growth.csv          # 20 diverse economies: area, density & decadal growth
│
├── population_insights.ipynb              # Complete Jupyter Notebook (Code, 7 Visualizations & Insights)
└── README.md                              # Complete academic documentation & viva preparation guide
```

---

## 📁 Datasets Description (`data/`)

All datasets are included in CSV format for transparent auditability and cross-tool analysis:

| File Name | Primary Source | Rows × Cols | Description |
|---|---|---|---|
| `world_population_historical.csv` | World Bank (`SP.POP.TOTL`) & UN WPP | 650 × 3 | Long-format annual population figures (1960–2024) across 10 benchmark nations (India, China, USA, Indonesia, Pakistan, Nigeria, Brazil, Bangladesh, Russia, Japan). |
| `world_population_wide.csv` | World Bank & UN WPP | 10 × 66 | Pivoted cross-sectional matrix showing countries along rows and years (1960–2024) along columns. |
| `india_census_states.csv` | Office of the Registrar General, India | 24 × 8 | Official Census of India 2011 state records: 2001 & 2011 population, land area (km²), sex ratio, literacy rate, decadal growth %, and density. |
| `india_age_sex_structure.csv` | Census of India / UN Population Division | 17 × 3 | 5-year demographic age cohorts (0–4 through 80+) disaggregated into male and female counts in millions. |
| `global_density_growth.csv` | UN WPP 2024 & World Bank | 20 × 11 | Land area (km²), 2024 population, density (people/km²), and decadal population growth rates spanning 1980–2024 for 20 nations across all world regions. |

> **Note:** `population_insights.ipynb` is designed to be completely self-contained. It can read these CSV files directly from the `data/` folder and also includes built-in dataset builders so it can execute autonomously in cloud environments like Google Colab without manual file uploads.

---

## 🛠️ How Core Python Libraries are Applied

| Library | Key Functions & Methods Used | Project Application |
|---|---|---|
| **Pandas** | `pd.read_csv()`, `df.pivot()`, `df.to_numpy()`, `df.sort_values()`, `df.describe()`, `df.head()` | Data structure modeling, state ranking, filtering time windows, and summary statistics. |
| **NumPy** | `np.divide()`, `np.subtract()`, `np.multiply()`, `np.power()`, `np.interp()`, `np.asarray()`, `np.round()` | Vectorized population delta calculations, decadal growth rates, and Compound Annual Growth Rate (CAGR) math. |
| **Matplotlib** | `plt.plot()`, `plt.pie()`, `plt.barh()`, `plt.scatter()`, `plt.imshow()`, `plt.bar()`, `plt.annotate()`, `plt.colorbar()` | Production of all 7 visualization figures with customized styling, spines, gridlines, dual-axes, and color mappings. |

---

## 📊 The 7 Visualizations & Key Findings

All charts are generated and rendered inline directly within `population_insights.ipynb`:

### 1. Line Chart: Population Trajectory (India, China, USA — 1960 to 2024)
- **Matplotlib Method:** `plt.plot()` with custom line styles, marker highlights, and direct curve labeling.
- **Location in Notebook:** Section: *Visualization 1 — Line Chart*
- **Key Demographic Insights:**
  - In 1960, China led globally with ~667M people, India had ~451M, and the USA stood at ~181M.
  - **The 2023 Historical Crossover:** India officially surpassed China in early 2023 at approximately ~1.43 Billion citizens.
  - China's growth has turned negative due to sustained sub-replacement fertility rates, while India maintains steady population expansion near replacement level.

### 2. Pie Chart: Proportional Share of Combined Top-10 Population (2024)
- **Matplotlib Method:** `plt.pie()` with `autopct='%1.1f%%'`, `explode=[0.08, 0.05, ...]`, and custom slice coloring.
- **Location in Notebook:** Section: *Visualization 2 — Pie Chart*
- **Key Demographic Insights:**
  - **India (~32.6%)** and **China (~31.9%)** together account for nearly **65%** of the combined population of the top 10 nations.
  - The remaining 8 countries (USA, Indonesia, Pakistan, Nigeria, Brazil, Bangladesh, Russia, Japan) collectively divide the remaining ~35%.

### 3. Horizontal Bar Chart: Ranking Indian States by Population (Census 2011)
- **Matplotlib Method:** `plt.barh()` with value labels placed on bar ends and custom gradient coloring.
- **Location in Notebook:** Section: *Visualization 3 — Horizontal Bar Chart*
- **Key Demographic Insights:**
  - **Uttar Pradesh** ranks #1 with **199.8 Million** residents (16.5% of India's population), comparable to the entire populace of Brazil.
  - The top 5 states (Uttar Pradesh, Maharashtra, Bihar, West Bengal, Madhya Pradesh) account for more than **47%** of India's total populace.

### 4. Demographic Population Pyramid: India Age-Sex Structure
- **Matplotlib Method:** Dual back-to-back `plt.barh()` sharing the categorical age cohort Y-axis. Negative values are used for males (expanding leftward) and positive values for females (expanding rightward), with custom axis formatters (`abs(x)`).
- **Location in Notebook:** Section: *Visualization 4 — Population Pyramid*
- **Key Demographic Insights:**
  - Displays a pronounced **Demographic Dividend** structure: a massive bulge in the working-age population (ages **15–39**).
  - The narrowing base (ages 0–9) reflects declining fertility rates approaching the national replacement level of 2.0.

### 5. Scatter Plot: Population Size vs. Population Density Across Global Economies
- **Matplotlib Method:** `plt.scatter()` with a logarithmic Y-axis (`plt.yscale('log')`) and bubble sizes proportional to $\sqrt{\text{Land Area}}$.
- **Location in Notebook:** Section: *Visualization 5 — Scatter Plot*
- **Key Demographic Insights:**
  - **Bangladesh** is a massive density outlier with over **1,180 people/km²**.
  - Landmass giants like **Canada** and **Australia** maintain extremely sparse settlements (<5 people/km²).
  - Logarithmic scaling is mathematically essential; a linear axis compresses 90% of countries to the baseline due to extreme outliers.

### 6. Heatmap Matrix: Decadal Population Growth Rates (1980 – 2024)
- **Matplotlib Method:** Native `plt.imshow()` with `cmap='YlOrRd'`, `plt.colorbar()`, and numerical text annotations overlaid inside every cell.
- **Location in Notebook:** Section: *Visualization 6 — Heatmap*
- **Key Demographic Insights:**
  - Illustrates the global demographic transition: almost all major nations exhibit paler hues (slowing growth) across successive decades.
  - **Sub-Saharan Africa** (Nigeria, Ethiopia) maintains the highest sustained fertility (>2.3% annually).
  - **Japan (-0.52%)**, **China (-0.10%)**, and **Russia (-0.19%)** have officially entered population contraction regimes.

### 7. Cumulative Growth Comparison Bar Chart (2000 – 2024)
- **Matplotlib Method:** `plt.bar()` with green/teal bars for positive expansion and crimson bars for population shrinkage.
- **Location in Notebook:** Section: *Visualization 7 — Cumulative Growth Bar Chart*
- **Key Demographic Insights:**
  - **Nigeria** expanded by **+89.4%** in 24 years, virtually doubling its population.
  - **India** expanded by **+36.45%**, adding **385 Million** people in 24 years (surpassing the entire population of the United States).
  - **Japan** contracted by **-2.44%** (-3.09 Million people), highlighting the demographic challenges of super-aging nations.

---

## 🧮 Bonus Feature: NumPy Population Growth Calculator

Implemented and verified directly in **Cell 2** of `population_insights.ipynb`, using vectorized NumPy math:

```python
import numpy as np

def calculate_growth(previous_pop, current_pop, years_elapsed=1):
    prev = np.asarray(previous_pop, dtype=np.float64)
    curr = np.asarray(current_pop, dtype=np.float64)

    # 1. Absolute Population Change
    abs_change = np.subtract(curr, prev)

    # 2. Percentage Growth Rate
    pct_growth = np.multiply(np.divide(abs_change, prev), 100.0)

    # 3. Average Annual Addition
    annual_change = np.divide(abs_change, years_elapsed)

    # 4. Compound Annual Growth Rate (CAGR)
    cagr = (np.power(np.divide(curr, prev), 1.0 / years_elapsed) - 1.0) * 100.0

    return {
        "absolute_change": abs_change,
        "percentage_growth": pct_growth,
        "annual_change": annual_change,
        "cagr_percent": cagr
    }
```

This function operates transparently on single scalars or multi-dimensional NumPy arrays and handles edge cases without raising unhandled runtime exceptions.

---

## 🚀 How to Run the Project

You can run `population_insights.ipynb` using any standard Python/Jupyter environment:

### Method 1: Google Colab (Recommended for Fast Evaluation)
1. Navigate to [Google Colaboratory](https://colab.research.google.com/).
2. Select **Upload** and choose `population_insights.ipynb` (or open it directly via GitHub URL).
3. Click **Runtime** > **Run all** (`Ctrl + F9`).
4. All dependencies are handled automatically by the setup cell, and all 7 visualizations render inline immediately.

### Method 2: Local Jupyter Notebook / JupyterLab
1. Clone or download this repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Install the required libraries:
   ```bash
   pip install pandas numpy matplotlib jupyter
   ```
3. Start the Jupyter server:
   ```bash
   jupyter notebook population_insights.ipynb
   ```
4. In the Jupyter interface, click **Cell** > **Run All**.

### Method 3: Visual Studio Code
1. Open the cloned project folder in VS Code.
2. Ensure the **Jupyter** and **Python** extensions are installed.
3. Open `population_insights.ipynb`.
4. Select your Python 3.9+ kernel at the top right.
5. Click **Run All** at the top of the notebook.

---

## 🎓 Viva Voce & Technical Exam Preparation

1. **Q: Why use `np.divide()` instead of standard Python `/` division?**  
   *A:* `np.divide()` provides vectorized execution over large arrays without Python loop overhead, supports broadcasting across mismatched dimensions, and manages division-by-zero safely according to IEEE floating-point rules (producing `inf` or `nan` instead of halting execution with a `ZeroDivisionError`).

2. **Q: How does `plt.imshow()` construct a heatmap without external libraries like Seaborn?**  
   *A:* `plt.imshow()` treats a 2D numerical matrix as raster pixel data, maps values onto a continuous color map (`cmap`), and interfaces with `plt.colorbar()` to display the scale. Cell values are overlaid via `plt.text()` in a double loop.

3. **Q: How is a dual-sided Population Pyramid constructed using `plt.barh()`?**  
   *A:* By plotting male and female demographic series along a shared categorical Y-axis (age groups). Male values are multiplied by `-1` so the bars grow leftward, while female values remain positive and grow rightward. The X-axis tick labels are formatted with `abs(x)` to eliminate negative signs.

4. **Q: Why is a logarithmic scale applied to the density axis in the scatter plot?**  
   *A:* Population densities vary across multiple orders of magnitude—from under 5 people/km² (Australia, Canada) to over 1,180 people/km² (Bangladesh). A linear scale collapses over 90% of countries against the bottom axis; a logarithmic scale (`plt.yscale('log')`) distributes points proportionally, revealing clustering and trends across all density tiers.

5. **Q: What is the Compound Annual Growth Rate (CAGR) formula used in the calculator?**  
   *A:* 
   $$\text{CAGR} = \left( \frac{\text{Ending Population}}{\text{Beginning Population}} \right)^{\frac{1}{n}} - 1$$
   where $n$ is the number of elapsed years. In NumPy, this is computed vectorially via:  
   `(np.power(np.divide(curr, prev), 1.0 / years) - 1.0) * 100.0`.

---

## 📜 Academic Integrity & Data Attribution

All datasets and demographic figures utilized in this project are aligned with public benchmark records from:
- **World Bank Open Data:** Indicator `SP.POP.TOTL` (Total Population)
- **Census of India 2011:** Office of the Registrar General & Census Commissioner, Ministry of Home Affairs, Government of India
- **United Nations Population Division:** World Population Prospects (UN WPP 2024 Revision)
