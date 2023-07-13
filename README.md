# Cyclistic Case Study using SQL and Tableau
This project serves as the culminating assignment for my Google Data Analytics course, focusing on utilizing SQL and Tableau. Within this case study, I will simulate the responsibilities of a junior data analyst at Cyclistic, a fictional company. By adhering to the data analysis process stages of **Ask, Prepare, Process, Analyze, Share, and Act**, I aim to address crucial business inquiries and generate actionable insights.

## Scenario
You are a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations. 

## Ask
### Business Task
My manager has assigned me a specific responsibility of examining the contrasting usage patterns between annual members and casual riders of Cyclistic bikes.

## Prepare
### Data Source
I will use Cyclistic’s historical trip data to analyze and identify trends from January 2022 to December 2022 which can be downloaded from [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html). The data has been made available by Motivate International Inc. under this [license](https://www.divvybikes.com/data-license-agreement).  

All personally identifiable information have been removed.  The data consists of 12 CSV files of long format data, ranging from January 2022 through December 2022. Each file consists of 13 columns:
ride_id,  rideable_type,  started_at,  ended_at,  start_station_name,  start_station_id,  end_station_name,  end_station_id,  start_lat,  start_lng,  end_lat,  end_lng,  member_casual. 

## Process
BigQuery is employed to merge multiple datasets into a single dataset and perform data cleansing tasks. This decision is driven by the limitations of Microsoft Excel, which can only handle up to 1,048,576 rows per worksheet, making it inadequate for managing extensive data sets. Given that the Cyclistic dataset exceeds 5.6 million rows, utilizing a platform such as BigQuery becomes imperative due to its capability to handle large data volumes effectively.
### Combining Data
SQL Query: [Combining Data](https://github.com/edjohna/Cyclistic/blob/main/Combining%20Data.sql) 

12 csv files are uploaded as tables in the 'cyclistic.bike.data' dataset. I then used the UNION ALL operator to combine all the files into one table, titled "combined_data". The table contains 5,667,717 rows. 
### Checking Data Types and Omitting Duplicates
SQL Query: [Checking Data Types and Duplicates](https://github.com/edjohna/Cyclistic/blob/main/2.%20Checking%20Data%20Types%20and%20Duplicates.sql)

In the data analysis process, several checks and evaluations were performed. Firstly, the data type of each column was examined. Additionally, the count of null values in each column was determined, starting with the ride_id column, but substituting it with other column names for further analysis. Duplicate rides were checked, with none found. The length of the ride_id string was also verified to ensure it consistently contained 16 characters. Furthermore, the most frequently used type of bike was identified. 

Subsequently, a new table was created, incorporating the minutes, day of the week, and month of the year. This new table was then tested. During the testing, the minimum, maximum, and average values were assessed. It was discovered that negative values and excessively long ride durations beyond a day were present, indicating errors that needed to be excluded. To address these data inaccuracies, filtering techniques will be employed to exclude rows with negative ride lengths and rides exceeding a day's duration, as deleting rows is not feasible in the free version of BigQuery.
### Exploring and Analyzing Data
SQL Query: [Exploring and Analyzing Data](https://github.com/edjohna/Cyclistic/blob/main/3.%20Exploring%20and%20Analyzing%20Data.sql)

Various analyses were conducted to derive meaningful insights from the data. This involved examining the mean, lowest, and highest ride durations while excluding inaccurate data. Average ride lengths were calculated for both members and casual riders, followed by determining the average ride length for each day of the week for both groups. Additionally, the average ride length by month was determined for members and casual riders. The total number of rides taken by members and casual riders was also evaluated. Furthermore, the count of rides taken on each day of the week for each group and the count of rides taken by each group in each month were determined. To analyze ride patterns throughout the day, the number of rides taken during each hour was analyzed separately for members and casual riders. 

To ensure clarity in data filtering within Tableau, the "day_of_week" column was modified to display weekdays as "Monday" through "Friday" instead of numerical values. The most popular start and end stations were identified for both member and casual riders. Results from each analysis were saved as new tables, enabling the joining of tables to obtain a comprehensive count of how often members and casual riders started or ended their rides at each station. Finally, the total number of visits to each station was calculated for members and casual riders.

## Analyze and Share
Data Visualization: [Tableau](https://public.tableau.com/views/CyclisticDashboard_16892138256590/RidesTakenperMonth?:language=en-US&:display_count=n&:origin=viz_share_link)
