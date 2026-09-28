# Rossmann Store Sales Analytics: Understanding Store Performance, Promotions, Customers, and Sales Trends

## Project Overview

Rossmann operates over 3,000 drug stores across seven European countries. This project analyzes historical sales data to uncover the factors influencing store performance, focusing on promotions, days of the week, store types, assortment strategies, and seasonal trends.

The project demonstrates a complete business analytics workflow, emphasizing data cleaning, data integration, feature engineering, and exploratory data analysis (EDA) to generate actionable business insights.

## The Data

The analysis combines two datasets:

- **`train.csv`**: Contains 1,017,209 rows of daily store-level sales data, including sales revenue, customer counts, store operating status, promotional activity, and holiday indicators.
- **`store.csv`**: Contains information on 1,115 stores, including store type, assortment level, competition distance, and promotional start dates.

The datasets are merged using a left join on the `Store` column, enriching the historical sales records with store-specific characteristics.

## Methodology

### 1. Data Cleaning and Integration

- Investigated missing values in both datasets.
- Handled missing competition distances and promotional dates using context-aware approaches.
- Merged the sales and store datasets using a left join on the `Store` identifier.
- Preserved valid observations while avoiding unnecessary row deletion.

### 2. Feature Engineering

Created additional variables to support deeper analysis:

- **Time-based features:** Year, quarter, month, day, week of year, and weekend indicators.
- **Customer metrics:** Sales per customer to examine average spending patterns.
- **Rolling metrics:** Seven-day rolling sales to identify underlying trends.
- **Growth metrics:** Daily percentage changes in sales to measure short-term fluctuations.

### 3. Exploratory Data Analysis (EDA)

Used statistical summaries and visualizations to investigate:

- Sales distributions and outliers.
- Performance differences across store types and assortment categories.
- Promotional activity across different days of the week.
- Monthly and seasonal sales patterns.
- Customer spending behavior and sales volatility.

## Key Findings and Visualizations

### 1. Sales Distributions and Outliers

Both daily sales and sales per customer exhibit substantial right skew. Some stores experience exceptionally high daily revenue, exceeding €40,000.

In contrast, sales per customer are more concentrated around €10, suggesting that variations in total daily revenue may be associated more closely with customer volume than with changes in average spending.

![Sales Distribution and Outlier Analysis](https://github.com/KeDataLab/rossman-sales-analysis/blob/main/Images/outlieranalysis.png)

### 2. Store Type and Assortment Performance

Store Type `b` demonstrates substantially higher average daily sales than the other store types.

Type `b` is also the only store type associated with Assortment `b`, making it important to distinguish store-type effects from assortment effects.

Among the standard store types (`a`, `c`, and `d`), stores carrying Assortment `c` consistently record higher average daily sales than those carrying Assortment `a`.

![Sales by Store Type and Assortment](https://github.com/KeDataLab/rossman-sales-analysis/blob/main/Images/Storetype.png)

### 3. The Impact of Promotions

Promotional activity is associated with higher sales across the working week. The median and interquartile ranges of daily sales are generally higher on promotional days from Monday through Friday.

The analysis also reveals that active promotions are absent on Saturdays and Sundays in the observed data. This presents an opportunity to investigate whether targeted weekend campaigns could increase sales.

These findings describe observed associations and do not, by themselves, establish causation.
![Promotional Impact on Sales](https://github.com/KeDataLab/rossman-sales-analysis/blob/main/Images/promoanalysis.png)

### 4. Seasonality and Time-Series Trends

Monthly trends and heatmap analyses reveal recurring seasonal patterns in store sales.

Sales experience a noticeable mid-year decline, particularly in July. In contrast, December records a substantial increase in revenue across store types, consistent with increased demand during the year-end holiday shopping period.

These patterns highlight the importance of accounting for seasonality when planning inventory, staffing, and promotional budgets.

![Monthly Sales Heatmap](https://github.com/KeDataLab/rossman-sales-analysis/blob/main/Images/heatmap.png)

## Strategic Business Recommendations

### 1. Test Weekend Promotional Campaigns

Evaluate targeted Saturday promotions in selected stores and compare their results against similar stores without the campaigns.

Measure incremental revenue, gross margin, transaction volume, and average basket value rather than sales revenue alone.

### 2. Evaluate Assortment Expansion

Investigate whether selected Assortment `a` stores would benefit from expanding their product ranges to include Assortment `c`.

Before making changes, assess shelf space, local demand, inventory costs, and gross margins.

### 3. Investigate the Store Type `b` Business Model

Examine differences in location, customer traffic, store size, product mix, and operating costs to understand the higher average sales observed in Type `b` stores.

Expansion decisions should consider profitability and return on investment, not revenue alone.

### 4. Investigate Basket-Size Growth Opportunities

Test product bundles, complementary-product recommendations, and point-of-sale promotions to determine whether average transaction value can be increased.

Evaluate the results using average basket value, gross margin, and customer response.

### 5. Develop Counter-Seasonal Summer Campaigns

Investigate whether seasonal product bundles, travel-sized products, and locally relevant promotions can support demand during the July sales decline.

Compare campaign performance against historical trends and suitable control stores.

### 6. Prepare for the December Sales Surge

Use historical demand patterns to inform inventory replenishment, supplier coordination, distribution capacity, and staffing schedules.

Begin preparations well before December to reduce stockouts and maintain service levels during peak demand.

## Tools and Libraries Used

- **Python:** Core programming language for data analysis.
- **Pandas:** Data cleaning, integration, transformation, and aggregation.
- **NumPy:** Numerical computations and feature engineering.
- **Matplotlib:** Static data visualization.
- **Seaborn:** Statistical visualization and distribution analysis.
- **Plotly:** Interactive charts and time-series exploration.
- **Jupyter Notebook:** Interactive analytical environment and documentation.

## Conclusion

This project demonstrates how raw retail sales data can be transformed into meaningful business insights through data cleaning, dataset integration, feature engineering, and exploratory analysis.

By examining promotional activity, store characteristics, customer spending, and seasonal trends, the analysis identifies opportunities for further investigation in retail operations, marketing, inventory planning, and assortment management.

The project also highlights an important distinction in business analytics: identifying a pattern is the first step; validating its commercial impact requires further testing and consideration of costs, margins, and operational constraints.
