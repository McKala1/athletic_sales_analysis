# athletic_sales_analysis 

## Overview

* With this challange problem I analyzed sales data to gain insights into which cities in the U.S. have sold the most athletic wear over two years. Then, I determined which retailers had the greatest total sales for athletic wear, and which retailers sold the most women's athletic footwear. Finally, I determined which day, and week had the highest sales for women's athletic footwear. This was a very insightful challenge because I got to really dig into the dataframe and put together a presentation I would use in the real world. 

# Part 1: Combine and Clean the Data

* First, I imported pandas as "pd". Then, I made the dataframe and added the csv file in using "Path". From there, I wanted to view the column names from the data set, so i called the dataframe and added".head()" at end. I did this for both the 2020, and 2021 athletic sales dataframes. I also checked the data types in the dataframes by adding ".dtypes" to see what was objects and floats. 

#  Check the data types of each DataFrame

*  I also checked the data types in the dataframes by adding ".dtypes" to see what was objects and floats. I did this for both 2020, and 2021 dataframes. 

#  Combine the sales data by rows

* For this section, I combined both 2020, and 2021 dataframes. In doing so I used the function "pd.concat". Then, I had to reset the index so I wrote "combined_sales.reset_index(drop=True, inplace=True)". This is so the computer knows to reset the dataframe to include both 2020, and 2021 data. Then I ran the dataframe again to double check what I did was correct. I also checked if there were any null values by using the ".isnull().sum()" function and found there were zero null values. I also wanted to check the data type of each column again and used the ".dtypes" function to see what were objects, floats, integers. Then, I converted the "invoice_date" to a datetime datatype. For this, I used the "to_datetime" function to not make it an "object" anymore. I double checked my work by running the dataframe as ".info()". I confirmed that "invoice_data" changed from an "object" to "datetime". 

# Part 2: Determine which Region Sold the Most Products

* For this section, I created a new dataframe and used "groupby" to view the number of products sold in each region, state, and city. I also did ".agg" for an aggregation with the units sold, and the total sales, both equal to "sum". I then renamed the units sold to "Total Products Sold" using ".rename(columns)". Lastly, I sorted the values to show the top five results in ascending = False order. I also wanted to show the number of products sold for each region, state, and city. For this, I used the "pivot_table" funcion. I used the "Total_Products_Sold" as the value, and "region, state, and city" as the index. I then, renamed the column "units_sold" to "Total_Products_Sold". Lastly, I sorted the top five results in ascending = False order with the "sort_values" function. The northeast region sold the most products. 

# Part 3: Determine which Region had the Most Sales

* For this portion of the challenge, I wanted to see the total sales for the products sold in each region, state, and city. For this I used the "groupby" function to view the number of products sold in each region, state, and city. I also did ".agg" for an aggregation with the total sales equal to "sum". I then renamed the total sales to "Total Sales" using ".rename(columns)". Lastly, I sorted the top five values to show the top five results in ascending = False order. I also used the "pivot_table" funcion. I used the "total_sales" as the value, and "region, state, and city" as the index, and "sum" as the aggreget function. I then, renamed the column "total_sales" to "Total_Sales". Lastly, I sorted the top five results in ascending = False order with the "sort_values" function. The northeast region had the most sales. 

# Part 4: Determine which Retailer had the Most Sales

* For this section, I wanted to see what retailer had the most sales. I used the "groupby" function, adding in the retailer, region, state, and city. I set the ".agg" to "total_sales" equal to "sum". I then, renamed "total_sales" to "Total Sales". I also wanted to see the top five results and used the ".sort_values" function ascending = False. The retailer West Gear had the most sales. I then, used the pivot table function. With this I set the values to equal total sales, the index to equal retailer, region, state, and city, and the aggfunc to equal sum. I then, renamed 'total_sales' to be "Total Sales". Lastly, I wanted to show the top five results so I used the ".sort_values" function with ascending = False. 

# Part 5: Determine which Retailer Sold the Most Women's Athletic Footwear

* For this section I made a new dataframe. I used the combined sales dataframe, called in the 'product' column, and made it equal to "Women's Athletic Footwear". I wanted to see the total number of women's athletic footwear sold. I used the groupby function and set it to pull from the retailer, region, state, and city columns. I set ".agg" to have units sold equal sum, and total sales equal sum as well. I then, renames units sold to Womens Footwear Units Sold. I also wanted to see the top five results so I used the ".sort_values" function and had ascending = False. I also, made a pivot table to display the information. I set the values to equal 'Womens Footwear Units Sold', set the index to equal 'retailer', 'region', 'state', 'city', and the .aggfunc to equal sum. I then renamed 'units_sold' to Womens Footwear Units Sold. Then, I wanted to show the top five results so I sorted the values of Womens Footwear Units Sold in ascending = False. The retailer that sold the most women's athletic footwear was West Gear in the region 'West', and in San Francisco, California, they sold a total of 12,107 units of women's athletic footwear. 

# Part 5: Determine the Day with the Most Women's Athletic Footwear Sales

* For this section, I wanted to figure out the day with the most women's athletic footwear. I created a pivot table, calling the dataframe and setting the index to equal "invoice_date", and the values to equal "total_sales". I then used the rename function to rename "total_sales" to "Total Sales". I then, resampled the pivot table into daily bins, and got the total sales for each day. This was done by using ".resample("D").sum()". The "D" in the parenthases means "days". I then, used the sort values function, and set ascending = False to sort the resampled pivot table in ascending order on "Total Sales".

# Part 6: Determine the Week with the Most Women's Athletic Footwear Sales

* Lastly, I resampled the pivot table into weekly bins, and get the total sales for each week. For this, I used the resample function and set the bin to "W", which means "weeks", then put ".sum". I then sorted the resampled pivot table in ascending order on "Total Sales". For this I used the sort values function, with ascending equal to False. 
