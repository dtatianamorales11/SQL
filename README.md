# Birth Rate Analysis for Northern New York Counties

## Project Overview

As a public health investigator for a state government agency, this project aimed to identify and analyze birth rates across various U.S. counties from 2016 to 2018. The goal was to determine which counties experienced the highest and lowest birth rates during this period and to identify any trends over the years.

## Objectives

1. **Organize and Analyze Data**: Use SQL to structure and explore the data effectively.
2. **Identify Extremes**: Find the counties with the highest and lowest number of births.
3. **Compare Trends**: Analyze birth rate trends over time and across different counties.

## Data Source

The analysis was conducted using the `county_natality` table from the [CDC WONDER Natality dataset](https://bigquery.cloud.google.com/dataset/bigquery-public-data:sdoh_cdc_wonder_natality).

## SQL Queries

### 1. Initial Data Exploration

To retrieve the first 1,000 rows from the `county_natality` table:

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
LIMIT
  1000;
```

2. Sorting by Births
To sort the data by the number of births and view the top 10 counties:

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
ORDER BY
  Births DESC -- Sorts data by number of births in descending order
LIMIT
  10;
```

3. Analyzing Birth Trends in Specific Counties
To analyze birth trends in Erie, Niagara, and Chautauqua counties, sorted by year:

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
WHERE
  County_of_Residence IN ('Erie County, NY', 'Niagara County, NY', 'Chautauqua County, NY')
ORDER BY
  County_of_Residence, 
  Year;
```

4. Identifying the Highest Number of Births in 2017
To find the county with the highest number of births in 2017:

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
WHERE
  Year = '2017'
ORDER BY
  Births DESC -- Orders data by number of births in descending order
LIMIT
  10;
```

## Results and Insights

Erie County had the highest total number of births in 2016, with 9,916 births.
Sorting by the number of births in descending order allowed for quick identification of counties with the highest and lowest birth rates.
Trends in birth rates over the years for Erie, Niagara, and Chautauqua counties were analyzed to determine if there were significant increases or decreases.

## Conclusion

This analysis provides valuable insights into birth rate trends in Northern New York counties, highlighting areas of significant change and informing public health decisions. The use of SQL queries enabled efficient data exploration and trend analysis, showcasing my skills in data management and interpretation.

## Additional Resources

*CDC WONDER Natality Dataset
*SQL Syntax Reference

Feel free to contact me for more details or if you have any questions about this analysis.

# Birth Rate Analysis for Northern New York Counties

You are a public health investigator in a state government agency. For your current project, you need to identify the U.S. counties with the most and fewest births in 2016-2018.

✏️ THE OBJECTIVE

Use SQL to:

- Organize and analyze your data in a significant way 
- Find the highest or lowest values in a data set
- Compare data in different dimensions

The next query in the Query Editor to show the first 1,000 rows of the county_natality table.

```sql
SELECT
  *
FROM
 bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
LIMIT
 1000;
```

![image](https://github.com/user-attachments/assets/84d243e6-20c8-47e0-bc52-2ea1cb0cc4af)

Now, order the data with the SQL ORDER BY function. Enter the next query in the Query Editor. The text preceded by two dashes (--) are comments explaining the code.

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
ORDER BY --This is a SQL sort order function
  Births --Applies the sorting to the Births column
LIMIT
  10
```
  ![image](https://github.com/user-attachments/assets/5988c2fe-c6bc-4983-a3b3-74d46132ab87)

In the job as a public health investigator, you are exploring whether birth rate trends in various counties in upstate New York have increased or decreased, and whether they follow the same trend.

To answer this, you will need the following information:

- Results for Erie, Niagara, and Chautauqua counties in New York State.
- Results sorted by county of residence and year to find the trend. 

The next Query will filter the results by county and sort the results by year and county. This will allow you to determine if the number of births is increasing or decreasing in each county.

```sql
SELECT
  *
FROM
bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
WHERE
  County_of_Residence = 'Erie County, NY' 
  OR County_of_Residence = 'Niagara County, NY'
  OR County_of_Residence = 'Chautauqua County, NY'
ORDER BY
  County_of_Residence, 
  Year
```

The last query you ran returned births in three counties, organized by year and county. Now, you want to identify the highest number of births in Erie, Chautauqua or Niagara counties between 2016 and 2018.

```sql
SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
WHERE
  Year = '2017-01-01' --This filters our results to 2017
ORDER BY
  Births DESC --This sorts Births and puts the lowest number at the bottom of our list
LIMIT
  10
```

- Answer: There were a total of 9,916 births in Erie County in 2016. To arrive at this answer, it was necessary to order by birth rather than by county and year. Adding DESC to the ORDER BY clause would order the Births column in descending order to make it easier to identify this information. 

  

