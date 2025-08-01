# Low-Cost-vs.-Non-Low-Cost-Airline-Analysis
## L&N Airline Analysis: Low-Cost vs. Non-Low-Cost Carriers
_This Power BI project compares low-cost and traditional airlines using metrics like EBIT, fleet age, and passenger yield. It provides visual insights and recommendations to improve airline profitability and efficiency_

## Table of Contents
+ Project Overview
+ Data Source
+ Importance of the Project
+ Tools Used
+ Business Questions
+ Data Overview
+ Analysis Breakdown
+ SQL Query Used
+ Data Visualization
+ Recommendations

## Project Overview
  This project focuses on analyzing and comparing low-cost and non-low-cost (traditional) airlines using key business metrics. The objective is to evaluate performance, efficiency, and profitability between the two types of carriers.
Using a structured dataset, I performed data cleaning in Excel, applied SQL for metric calculation and grouping, and built a comprehensive Power BI dashboard to visualize insights.
+ Key metrics analyzed include:
+ EBIT (Earnings Before Interest and Taxes)
+ Load Factor
+ Number of Routes
+ Passenger Yield
+ Average Fleet Age
The final dashboard enables interactive exploration and clear comparisons between airline categories, aiding in performance evaluation and decision-making.

## Importance of the Project
+ Business Insight: Helps airline stakeholders understand where low-cost and traditional carriers differ operationally and financially.

+ Decision Support: Offers actionable recommendations to optimize profitability, such as fleet investment, pricing strategy, and route planning.

+ Skill Application: Demonstrates practical application of data cleaning, SQL querying, and Power BI visualization in a real-world business scenario.

+ Strategic Planning: Provides valuable benchmarks for airlines aiming to improve efficiency or enter new market segments.

+ Industry Relevance: Addresses a timely topic in aviation where low-cost models are growing, yet face profitability challenges.

## Data Source
This dataset was generously shared within a data community group.
Special thanks to Silvia Wutche for providing the airline performance dataset used in this analysis.
The dataset includes key metrics such as EBIT, Load Factor, Fleet Age, Passenger Yield, and more allowing for comparative analysis between low-cost and non-low-cost carriers.

## Tool Used:
#### Microsoft Excel
Used for initial data cleaning, handling missing values, verifying data types, and preparing the dataset for analysis.
#### SQL (Structured Query Language)
Applied for filtering, grouping, and aggregating key metrics to compare low-cost vs. non-low-cost carriers.
#### Power BI
Designed a dynamic dashboard to visualize:
Average EBIT, Load Factor, and Passenger Yield
Fleet Age comparison
Slicers for interactive filtering by region and carrier type
KPI cards to highlight high-level insights

## Business Question Answered
What operational and financial differences exist between low-cost and traditional airlines based on key performance metrics?
Specifically, the project seeks to answer:
1. How does average EBIT (Earnings Before Interest and Taxes) differ between low-cost and non-low-cost carriers?
2. Do low-cost airlines operate with newer or older aircraft fleets?
3. How does the passenger yield compare across both airline categories?
    The goal is to uncover performance trends that can guide strategic decisions for airline operators and industry analyst

## Data Overview
The dataset contains information about various global airlines, focusing on both financial and operational metrics. It includes two airline categories: Low-Cost Carriers and Non-Low-Cost (Traditional) Carriers, labeled using the low_cost_carrier column.

##### Key Columns in the Dataset:
+ airline_name – Name of the airline
+ low_cost_carrier – Indicator (Y or N) showing if the airline is a low-cost carrier
+ ebit_usd – Earnings Before Interest and Taxes (in USD)
+ load_factor – Efficiency metric showing average seat occupancy (%)
+ num_routes – Number of routes operated
+ passenger_yield – Average revenue per passenger per kilometer (USD)
+ avg_fleet_age – Average age of the airline’s fleet (in years)

## Analysis Breakdown
This project followed a structured approach to explore and compare key performance metrics between low-cost and non-low-cost airlines.

#### Data Cleaning (Excel)
+ Removed missing and duplicate records
+ Ensured consistent data types for numerical fields (e.g., EBIT, Load Factor)
+ Verified low_cost_carrier labels (Y or N) for accurate filtering

#### Data Exploration & Querying (SQL)
+ Grouped airlines based on low_cost_carrier status
+ Used aggregation functions like AVG() to compute:
   + Average EBIT (ebit_usd)
   + Average Load Factor
   + Average Number of Routes
   + Average Fleet Age

#### Visualization (Power BI)
+ Clustered Bar Chart: Compared average EBIT by carrier type
+ Column Chart: Displayed comparisons for Load Factor, Passenger Yield, and Route Count
+ Card Visuals: Highlighted key KPIs
+ Slicer: Enabled dynamic filtering between low-cost and traditional airlines

#### Insight Generation
Analyzed metric differences to understand:
  + Profitability patterns
  + Operational strengths (fleet age, route network)
  + Revenue efficiency (yield per passenger)

## SQL Query Used
### Compare average values for key metrics between low-cost and non-low-cost carriers
```
SELECT
  low_cost_carrier,
  COUNT(*) AS airline_count,
  ROUND(AVG(ebit_usd), 2) AS avg_ebit_usd,
  ROUND(AVG(load_factor), 3) AS avg_load_factor,
  ROUND(AVG(num_routes), 2) AS avg_num_routes,
  ROUND(AVG(passenger_yield), 3) AS avg_passenger_yield,
  ROUND(AVG(avg_fleet_age), 2) AS avg_fleet_age
FROM airline_data
WHERE ebit_usd IS NOT NULL
  AND load_factor IS NOT NULL
  AND num_routes IS NOT NULL
  AND passenger_yield IS NOT NULL
  AND avg_fleet_age IS NOT NULL
GROUP BY low_cost_carrier;


### identify top-performing regions globally.
SELECT
  region,
  AVG(ebit_usd) AS avg_ebit,
  AVG(passenger_yield) AS avg_yield
FROM airline_data
GROUP BY region;


## Data Visualization
<img width="757" height="446" alt="airline dashboard" src="https://github.com/user-attachments/assets/0f9d8997-f6a5-4677-9e14-95f03fb0a1e6" />

## Recommendations
Based on the analysis of low-cost and non-low-cost airlines, the following recommendations are proposed:
+ Leverage Fleet Efficiency
Low-cost carriers tend to operate with newer fleets. Traditional carriers should consider renewing older aircraft to improve fuel efficiency and reduce maintenance costs.
+ Optimize Route Strategy
Non-low-cost airlines operate more routes on average. However, reviewing underperforming or low-yield routes could improve profitability and align with demand trends.
+ Improve Passenger Yield
Since non-low-cost carriers have higher passenger yield, low-cost airlines can explore value-added services (e.g., premium seating, in-flight meals) without compromising affordability.
+ Boost Load Factor
Both categories should aim to maintain high load factors. Dynamic pricing models and route scheduling based on seasonal demand can help maximize seat occupancy.
+ Benchmark EBIT Across Models
Airlines should monitor EBIT performance relative to their model (low-cost or traditional) and adjust business operations (e.g., ancillary revenue strategies) to stay competitive.
 

