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
```sql
In[1]:
-- What is the oldest business on each continent?
SELECT 
		b.business,
		b.year_founded,
		c.continent,
		c.country
FROM 
	businesses AS b
JOIN 
	countries AS c
ON b.country_code = c.country_code
WHERE
	(b.year_founded, c.continent) IN (
	SELECT 
	 MIN(year_founded),
	 c2.continent
	FROM
	 businesses AS b2
	JOIN
	 countries AS c2 
	ON b2.country_code = c2.country_code
	GROUP BY
	 c2.continent
	)
ORDER BY
	c.continent, b.year_founded;

Out[1]:
| business | year_founded | continent | country |
|---|---|---|---|
| Staffelter Hof Winery | 862 | Europe | Germany |
| Kongō Gumi | 578 | Asia | Japan |
| Shirley Plantation | 1638 | North America | United States |
| ... | ... | ... | ... |

	
