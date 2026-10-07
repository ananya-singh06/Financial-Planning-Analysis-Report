# Financial-Planning-Analysis-Report
End-to-end FP&amp;A Budget vs. Actual variance dashboard: star-schema model on SQL Server, T-SQL (CTEs, window functions, stored procedures), Power Query, advanced DAX and hierarchical row-level security. Includes synthetic data and a full build guide.


FPA Budget vs Actual 
Synthetic dataset (star schema)

Files: DimEmployee, DimDepartment, DimAccount, DimRegion, FactBudget, FactActuals, FactTransaction 
Date range: Jan 2024 - Dec 2026. Actuals exist through Sep 2026 only (budget runs through Dec 2026).
Date table is NOT included: create it in Power BI (DAX). 
Relationships: Fact[MonthStart] -> Date[Date]; 
Fact[DepartmentID/AccountID/RegionID] -> matching dimension IDs.

RLS: see DimEmployee (ManagerID hierarchy) + DimDepartment[HeadEmployeeID]. Test in Power BI with View as > Other user (use an Email from DimEmployee.csv).

Planted stories (for insights):
 1. Marketing Spend ~+30% over budget Jul-Sep 2026
 2. Technology & Cloud costs creeping up ~3%/month from Apr 2026
 3. West region Product Revenue ~18% below budget Jan-Jun 2026

Data is fully synthetic; no real company or customer data.

