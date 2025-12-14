# Data_Analysis_Excel_Power_Query_DAX
This project demonstrates my end-to-end BI skills using Power Query, Power Pivot (DAX), and Excel Visualization. I built a dynamic and interactive sales performance dashboard for a multi-store coffee chain.


<br>

## Project Objectives

- Analyze total sales performance over a 6-month period (Jan–Jun 2025)

- Identify top-performing products and categories driving revenue

- Compare store-wise performance to assess consistency and potential for expansion

- Detect sales trends over time, including monthly growth and quarterly comparisons

- Understand customer behavior by time of day to optimize operations and marketing

- Evaluate the average selling price per product and category to inform pricing strategies

- Dashboard Interaction <a href="https://github.com/fardousfa/Data_Analysis_Excel_Power_Query_DAX/blob/main/Project%20Dashboard.PNG">View Project Dashboard</a>

<img width="1563" height="1040" alt="Project Dashboard" src="https://github.com/user-attachments/assets/08beb446-b402-47fb-87e6-8b63ee895b6c" />


## Process Overview
**1. Data Source & ETL**

    Source: Kaggle

    Tool: Power Query, Excel, DAX, Excel Data Modelling

    Steps:

        Cleaned and normalized Transactions, Product, Store, and Calendar tables.

        Generated Quarter, Month Name, and Month Index columns from transaction dates.

**2. Data Model**

    Built a star schema with:

        Fact Table: Transactions

        Dimension Tables: Calendar, Store, Product

    Relationships:

        Many-to-one joins between Transactions and each dimension.

    Used DISTINCTCOUNT, CALCULATE, FILTER, AVERAGEX, and DATEADD to create robust DAX measures.
<img width="991" height="773" alt="Data Model" src="https://github.com/user-attachments/assets/0615dfd6-adfd-48a0-83c8-f8f6b98b5c4d" />


**3. DAX Measures (Samples)**

    Total Sales Previous Period = =CALCULATE([Total Sales],DATEADD('Calendar'[transaction_date],-1,MONTH))

    Total Sales Previous Corresponding Period = =CALCULATE([Total Sales],SAMEPERIODLASTYEAR('Calendar'[transaction_date]))

    % of Growth = IF(ISBLANK([Total Sales PP]), BLANK(), ([Total Sales] - [Total Sales PP]) / [Total Sales PP])

    Coffee Sales % = [Coffee Sales] / [Total Sales All]

DAX usage included context transition, CALCULATE filters, and time intelligence for trend analysis.

***DAX Measure Window***
<img width="963" height="476" alt="DAX Measures" src="https://github.com/user-attachments/assets/15c3ebda-9000-43e5-94be-c2944b4af4b8" />

***Power Query Editor Window***

<img width="1920" height="925" alt="Measures In Query Editor" src="https://github.com/user-attachments/assets/519d522a-bc05-4a2b-b57b-23b0d1f071bf" />

<br>


**4. Visualization**

    Tool: Excel PivotCharts with slicers and KPIs

    Dashboards include:

        Monthly and quarterly sales trends

        Top categories/products

        Sales by store & time of day

        % sales growth, total sales, average product price

        Interactive slicers for time period & store location
<br>

## Key Findings & Recommendations
**Findings:**

- Total Sales: £504,343 across 214,470 units

- Highest Sales by Category: Coffee (£176,629), 35% of all sales

- Peak Sales Time: Breakfast (49.3% of total sales)

- Q2 Growth: +63.1% vs Q1, major jump in May (31.9% MoM growth)

- All three stores performed evenly, showing consistency

**Recommendations:**

- Boost breakfast-time marketing (offers, staffing, loyalty).

- Replicate Q2 strategies to maintain momentum.

- Expand coffee and tea variants (60% of total category sales).

- Consider new store locations based on uniform performance.

- Investigate February dip for process/marketing gaps.

## Skills Demonstrated

- Power Query for efficient ETL & calculated columns

- DAX for advanced KPIs & time intelligence (YoY, MoM, QoQ)

- Data modeling with star schema & relationships

- Excel Pivot Dashboarding with interactivity

- Business acumen in interpreting sales performance

## Future Enhancements

- Migrate dashboard to Power BI for real-time cloud publishing

- Add forecasting and trendlines using DAX or Excel Add-ins

- Integrate customer or demographic data for segmentation

- Include profitability metrics (COGS, margins, etc.)
