

# Chocolate Sales - Dashboard

### Dashboard Link : https://mytrine-my.sharepoint.com/:u:/r/personal/rvarma23_my_trine_edu/Documents/chocolate_sales_dashboard.pbix?csf=1&web=1&e=5MmnfE

## Problem Statement

This dashboard provides insights into the revenue earned by a chocolate company during the years 2023 and 2024. It enables the company to evaluate its overall revenue performance and identify key contributors, including teams and individual salespersons. The insights help the company understand revenue trends and optimize team performance, aiding in better decision-making for future sales strategies.

The first page of the report focuses on overall company revenue, while the second page delves into the performance of teams and individual salespersons, highlighting their contributions to the total revenue.

### Steps followed 

- Step 1: Load the dataset (a CSV file) containing sales and revenue information into Power BI Desktop.
- Step 2: Open Power Query Editor and enable "Column distribution," "Column quality," and "Column profile" under the View tab in the Data Preview section.
- Step 3: Profile columns based on the entire dataset instead of the default first 1000 rows.
- Step 4: Handle missing or erroneous data:

    Found no errors or empty values in most columns.
    Columns with null values (e.g., "Revenue" for certain entries) were reviewed and adjusted. Null values were excluded from calculations for accuracy.

- Step 5: Created a clean dataset by applying necessary transformations (e.g., removing nulls, creating calculated columns).
- Step 6: Designed the first page of the report to display company-level revenue insights:

    Added visuals such as donut charts, pie chart, bar charts, and cards to showcase total revenue trends across 2023 and 2024.

    Used filters for selecting year.

- Step 7: Designed the second page to highlight team and individual salesperson performance:

    Added a clustered bar chart showing revenue by team.
    Added a table visual with details for each salesperson, including total revenue generated, number of shipments.
    Incorporated team and year filters. 

- Step 8: Created DAX measures for custom calculations such as:

Total Revenue:

    Total Revenue = SUM(shipments[Amount])

Year over Year:

    YoY = 
        VAR
        _previous = 
        IF(
        NOT(ISBLANK([Total Revenue]))
        , CALCULATE(
            [Total Revenue]
            , PREVIOUSYEAR('calendar'[cal_date]
            )
        )
    )
    RETURN
    DIVIDE(([Total Revenue] - _previous), _previous, "No change")


 
- Step 9 : The report was then published to Power BI Service.
 
 

# Sales_Revenue Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://github.com/rajsvarma1492/Power_Bi/blob/main/Sales_dashboard.png?raw=true)

# Sales_Person_Revenue Report Snapshot (Power BI DESKTOP)

![Dashboard_upload](https://github.com/rajsvarma1492/Power_Bi/blob/main/Sales_person_dashboard.png?raw=true)
