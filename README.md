
# 🌍 Global Economic Indicator Dashboard

An interactive Power BI dashboard designed to visualize and analyze global economic trends. This project integrates data from the World Bank API and provides insights into GDP, population density, and other key metrics for strategic decision-making.

## 📊 Overview
The dashboard consists of three key pages:

### Overview page

Displays a country-level table, a world map, and a bar chart showing the total number of countries by region.
Screenshot Recommendation: Add an image of the Overview Page with a focus on the map and table to highlight interactivity.

### Country Details

Detailed analytics for a selected country, including:
Four KPI cards (Population, GDP, Population Density, GDP per Capita).
A bar graph and table showing yearly GDP trends.
Screenshot Recommendation: Include a snapshot of a selected country's drillthrough page showing all visuals (KPI cards, trends, and table).

### Metadata

Provides detailed information about the data sources used in the report.
Screenshot Recommendation: Add a clean image of the Metadata Page with visible data source links.


## 🛠️ Key Features
Dynamic Visualization: Interactive charts and tables for country-level insights.

Advanced Measures: Custom DAX measures, including:
GDP Growth Rate
GDP Per Capita
Population Density
Year-specific GDP and Population

Drillthrough Analysis: Allows users to explore detailed statistics for a selected country.

Scalable Design: Optimized for performance with clean data models and calculated measures.

## 📂 Project Structure
Page 1: Overview

Provides a global snapshot of countries with key indicators and region-based analysis.

Page 2: Country Details

Focused analysis for individual countries, showcasing trends and KPIs.

Page 3: Metadata

Comprehensive data source and metadata documentation for transparency.

### 🔍 Data Sources
This project uses data from the World Bank's World Economic Data Database.

API Endpoints:
GDP (NY.GDP.MKTP.KD)
GDP Per Capita (NY.GDP.PCAP.KD)
Population (SP.POP.TOTL)

### 📈 Measures Used
Here are some of the key DAX measures used in the dashboard:

#### GDP Growth Rate (%)

DAX
Copy
Edit
VAR CurrentYear = SELECTEDVALUE(Indicators[Year])  
VAR CurrentYearGDP = CALCULATE([GDP], Indicators[Year] = CurrentYear)  
VAR PrevYearGDP = CALCULATE([GDP], Indicators[Year] = CurrentYear - 1)  
RETURN DIVIDE(CurrentYearGDP - PrevYearGDP, PrevYearGDP, 0)  
#### Population Density

DAX
Copy
Edit
DIVIDE([2020 Population], SUM(Countries[Land Area]), 0)  
#### GDP Per Capita

DAX
Copy
Edit
DIVIDE([GDP], [Population], 0)  

For a complete list of measures, refer to the pbix file in this repository.

### 🚀 Getting Started

To view or interact with the dashboard:

Download the .pbix file and open it in Power BI Desktop.


Overview Page

Drillthrough Page

Metadata Page

### 🛠️ Tools Used
Power BI: Data visualization and dashboard design.
SQL: Data extraction and transformation.
DAX: Custom measures and calculations.

### 🌟 Future Enhancements
Add time-series forecasting for economic indicators.
Include additional metrics like inflation rates or trade balances.
Provide localized filtering for specific regions or income groups.
