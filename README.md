# CARBON EMISSION ANALYSIS
![CARBON-EMISSION](https://github.com/DongVND/carbon-emssion-analysis/blob/main/cover.jpg)
Photo by Chris LeBoutillier (unsplash.com)


This report aims to analyze carbon emissions to examine the carbon footprint across various industries. We aim to identify sectors with the highest levels of emissions by analyzing them across countries and years, as well as to uncover trends.

Carbon emissions play a crucial role in the environment, accounting for over 75% of global emissions and posing a significant environmental challenge. These emissions contribute to the accumulation of greenhouse gases in the atmosphere, leading to climate change, planetary warming, and involvement in various environmental disasters.

Through this analysis, we hope to gain an understanding of the environmental impact of different industries and contribute to making informed decisions in sustainable development.

### **Data Source: Where Our Data Comes From**
Our dataset is compiled from publicly available data from nature.com and encompasses the product carbon footprints (PCF) for various companies. PCFs represent the greenhouse gas emissions associated with specific products, quantified in CO2 (carbon dioxide equivalent).

#### Data Structure
The dataset consists of 4 tables containing information regarding carbon emissions generated during the production of goods.
![data_structure](https://github.com/DongVND/carbon-emssion-analysis/blob/main/Database%20diagram.png)

##### Table 'product_emissions'
Let's take a look at the first 3 records of the table
Using query:
```
SELECT * FROM product_emissions LIMIT 3;
```
Result:
| id           | company_id | country_id | industry_group_id | year | product_name                                                    | weight_kg | carbon_footprint_pcf | upstream_percent_total_pcf | operations_percent_total_pcf | downstream_percent_total_pcf | 
| -----------: | ---------: | ---------: | ----------------: | ---: | --------------------------------------------------------------: | --------: | -------------------: | -------------------------: | ---------------------------: | ---------------------------: | 
| 10056-1-2014 | 82         | 28         | 2                 | 2014 | Frosted Flakes(R) Cereal                                        | 0.7485    | 2                    | 57.50                      | 30.00                        | 12.50                        | 
| 10056-1-2015 | 82         | 28         | 15                | 2015 | "Frosted Flakes, 23 oz, produced in Lancaster, PA (one carton)" | 0.7485    | 2                    | 57.50                      | 30.00                        | 12.50                        | 
| 10222-1-2013 | 83         | 28         | 8                 | 2013 | Office Chair                                                    | 20.68     | 73                   | 80.63                      | 17.36                        | 2.01                         | 


##### Table 'companies'
Query:
```
SELECT * FROM companies LIMIT 3;
```
Result:
| id | company_name               | 
| -: | -------------------------: | 
| 1  | "Autodesk, Inc."           | 
| 2  | "Casio Computer Co., Ltd." | 
| 3  | "Cisco Systems, Inc."      | 


##### Table 'countries'
Query: 
```
SELECT * FROM countries LIMIT 3;
```
Result:
| id | country_name | 
| -: | -----------: | 
| 1  | Australia    | 
| 2  | Belgium      | 
| 3  | Brazil       | 

##### Table 'industry_groups'
Query: 
```
SELECT * FROM industry_groups LIMIT 3;
```
Result:
| id | industry_group                                                         | 
| -: | ---------------------------------------------------------------------: | 
| 1  | "Consumer Durables, Household and Personal Products"                   | 
| 2  | "Food, Beverage & Tobacco"                                             | 
| 3  | "Forest and Paper Products - Forestry, Timber, Pulp and Paper, Rubber" | 

### ❓ Questions to research
1. > Which products contribute the most to carbon emissions?
2. > What are the industry groups of these products?
3. > What are the industries with the highest contribution to carbon emissions?
4. > What are the companies with the highest contribution to carbon emissions?
5. > What are the countries with the highest contribution to carbon emissions?
6. > What is the trend of carbon footprints (PCFs) over the years?
7. > Which industry groups has demonstrated the most notable decrease in carbon footprints (PCFs) over time?

#### 1. Which products contribute the most to carbon emissions?
Query:
```
SELECT product_name, SUM(carbon_footprint_pcf) AS total_carbon_footprint_pcf
FROM product_emissions
GROUP BY product_name
ORDER BY total_carbon_footprint_pcf
LIMIT 1;
```
Result:
| product_name                 | total_carbon_footprint_pcf | 
| ---------------------------: | -------------------------: | 
| Wind Turbine G128 5 Megawats | 3718044                    | 










