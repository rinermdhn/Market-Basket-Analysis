# Market-Basket-Analysis

🛒 Market Basket Analysis (MBA) is a data analysis technique that uses transaction data to find associations between products. The process involves data preprocessing, exploratory data analysis, and Market Basket Analysis.

## Data Source
This analysis uses *Online Retail* dataset from the **UCI Machine Learning Repository**, which contains transaction data from a UK-based online shop. The dataset covers the period from December 2010 to December 2011 and contains 541,909 transactions with 8 features.

## Objectives
1. Analyze transaction data to understand customer purchase patterns.
2. Identify frequently co-purchased products.
3. Generate product recommendations based on product associations.

## Features
* `id`: A unique six-digit invoice number assigned to each transaction. If the invoice number starts with the letter 'C', it indicates a cancellation.
* `StockCode`: A unique five-digit product code assigned to each item.
* `Description`: The name or description of the product.
* `Quantity`: The number of units of the product purchased in a single transaction.
* `InvoiceDate`: The date and time when the transaction occurred.
* `UnitPrice`: The price per unit of the product, in British Pounds (GBP).

## Methodology
### Data Preprocessing
1. Data Type Conversion
   * `InvoiceDate`: Converted from **object** to **datetime64[ns]**.
   * `UnitPrice`: Converted from **object** to **float64**.
3. Handling Missing Values
   * `CustomerID`: Missing values were not dropped and treated as anonymous customers.
   * `Description`: Missing values were imputed based on matching `StockCode` values with existing non-null `Descriptions`.
4. Data Standardization
   * Replaced `Description` values for each `StockCode` with the most frequent description.
   * Standardized `StockCode` values to uppercase.
   * Converted `Description` values to title case.
   * Converted negative values in `Quantity` to absolute values.
5. Outliers Handling
   * Filtered transactions to include only those with `Quantity` ≤ 300 for further analysis.

### Exploratory Data Analysis (EDA)
* Analyzed and visualized the top 10 best-selling products, highest revenue-generating items, most active customers, and top countries by number of purchases.
* Analyzed monthly trends to understand seasonal purchasing behavior.

### Market Basket Analysis
* Due to data complexity, the analysis focused on the top 20 most-purchased products.
* Product associations were evaluated using three indicators: **support**, **confidence**, and **lift**.
* The analysis was performed on transaction data covering the entire period and seasonal purchasing patterns between September to December (Christmas or Winter Season).

## Results
The ranking of support values differs between the overall analysis and the Christmas period, indicating a change in seasonal purchasing trends. Higher transaction volumes at the end of the year and frequently purchased products during this period associated with Christmas or Winter Season preparations.

## Recommendation
- Apply insights from product association rules to develop targeted sales strategies.
- Utilize seasonal patterns (September to December) to design more effective promotional strategies.
- Suggested strategies to increase profitability:
   - Offer promotions on product combinations with high lift values.
   - Use bundling to boost sales of products with low support values.
