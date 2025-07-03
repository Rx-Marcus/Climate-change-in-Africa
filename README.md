# Climate change in Africa

## Table of Content
- [Project Overview](#project-overview)
- [Business Objectives](#business-objectives)
- [Data source](#data-source)
- [Tools](#tools)
- [Data cleaning and preparation](#data-cleaning-and-preparation)
- [Data Analysis](#data-analysis)
- [Visualization](#visualization)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)

### Project Overview 📽️
---

This project aims to analyze historical temperature patterns across various regions in Africa from 1900 to 2013. The goal is to uncover long-term trends, regional variations, and seasonal patterns to support data-driven insights for environmental planning, climate awareness, and policy recommendations.

### Business Objectives
1.	What is the long-term trend of average temperatures across Africa from 1900 to 2013?
2.	How much has the average temperature increased per decade across the African continent?
3.	What is the overall average temperature recorded across all selected African countries and cities?
4.	Which months consistently record the highest and lowest average temperatures in Africa?
5.	Which country in the dataset has the highest average temperature, and which has the lowest?
6.	Which African region experiences the warmest temperatures on average?
7.	What is the level of uncertainty in the decadal average temperature measurements (confidence intervals)?
8.	Are there observable seasonal temperature patterns that repeat across years?

### Data source

The dataset used for this project is the "GlobalLandTemperaturesByCity.xlsx" obtained from [kaggle](https://kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data?resource=download)

### Tools

Power Bi

### Data cleaning and preparation
1.	The `dt` column datatype was changed to date
2.	The `dt` column was renamed to date for clarity
3.	Removed the `latitude` and `longitude` column
4.	Filtered `date` column for records between 1900 to 2013
5.	Two dimension tables were created;
- DimCity
- DimCountry
6.	The cleaned dataset was imported into Power Bi, and a relationship was created between the dimension tables and the fact table
7.	A calendar date table was created and added to the star schema

### Data Analysis

Four (4) DAX measures were created to enhance analysis
- ```Avg temperature = AVERAGE(GlobalLandTemperaturesByCity[AverageTemperature])```
- ```Avg temperature uncertainty = AVERAGE(GlobalLandTemperaturesByCity[AverageTemperatureUncertainty])```
- ```Lower temperature = [Avg temperature] - [Avg temperature uncertainty]```
- ```Upper temperature = [Avg temperature] + [Avg temperature uncertainty]```

### Visualization
#### 1.	KPI Cards:
- Total countries
- Total cities
- Average temperature
#### 2.	Line chart:
- Average temperature by decades with uncertainty range
- 	Monthly average temperature trend
#### 3.	Map visuals:
- verage temperature by country
#### 4.	Table:
- Country, average temperature
#### 5.	Slicers:
- Country 
- Month-Year

### Key Insights
1. The analysis covered 20 African countries and 53 cities, revealing an overall average temperature of 23.35°C across the dataset.
2. Decadal average temperatures from 1900 to 2010 show a gradual warming trend:
- In the early 1900s, the average temperature was 22.75°C, with a confidence interval ranging from 21.87°C to 23.64°C.
- By the 2010s, the average temperature rose to 24.11°C, with a confidence interval between 23.55°C and 24.68°C.
3. The monthly temperature trend shows that temperatures rise from January, peaking in April with an average of 24.36°C, indicating a warming phase during the early part of the year. From May to July, temperatures gradually decrease. A slight increase is noted from August to October, followed by another decline, reaching the lowest average temperature of 22.16°C in December.
4. This repeating rise and fall in temperature throughout the months suggests a seasonal climate cycle, with April being the hottest month and December the coolest. The consistency of this trend across months indicates a stable, seasonal temperature pattern that is repeated year after year.
5. Among all countries analyzed:
- Burkina Faso recorded the highest average temperature at 27.78°C.
- South Africa had the lowest average temperature, at 15.76°C.
6. The West African region emerged as the warmest, a pattern clearly visible in the heat map visualization, indicating consistently higher temperatures compared to other regions.

### Recommendations
1.	Increase climate awareness by presenting clear evidence of long-term warming trends across various regions in Africa.  
2.	Align national policies with these observed warming trends to enhance climate resilience.  
3.	Implement effective climate action policies to tackle the increasing long-term temperature trends in Africa.  
4.	Consider seasonal patterns in the planning of agriculture, energy, and health initiatives.
