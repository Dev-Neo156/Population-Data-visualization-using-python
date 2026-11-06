# Population Insights: India & World Population Analysis

An exploratory data visualization project using Python to examine population trends, country comparisons, Indian state populations, age and sex structure, population density, and demographic growth. The analysis is presented in a Jupyter notebook and uses Pandas, NumPy, and Matplotlib.

## Project Contents

- `population_analysis.ipynb` — the notebook containing data loading, analysis, and visualizations.
- Five CSV datasets loaded by the notebook:
  - `world_population_historical.csv`
  - `world_population_wide.csv`
  - `india_census_states.csv`
  - `india_age_sex_structure.csv`
  - `global_density_growth.csv`

The notebook looks for CSV files in the current folder and common `data/` locations. If the files are not present locally, it downloads them from the project’s public data repository.

## Visualizations

1. Population trends for India, China, and the United States over time
2. Population shares of ten selected countries
3. The 15 most populous Indian states (2011 Census)
4. India’s age and sex population pyramid
5. Population versus density across global regions
6. Population growth-rate heatmap across selected countries and years
7. Cumulative population change from 2000 to 2024
8. Population distribution across ten selected countries, with a median marker

## Run the Notebook

### Google Colab

1. Upload `population_analysis.ipynb` to Google Colab or open it from your GitHub repository.
2. Connect to the internet so the notebook can install the required packages and download any missing CSV files.
3. Run the notebook cells in order.

### Local Jupyter

Use Python 3 with Jupyter installed. Open the notebook and run its setup cell; it installs the required data and plotting libraries. To avoid downloading the data, place the five CSV files in the notebook folder or a supported `data/` folder before running it.

## Libraries

- [Pandas](https://pandas.pydata.org/) — loading and preparing tabular data
- [NumPy](https://numpy.org/) — numerical operations
- [Matplotlib](https://matplotlib.org/) — charts and visualizations

## Data Sources

The notebook loads its CSV datasets from the public repository below when local copies are unavailable:

- [Population Data Visualization Using Python](https://github.com/Dev-Neo156/Population-Data-visualization-using-python)

The notebook’s charts include source notes for the relevant underlying population and census data. Check those notes when interpreting a particular figure.

## Notes

- Some population series combine benchmark estimates and interpolated values; the notebook explains this where relevant.
- The population pyramid uses age-cohort estimates, so its total may not exactly match the overall population figure for a given year.
- The histogram uses logarithmic population scaling and geometrically spaced bins to make the spread across countries easier to see.

## License

Add the license you intend to use before redistributing this project. Dataset terms may differ from the terms you choose for your code and notebook.
