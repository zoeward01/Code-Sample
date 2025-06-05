Here's the same GitHub README section with all emojis removed for a cleaner, professional look:

---

## Jupyter Notebook Analysis: `ward_final.ipynb`

This repository includes a full analysis of the dataset `Country_Level_Results_by_Modality_Coarse_Age_and_Sex.txt` using Python and Jupyter Notebook. The notebook outlines a complete data processing, analysis, and visualization workflow.

---

### 1. File Import & Setup

* Imported essential Python libraries:

  * `pandas` for data manipulation
  * `numpy` for numerical operations
  * `matplotlib.pyplot` for data visualization
* Loaded a tab-delimited `.txt` file using `pd.read_csv()`
* Included `try-except` error handling to manage missing files and unexpected issues

---

### 2. Data Inspection

* Used `.info()` to examine data types and identify missing values
* Used `.head()` to preview the first few rows of the dataset

---

### 3. Data Cleaning

* Dropped columns with over 90% missing data
* Identified remaining missing values
* Converted numeric columns to the correct type and filled missing values with `0`
* Standardized text:

  * `Country`: converted to title case
  * `Modality`: converted to lowercase

---

### 4. Data Aggregation & Feature Engineering

Created a new column to calculate the total number of individuals tested:

```python
data_cleaned["Total_Tested"] = data_cleaned[years].sum(axis=1)
```

This aggregates HIV testing counts across all year-based columns.

---

### 5. Descriptive Statistics

* Used `.describe()` to summarize numeric variables
* Used `.value_counts()` to find the most common HIV testing modalities

---

### 6. Visualizations

1. **Total HIV Tests by Country**

   * Aggregated total tested by country
   * Visualized using a vertical bar chart

2. **Distribution of Modalities**

   * Counted test records by modality
   * Visualized using a horizontal bar chart

3. **Testing Trends in Angola**

   * Filtered the dataset for Angola
   * Created a line plot showing yearly testing trends

4. **Total Tested by Gender**

   * Counted individuals tested by gender (`Sex`)
   * Visualized with a gender-colored bar chart

---

### Key Skills Demonstrated

* Data ingestion and error handling
* Missing value treatment and numeric type conversion
* Categorical text cleaning and standardization
* Grouped aggregations and derived feature creation
* Plotting with `matplotlib` for categorical and time-series data

---

### Recommendations for Further Development

1. **Add Axis Labels & Units**
   Ensure all plots are clearly labeled and units (e.g., "Individuals", "Year") are included.

2. **Normalize by Population**
   Consider per capita testing to compare countries more fairly.

3. **Export Cleaned Data**
   Use `to_csv()` or `plt.savefig()` to save outputs.

4. **Add Interactivity**
   Tools like `plotly` or `dash` could enhance data exploration and sharing.

5. **Document Assumptions**
   Use Markdown cells to explain data decisions (e.g., 90% missingness cutoff).
