# enterprise-fleet-analytics-powerbi
An end-to-end Power BI data model transforming 85k+ logistics records into actionable financial, maintenance, and safety intelligence using advanced DAX and Star Schema architecture.


Enterprise Logistics & Fleet Operations Data Model
Role: Data Analyst / BI Developer
Tools Used: Power BI, Advanced DAX, Power Query, Relational Data Modeling.

📊 Project Overview
Transformed a highly fragmented logistics database—consisting of 14 interconnected operational tables and over 85,000 raw records—into a unified, 3-page interactive Executive Dashboard. The objective was to bridge the gap between raw dispatch data and actionable financial and risk intelligence.

🛠️ Data Architecture & Modeling
To ensure accurate aggregation and avoid cross-filtering errors across multiple fact tables, I architected a robust Star Schema relational model:
• Designed custom Dimension tables (Dim_Trucks, Dim_Drivers) to resolve Many-to-Many relationships between utilization metrics and transactional repair/safety logs.
• Engineered a master Dim_Date table using DAX (CALENDARAUTO()) to perfectly sync financial metrics across all departments and avoid "vanishing data" issues on days with zero loads.
• Developed complex DAX measures utilizing VAR (Variables) for query optimization and conditional logic to construct custom financial metrics.

📈 The Dashboard Ecosystem
1. Executive Financials (The Profit Engine)
   
• Modeled industry-standard driver compensation dynamically using an interactive "What-If" Parameter, allowing executives to adjust Cost-Per-Mile (CPM) rates and watch profit margins recalculate in real-time.

• Designed a temporal Line Chart tracking Gross Revenue against Total Operating Costs by Year-Month to expose historical margin trends and seasonal volatility.

• Developed a categorical Donut Chart breaking down the exact composition of total operational expenses (Fuel, Maintenance, Driver Pay, and Safety Costs), providing immediate visibility into budget distribution.

2. Fleet & Asset Management (The "Hit List")
   
• Strategic UI Pivot: Rather than displaying a massive, overwhelming matrix of all 500+ assets, I implemented a Top-N DAX filter to isolate the Top 10 High-Risk Assets. This created an actionable "Hit List" of trucks exhibiting the highest Total Downtime Hours, instantly telling the Operations Manager exactly which assets need to be pulled off the road.

3. Safety & Risk Assessment (The Risk Profile)
   
• Strategic UI Pivot: Replaced redundant operational KPIs with purely risk-focused metrics (e.g., swapping "On-Time Rate" for "Delayed Delivery %") to unify the tab's narrative around revenue loss.

• Designed a conditional Driver Leaderboard matrix juxtaposing generated freight revenue against accident claim liabilities. Applied a strict Top 13 Filter by Claim Amount to mathematically isolate only the drivers who represent actual financial liabilities, stripping away the noise of average performers.

💡 Business Value
This data model transitioned the company from reactive reporting to proactive operational strategy, clearly illuminating the break-even Cost Per Mile and exposing hidden profit drains within fleet maintenance and driver behavior.
