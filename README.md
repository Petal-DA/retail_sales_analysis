# Retail Sales Data Analysis

A data analytics project exploring the relationship between promotional markdowns, holidays, and weekly retail sales using historical data from 45 stores. This project uses Python (including Pandas, Plotly and Seaborn) to extract insights that support strategic decisions in retail performance and marketing planning.

The dataset includes:
- `stores_data_set.csv` — store type and size
- `features_data_set.csv` — markdowns, CPI, fuel price, temperature, unemployment, and holiday indicators
- `sales_data_set.csv` — weekly sales by store and department

Each file shares a common `Store` and `Date` column, which enabled effective merging into a single, unified dataset. After performing ETL operations—cleaning missing values and transforming date formats—we conducted a series of analyses to address key business questions:

- **Sales Trends**: Identify the impact of time and holidays on total weekly sales.

- **Holiday Impact**: Compare sales between holiday vs. non-holiday periods using both the original `IsHoliday` flag and our custom `AdjustedHoliday` column.
While the average weekly sales during holiday-affected periods are slightly higher, our line plots reveal that **specific holidays like Christmas drive sharp spikes in sales**. This suggests that not all holidays contribute equally to revenue. Averages may understate the importance of key events, so it's vital to explore **holiday type-level analysis** to truly understand their impact.

- **Markdown Analysis**: Evaluate the relationship between promotional markdowns and sales performance.

- **Store & Department Performance**: Understand which store types and departments perform best overall and during holiday periods.

- **Economic Correlations**: Explore the influence of CPI, fuel prices, and unemployment on sales using correlation matrices and visualisations.

This approach ensures the analysis is **business-relevant**, **data-driven**, and builds toward **actionable retail insights**.

## Analysis techniques

### Adjusted Holiday Flag

The original `IsHoliday` column did not always reflect real-world shopping behavior. For instance, weeks like December 23, 2011 showed massive sales spikes but were not flagged as holidays. 

To address this, a new `AdjustedHoliday` column was created. It marks weeks as holiday-impacted if they fall within 7 days of major events like Christmas, Thanksgiving, or the Super Bowl. While the Super Bowl isn't a federal holiday, it often influences retail trends in food and electronics, justifying its inclusion from a business perspective.

The next stage involves visualising these trends and evaluating how markdowns and economic indicators affect performance across store types and departments.


## Hypothesis

We hypothesise that holiday periods and promotional markdowns have a significant impact on weekly retail sales. Specifically, we expect to see sales spikes during major holidays and in weeks with high markdown values.

## Project Plan

This project followed a fast-paced project model using Jupyter Notebook for data exploration and GitHub for version control. The process included:

1. **Data Loading**: Loaded CSV files into dataframes using Pandas.
2. **ETL Process**:
   - Handled missing values using imputation (forward-fill for economic indicators).
   - Merged datasets on `Store` and `Date`.
   - Created a new `AdjustedHoliday` column for improved holiday accuracy.
3. **Exploratory Data Analysis**:
   - Plotted total sales trends over time.
   - Compared sales between holiday and non-holiday weeks.
   - Investigated markdown effectiveness.
   - Evaluated department/store type performance.
   - Analysed correlation with economic indicators.

 4. **Version Control**: Committed regularly using `git add .`, `git commit -m ""`, and `git push` to keep the project synched with GitHub.

## Tools & Libraries Used

- **Pandas**: Data manipulation and cleaning
- **Plotly**: Interactive data visualizations
- **Seaborn**: Statistical plots for deeper insights
- **VS Code + Jupyter Notebook**: Development environment
- **GitHub**: Version control and project tracking

## Ethical Considerations

- The dataset anonymised, and avoids any customer data exposure.
- We remain cautious in interpreting correlations as causations—economic data may be influenced by many external factors.
- Highlighted a potential flaw in the original dataset’s holiday labeling, demonstrating the importance of validating source data.

