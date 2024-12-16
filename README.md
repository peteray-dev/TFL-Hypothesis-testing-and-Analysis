# TFL-Hypothesis-testing-and-Analysis
Transport for London Big data analysis using Pyspark

## INTRODUCTION
The Big Data task contains the data of rides made using bikes available in London from one station to another. The data was gotten from transport for London (TFL) collected between 2013 and 2015. This dataset includes the details of rides made from one station to another, it contains nine features which are very important in analyzing the rides made by the users within a particular period. The features include rental id, duration, bike id, end date, end station id, endstation name, start date, startstation id, startstation name. These features are very important to understand the bikers’ travelling patterns, duration, usage, and mobility trend within the city. This dataset contains millions of rows that will help to explore transportation dynamics in London and undercover meaningful patterns that will further help the organization to enhance efficiency and sustainability of bike transportation services in the city.

## DATA ANALYSIS
The technology used in analyzing the large dataset is Apache Spark (PySpark). The dataset contains 11,481,596 rows and 9 columns of string datatype with rows that are empty and contain wrong entry. From the statistical description, it was discovered that the minimum duration is a negative value which is not reasonable, so there is a need they are removed from the dataset as it might be because of system error or wrong entry. 
The total number of stations for bikes in London is 763. The bikes in different stations have their Id, from this it can be driven that the total number of bikes that are in use and available to users in London in the year 2014 is 12,229.
From the dataset, some rows have no entry for the end station id and end station name, this might have happened probably because the user refused to return the bike to the end station, it will be difficult to replace the null value. Moreso, there are some rows that have no entry, they contain null values across columns, the total number or rows with missing value is 1,239,245 which were all removed from the dataset. 
Research Hypothesis:
Null hypothesis (H0) = The average duration of rides starting from Baylis Road, Waterloo station is not significantly different from the other stations (µ1 = µ2)
Alternative hypothesis (H1) = The average duration of rides starting from Baylis road, Waterloo station is significantly shorter than other stations (µ1 < µ2)
Significant level (α) = 5% 

## INSIGHT
Hyde Park Corner, Hyde Park station experiences the highest bike usage, often with longer ride duration compared to other stations. However, it is important to note that the number of rentals doesn’t necessarily correlate with the ride duration. For instance, Black Lion Gate, Kensington Garden and Speakers’ Corner 2, Hyde Park Start Station, despite having a lower rental count than Waterloo Station 3 and Belgrove Street (figure 1), they exhibit higher hourly ride or duration covered in 2014 (figure 2). This suggests that users at the former two stations may have travelled longer distances to reach their end stations compared to the latter.
 
  ![image](https://github.com/user-attachments/assets/31f99489-4d07-4d5b-b7b6-42455aa0fd93)

Figure 1: Top 20 Start Stations by Count 2014

 ![image](https://github.com/user-attachments/assets/5af23208-40e7-4863-a955-f5fc859a865e)

Figure 2: Top 20 Start Stations by Duration (hours) in 2014
 
Futhermore, among the top 8 stations, 6 are located around Hyde Park and 2 in Kensington, indicating higher bike usage in term of duration (Figure 2). This suggests that these locations are likely to generate more revenue. Consequently, high maintenance effort in these locations is essential to retain users, attract more users and continue more revenue generation.
For stations ‘Tabletop1 Station” and “Contact Centre Station”, bicycles were returned to the same station after use. This suggests a lack of nearby alternative stations and possibly indicates that these stations are situated in areas where there is less demand for bicycles.
Regarding “Mechanical Workshop station”, it was observed that the only bike usage recorded was for a longer duration with rentals ending at another stations. This pattern suggests that the user travelled a longer distance to the end station. Overall, these stations are likely located in areas where there are no nearby alternative end stations, leading to bikes being returned to the same stations after use and travelling far to an alternative station.

 ![image](https://github.com/user-attachments/assets/7644650b-985e-465d-8f70-c5c0868b69f9)

Figure3: Mean Duration and rental count per month in 2014
From the above figure, August exhibits a high mean duration even though the number of rentals is lower than July, this suggests that the users rented bikes for longer duration on average in August, possibly due to it being a holiday period, thus encouraging longer trips. However, it is important to note that the average duration for November, January and February is below 1300 minutes, one might have expected a similar trend in December, despite it being a winter month like the others, it is observed that December has an average duration above 1400, confirming that users travel farther during the holiday. Also, it is worth noting that season influences the number of rentals in each month.
Hypothesis testing result:
From SciPy, the two-sample t-test was used. 
T-statistic: -7.432747917582017
P-value: 1.9865071945592685e-07
Conclusion:
Since the p-value is less than the significance level, the null hypothesis is rejected, therefore the average duration of rides starting from Baylis road, Waterloo station is significantly shorter than other stations.

RECOMMENDATION
Based on the analysis of the Transport for London bike dataset, there are some recommended actions that would improve the service in various locations
1. Improvement of stations: Start stations that record a high number of rentals should be maintained and improved, the bikes in every area should be maintained, many people might refuse usage because of poor bike functionalities.
2. Promotion of services: Awareness should be raised in start stations that recorded low usage and to improve the services, offers should be provided such as discounted prices.
