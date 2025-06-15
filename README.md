# Retail Sales Data Analysis

A data analytics project exploring the relationship between promotional markdowns, holidays, and weekly retail sales using historical data from 45 stores. This project uses Python (including Pandas, Plotly and Seaborn) to extract insights that support strategic decisions in retail performance and marketing planning.

The dataset includes:
- `stores_data_set.csv` — store type and size
- `features_data_set.csv` — markdowns, CPI, fuel price, temperature, unemployment, and holiday indicators
- `sales_data_set.csv` — weekly sales by store and department

Each file shares a common `Store` and `Date` column, which enabled effective merging into a single, unified dataset. After performing ETL operations—cleaning missing values and transforming date formats—we conducted a series of analyses to address key business questions:

- **Sales Trends**: Identify the impact of time and holidays on total weekly sales.
- **Holiday Impact**: Compare sales between holiday vs. non-holiday periods using both the original `IsHoliday` flag and our custom `AdjustedHoliday` column.
- **Markdown Analysis**: Evaluate the relationship between promotional markdowns and sales performance.
- **Store & Department Performance**: Understand which store types and departments perform best overall and during holiday periods.
- **Economic Correlations**: Explore the influence of CPI, fuel prices, and unemployment on sales using correlation matrices and visualisations.

This approach ensures the analysis is **business-relevant**, **data-driven**, and builds toward **actionable retail insights**.


### Adjusted Holiday Flag

The original `IsHoliday` column did not always reflect real-world shopping behavior. For instance, weeks like December 23, 2011 showed massive sales spikes but were not flagged as holidays. 

To address this, a new `AdjustedHoliday` column was created. It marks weeks as holiday-impacted if they fall within 7 days of major events like Christmas, Thanksgiving, or the Super Bowl. While the Super Bowl isn't a federal holiday, it often influences retail trends in food and electronics, justifying its inclusion from a business perspective.
