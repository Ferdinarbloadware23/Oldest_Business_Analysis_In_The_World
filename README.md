# Oldest_Business_Analysis_In_The_World
    This project aims to identify the characteristics and factors that have allowed the world's oldest companies to survive for centuries. This analysis uses data compiled by BusinessFinancing.co.uk to answer key business questions.
    
#Data_Sources_and_Tools
`businesses` and `new_businesses`
|Column|Description|
|------|-----------|
|`business`|Name of the business (varchar)|
|`year_founded`|Year the business was founded (int)|
|`category_code`|Code for the business category (varchar)|
|`country_code`|ISO 3166-1 three-letter country code (char)|
---
`countries`
|Column|Description|
|------|-----------|
|`country_code`|ISO 3166-1 three-letter country code (varchar)|
|`country`|Name of the country (varchar)|
|`continent`|Name of the continent the country exists in (varchar)|
---
`categories`
|Column|Description|
|------|-----------|
|`category_code`|Code for the business category (varchar)|
|`category`|Description of the business category (varchar)|

#Analysis Process & Key Questions
This analysis focuses on three main questions:
  1. Oldest Business on Each Continent
     This question aims to find the oldest company on each continent, which can provide an initial overview of the most resilient sectors geographically.
