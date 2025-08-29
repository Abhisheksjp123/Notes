#Demand_forecast_planning #Inventory_management
Field planning template as the name suggest is a tool utilized by the retailers/manufacturers to plan their sales in upcoming periods.

Consider the file for 2025-2026: yes the file i at year level and is created for 2 years, CY - 2025 and NY - 2026
# Objective:
==Main functionality==
1. Every retailer can input 
	1. Forecasted->cases, tones and GSVs for each period in the current year and upcoming year
	2. Actuals-> User can also see actual demand that was in the completed periods
	This was all done in base forecast sheet in FPT
2. Current PPG list
	1. This sheet gives information for the PPGs that are available in system
	2. Their case price, unit price, case weight and weather retailer want to forecast them or not
	3. These prices are further utilized for Tonnes and GSV calculation in base forecasting template 
==Other functionalities in the tool==
3. Mac and Trade
4. Building Blocks

==Power BI tools==
1. Forecast accuracy, year to year and period to period
2. Forecast error


# Approach

### Approach from the retailer
Every period tool is updated with that period actuals, as well as pervious period actuals are also updated if there is any change.
Retailers can see these actuals in following format

| **Retailer**    | **Walmart** |
| --------------- | ------- |
| **Subcategory** | **All**     |
Note: retailer will only be able to access his retailer and his subcategory data
this is the sample data they will be seeing

|      | GSV 2025 |      |      |         |         |         |
| ---- | -------- | ---- | ---- | ------- | ------- | ------- |
| PPG  | P01      | P02  | P03  | ==P04== | ==P05== | ==P06== |
| PPG1 | 1M       | 2M   | 3M   | 2M      | 3M      | 1M      |
| PPG2 | 1.1M     | 2.1M | 2.3M | 2M      | 3M      | 1M      |
|      |          |      |      |         |         |         |
Fields marked in yellow are not yet actualized and are forecasted number of retailer from previous period.

Steps for retailer:
1. Retailer can check the actualized demand
2. Based on his internal Forecast calculation, he can input upcoming period forecast numbers

### Approach for development of tool and maintenance
Tool was created on excel as final stakeholders, that is the retailers were comfortable with excel environment. 
Besides this was an MVP which will be in future transitioned into ANAPLAN.
Version 1: for 2024-2025 demand and forecast
Version 2: for 2025-2026 demand and forecast

Approach to create the tool was:
1. Data was stored in SQL for relational format
2. Data was access by the tool with the help of regex APIs
3. Excel VBA was utilized to function call the APIs for latest data, other than that what it does was.
	1. It send the user email id and access table to check if the user is authorized to access this retailer and subcategory 
	2. It also upload user input to the sql data

Approach to maintain tool was
Ever period after the actuals data for that period arrives
1. SQL codes are triggered through data bricks pipeline, to save forecast for that period as
   FF05 for Period 5 in Archive folder in data lake
2. Python codes are also triggered through pipeline to get the latest period actuals, and then combine these actuals with previous period forecast
3. New data is uploaded to SQL through pipelines
4. Also, before uploading the new data, sourced data is checked for new Demand Units(SKUs)
if found, these DUS are tagged to PPGs, their prices are validated and confirmed from the client, and then they are integrated to current price list

Approach to take in power bi
There were 2 reports in power BI
1. Field planning table:
this lets Admins from my client to access the entire live data from SQL and also archived data from datalake
2. Forecast error report.
This report created some analysis based on the archived data
- Like how accurate is the forecast compared to 4 periods back
- How is actuals for current period are different from the its forecasted numbers and reason for that.




# Use case
1. Admins/Client/Manufacturer
		- It helps them in inventory planning
		- It helps them to come up with on invoice/lumpsum discounted price based on the units they project to sell
		- It helps them to track if the actual sold inventories matches with what the retailer projected