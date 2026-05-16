# enterprise-fleet-analytics-powerbi
An end-to-end Power BI data model transforming 85k+ logistics records into actionable financial, maintenance, and safety intelligence using advanced DAX and Star Schema architecture.


Enterprise Logistics & Fleet Operations Data Model
Role: Data Analyst / BI Developer
Tools Used: Power BI, Advanced DAX, Power Query, Relational Data Modeling.

Project Overview

Transformed a highly fragmented logistics database consisting of 14 interconnected operational tables and over 85,000 raw records into a unified, 3-page interactive Executive Dashboard. The objective was to bridge the gap between raw dispatch data and actionable financial and risk intelligence.

Data Architecture & Modeling

To ensure accurate aggregation and avoid cross-filtering errors across multiple fact tables, I architected a robust Star Schema relational model:

• Designed custom Dimension tables (Dim_Trucks, Dim_Drivers) to resolve Many-to-Many relationships between utilization metrics and transactional repair/safety logs.

• Engineered a master Dim_Date table using DAX (CALENDARAUTO()) to perfectly sync financial metrics across all departments and avoid "vanishing data" issues on days with zero loads.

• Developed complex DAX measures utilizing VAR (Variables) for query optimization and conditional logic to construct custom financial metrics.

The Dashboard Ecosystem

1. Executive Financials (The Profit Engine):

• Key Metrics Tracked: Gross Revenue, Total Operating Costs, Net Profit Margin.

• Modeled industry-standard driver compensation dynamically using an interactive "What-If" Parameter, allowing executives to adjust Cost-Per-Mile (CPM) rates and watch profit margins recalculate in real-time.

• Designed a temporal Line Chart tracking Gross Revenue against Total Operating Costs by Year-Month to expose historical margin trends and seasonal volatility.

• Developed a categorical Donut Chart breaking down the exact composition of total operational expenses (Fuel, Maintenance, Driver Pay, and Safety Costs), providing immediate visibility into budget distribution.

P.S: Since the drivers pay rate/Salary wasn't provided in the datasets, I created a "What-If Parameter" (a slider on the dashboard) labeled Driver Pay Rate ($/Mile) and set the default to $0.60 and I dynamically modeled Driver's compensation based on industry-standard Cost-Per-Mile (CPM) rates. You can use the parameter slider to adjust the rate and model different profitability scenarios.

2. Fleet & Asset Management (The Efficiency Matrix):

• Key Metrics Tracked: Total Maintenance Cost, Maintenance Cost Per Mile, Total Downtime Hours, Average Fleet MPG.

• Developed an interactive Scatter Chart ("Truck Efficiency Matrix") to instantly isolate high-risk "lemon" assets—trucks exhibiting low mileage utilization but exorbitant repair costs.

• Implemented a Clustered Bar Chart to track total downtime hours across the fleet, allowing the Operations team to pinpoint exactly which assets are causing the most severe operational bottlenecks.

• Designed a Funnel Chart categorizing total maintenance costs by repair type, providing clear visibility into the hierarchy of mechanical issues draining the fleet budget.

3. Safety & Risk Assessment (The Risk Profile)

• Key Metrics Tracked: Total Accident Claim Costs, Total Incident Volume, Average Idle Hours, Delayed Delivery %.

• Strategic UI Pivot: Replaced redundant operational KPIs with purely risk-focused metrics to unify the tab's narrative around revenue loss and operational liability.

• Developed an interactive Scatter Chart ("Driver Risk Matrix") plotting total miles driven against accident claim amounts to immediately isolate high-liability drivers (low miles, high crash costs).

• Implemented a Stacked Bar Chart breaking down total incidents by incident type, providing the safety team with clear visibility into the most common behavioral or equipment violations.

• Designed a conditional Driver Leaderboard matrix juxtaposing generated freight revenue against accident claim liabilities. Applied a strict Top 13 Filter by Claim Amount to mathematically isolate only the drivers who represent actual financial liabilities, stripping away the noise of average performers.

💡 Business Value

This data model transitioned the company from reactive reporting to proactive operational strategy, clearly illuminating the break-even Cost Per Mile and exposing hidden profit drains within fleet maintenance and driver behavior.
