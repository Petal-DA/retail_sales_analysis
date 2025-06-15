# Retail Sales Data Analysis

A data analytics project exploring the relationships among **holidays**, **markdowns**, and **weekly retail sales** using historical data from 45 stores. The analysis was performed in Python using Pandas, Plotly, and Seaborn, with an emphasis on generating **business-relevant**, **data-driven**, and **actionable insights**.

---

## 📁 Dataset Overview

Three datasets were merged using common `Store` and `Date` columns:

- `stores_data_set.csv` — store type and size  
- `features_data_set.csv` — markdowns, CPI, fuel price, temperature, unemployment, and holiday flags  
- `sales_data_set.csv` — weekly sales by store and department  

---

## 🧠 Hypothesis

> Holiday periods and promotional markdowns significantly impact weekly retail sales. We expect to see sales spikes during key holiday weeks and when markdowns are applied.

---

## ⚙️ ETL Pipeline

1. **Data Loading**: Read all datasets into Pandas dataframes  
2. **Data Cleaning**:
   - Handled missing values (e.g. forward-filled CPI & Unemployment)
   - Checked for nulls and ensured type consistency
3. **Data Merging**: Combined datasets on `Store` and `Date`
4. **Feature Engineering**:
   - Created `AdjustedHoliday` column to capture weeks near real-world events like Christmas and Super Bowl
5. **Validation**: Verified merged dataset shape and column integrity

---

## 📊 Key Insights & Visualisations

### 🧭 Sales Trends Over Time

- A **line chart** of total weekly sales revealed **distinct seasonal spikes**, especially around late December (Christmas) and late November (Thanksgiving).
- **Original holiday labels** sometimes missed high-spike weeks (e.g., Dec 23, 2011), leading to the creation of a more context-aware `AdjustedHoliday` flag.

### 🏖️ Holiday Impact

- **Boxplot and line plots** showed that holidays do increase average sales, but spikes are **event-dependent**, not all holidays perform equally.
- The `AdjustedHoliday` column captures hidden spikes like Christmas Eve not labeled as holidays in the original data.

> ⚠️ **Note**: Averages may understate true holiday effects. It's key to analyse holidays individually rather than as a group; however, within the limits of this project, holidays were not further categorised or analysed by type.

---

### 📉 Markdown Impact Analysis

- **Correlation Heatmap** (lower triangle only) shows weak correlations between markdowns and `Weekly_Sales`
- `MarkDown1` and `MarkDown4` were strongly correlated with each other (0.84), but not with sales (~0.05)
- **Scatter plot** of `MarkDown1` vs `Weekly_Sales` showed high variance and little trend

> ✅ Promotions alone don’t drive sales. Timing or seasonality and store type may matter more.

---

### 🛒 Store & Department Performance

> 🏪 Store Type Performance
To understand how store type influences revenue, we analyzed weekly sales across Types A, B, and C:

📊 Finding: A time-series line plot revealed that Type A stores consistently outperformed Types B and C throughout the year.

💡 Insight: This suggests that larger-format stores (Type A) benefit from broader product selection or better location, making them key revenue drivers.

✅ Business Impact: For strategic growth, investing in or replicating the model of Type A stores could yield stronger ROI.

---

### 💬 Overall Visualisation: Animated Bubble Chart

To illustrate store-level sales evolution over time, we built an **interactive animated bubble chart**:

- **X-axis**: Store  
- **Y-axis**: Weekly Sales  
- **Bubble Size & Color**: Reflect sales volume  
- **Animation Frame**: Date  

🎯 **Reveals**:
- Which stores consistently outperform (Stores 4, 13, and 20; followed by stores 2, 10, 14, and 27)
- Seasonal surges (e.g., end-of-year spikes)
- Time-based store performance variance

---

## 🧪 Tools & Libraries Used

- **Pandas** — ETL and data manipulation  
- **Plotly** — Interactive and animated visualisations  
- **Seaborn** — Statistical heatmaps and scatter plots  
- **VS Code + Jupyter Notebook** — Analysis and development  
- **Git + GitHub** — Version control and Kanban board for project management  

---

## ✅ Ethical & Data Integrity Considerations

- Dataset is anonymised; no customer-level data present  
- Correlation ≠ causation: markdowns and economic indicators are interpreted cautiously  
- Adjusted for **dataset labeling issues** (e.g., misclassified holiday weeks)

---

## 📉 Feature Relevance

While the dataset includes columns like `Fuel_Price`, `CPI`, `Temperature`, and `Unemployment`, they were not prioritized in the final analysis for two reasons:

1. **Low Business Impact**: Initial correlation checks revealed **very weak relationships** between these indicators and weekly sales. Their fluctuations didn’t meaningfully align with revenue changes.

2. **Retail Context**: In the short-term retail setting, **consumer behavior is more influenced by promotions, holidays, and store operations** than macroeconomic variables. These features may be more relevant in long-term trend analysis or inflation-adjusted performance, which was beyond the scope of this project.

> 🎯 We focused on the variables that gave **clear, actionable insights** to business decision-makers—like holidays, store types, and markdown effectiveness.

---


