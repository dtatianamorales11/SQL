# Birth Rate Analysis for Northern New York Counties

You are a public health investigator in a state government agency. For your current project, you need to identify the U.S. counties with the most and fewest births in 2016-2018.

✏️ THE OBJECTIVE

Use SQL to:

- Organize and analyze your data in a significant way 
- Find the highest or lowest values in a data set
- Compare data in different dimensions

The next query in the Query Editor to show the first 1,000 rows of the county_natality table.

SELECT
  *
FROM
 bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
LIMIT
 1000

![image](https://github.com/user-attachments/assets/84d243e6-20c8-47e0-bc52-2ea1cb0cc4af)

Now, order the data with the SQL ORDER BY function. Enter the next query in the Query Editor. The text preceded by two dashes (--) are comments explaining the code.

SELECT
  *
FROM
  bigquery-public-data.sdoh_cdc_wonder_natality.county_natality
ORDER BY --This is a SQL sort order function
  Births --Applies the sorting to the Births column
LIMIT
  10

  ![image](https://github.com/user-attachments/assets/5988c2fe-c6bc-4983-a3b3-74d46132ab87)

In the job as a public health investigator, you are exploring whether birth rate trends in various counties in upstate New York have increased or decreased, and whether they follow the same trend.

To answer this, you will need the following information:

- Results for Erie, Niagara, and Chautauqua counties in New York State.
- Results sorted by county of residence and year to find the trend. 

The next Query will filter the results by county and sort the results by year and county. This will allow you to determine if the number of births is increasing or decreasing in each county.

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

  ![image](https://github.com/user-attachments/assets/f84fed44-b7c9-4346-828e-21c920ec1254)

The last query you ran returned births in three counties, organized by year and county. Now, you want to identify the highest number of births in Erie, Chautauqua or Niagara counties between 2016 and 2018.

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

  ![image](https://github.com/user-attachments/assets/7818db9a-e001-4772-a0b6-a7e454768616)

- Answer: There were a total of 9,916 births in Erie County in 2016. To arrive at this answer, it was necessary to order by birth rather than by county and year. Adding DESC to the ORDER BY clause would order the Births column in descending order to make it easier to identify this information. 

  

