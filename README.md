# Retail Sales Data Analysis

A data analytics project exploring the relationships among **holidays**, **markdowns**, and **weekly retail sales** using historical data from 45 stores. The analysis was performed in Python using Pandas, Plotly, and Seaborn, with an emphasis on generating **business-relevant**, **data-driven**, and **actionable insights**.

## Dataset Content

This dataset was highly relevant to business questions, as it provided store-level weekly sales along with contextual features like holidays, markdowns, and economic indicators—all key inputs for analysing retail performance drivers.

Three datasets were merged using common `Store` and `Date` columns:

- `stores_data_set.csv` — store type and size
- `features_data_set.csv` — markdowns, CPI, fuel price, temperature, unemployment, and holiday flags
- `sales_data_set.csv` — weekly sales by store and department

## Business Requirements

- Identify the impact of holidays and markdowns on weekly sales
- Understand which store types and departments perform best
- Explore correlations between economic indicators and sales

## Hypothesis and how to validate?

> Holiday periods and promotional markdowns significantly impact weekly retail sales. We expect to see sales spikes during key holiday weeks and when markdowns are applied.

**Validation Steps**:

- Use line plots to identify seasonal spikes
- Compare weekly sales averages between holiday and non-holiday weeks
- Correlation analysis between markdown values and weekly sales

## Project Plan

- **Data Loading**: Read all datasets into Pandas dataframes
- **Data Cleaning**:
  - Handled missing values:
    - Forward-filled CPI & Unemployment to preserve economic trend continuity, as these two variables are only expected to change gradually from week to week 
    - Filled missing markdowns with 0 to reflect periods with no promotions (a guarded assumption)
  - Checked for nulls and ensured type consistency
- **Data Merging**: Combined datasets on `Store` and `Date`
- **Feature Engineering**:
  - Created an 'AdjustedHoliday' column to reflect real-world retail events: The original 'IsHoliday' flag missed critical high-spend weeks such as Christmas Eve. By identifying dates within 7 days of events like Christmas, Thanksgiving, and the Super Bowl, we captured additional spikes in sales that would otherwise go unflagged. This adjusted label offers a more business-aware understanding of holiday-driven demand patterns.
- **Validation**: Verified dataset shape and integrity post-merge

## Rationale to Map Business Requirements to Data Visualisations

- **Sales Trends**: Line charts for weekly sales
- **Holiday Impact**: Boxplots and enhanced line plots using `IsHoliday` and `AdjustedHoliday`
- **Markdown Analysis**: Correlation heatmaps and scatter plots
- **Store Performance**: Store-type specific line charts
- **Dynamic Insight**: Animated bubble plot to highlight store trends over time

## Analysis Techniques Used

- Correlation matrices
- Static and interactive visualizations
- Feature engineering to improve label accuracy

**Limitations**:

- Economic indicators showed low sales correlations
- Sunburst and Treemap plots were initially considered, but ultimately excluded due to rendering limitations

**AI Tools Used**:

- Code optimization
- Markdown formatting
- Visualisation strategy review

## Ethical Considerations

- Anonymized data, no customer details were included in data analysis
- Holiday mislabeling corrected with `AdjustedHoliday`
- Causal claims avoided; insights presented with context

## Dashboard Design

- Visuals are embedded throughout the Jupyter Notebook, each introduced and explained via contextual markdown for clarity.
- Titles, axis labels, legends, and interactivity were applied to ensure all charts could be understood by both technical and non-technical audiences.
- The **most impactful visualisations** include:
  - **Line plot of weekly sales over time**: Showed seasonal spikes and motivated the creation of the `AdjustedHoliday` flag.
  - **Boxplot comparing `IsHoliday` and `AdjustedHoliday` sales**: Highlighted the improved accuracy of our engineered feature.
  - **Animated Bubble Chart**: Offered a dynamic, store-level view of performance over time, revealing consistent top-performers.

These charts were aligned with the business goals and delivered strong narrative clarity and decision support.

## Unfixed Bugs

- None impacting outputs
- Sunburst and Treemap plots were initially explored, but rendering issues were encountered; thus, they were omitted from consideration.

## Development Roadmap

- Day 1: ETL and preliminary visuals
- Day 2: Advanced plots, insights, and dashboard polish
- Future: Feature-level filterable dashboards

## Main Data Analysis Libraries

- `pandas` — data wrangling
- `plotly.express` — interactive charts
- `seaborn` — statistical visualizations

## Credits

### Content

- Code Institute curriculum and facilitators
- OpenAI's ChatGPT for code support and visual guidance

### Media

- All plots created using Plotly and Seaborn within Jupyter Notebook

## Acknowledgements

- Thanks to Code Institute staff and community members, including the following individuals (listed alphabetically): Spencer Barriball; Julian Elliott; Emma Lamont; Kevin Loughrey; Niel McEwen; John Rearden.
- ChatGPT credited as a logic reviewer, design advisor, and debugging tool

---

> **Note**: All plots were made using Plotly and Seaborn.
