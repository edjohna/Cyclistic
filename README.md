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
### Combining the Data
