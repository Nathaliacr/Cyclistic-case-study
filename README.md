# Cyclistic: A Case of Study

This is the final project from the Google Data Analytics Certificate. Here I analyzed a case of study from a fictional company. Nonetheless, data utilized in this project is real* and belong to Divvy bicycle-sharing service in Chicago (Link license). 

## Scenario
Cyclistic is a fictional company that offers bike-share services since 2016. Nowadays the company counts with more than 6000 geotracked bikes and more than 700 stations across Chicago. Previously, Marketing’s strategy was centered on building general awareness of the program in different consumers segments*. But now the Marketing team wants to focus on increasing profit by maximizing the number of annual members, because users with an annual membership are more profitable than users that buy single-day or full-day tickets.
The objective of this analysis is to find out how casual riders and members use the bikes, so the marketing team can create new strategies in digital media to convert casual users into members. So* the question that will guide my analysis is: How do annual members and casual riders use Cyclistic bikes differently?
For this project I based my study * on the six phases of the data analytics process*: Ask, Prepare, Process, Analyze, Share and Act.


## First setp: Preparing an processing the data
Before starting the analysis, it is important to check the integrity of the data. The data is owned by the City of Chicago and it was published by Lyft Bikes and Scooters (llc), which is the company that operates the Divvy service. The fact that the company that collects the data published it, makes the data relieve, original, and unbiased. 
There are data from different years available and every year is divided in 12 datasets corresponding to every month. I took the data from 2022, given that it is the last current complete year.
I selected R as my tool to clean and analyze the data, since it is a powerful tool that can process millions of data quickly and also makes really good visualizations. I also used Tableau for one of my visuals. I used the following libraries on my analysis: ggplot2, tidyverse, scales, *, and basic R functions.  

Firstly, I merged the 12 datasets into one. All datasets have the same columns in the same order; thus, I just used the function r bind to append the other datasets as new rows. The resulting dataframe (data_2022) has a total of 5,667,717 observations and 13 fields. The 13 included columns were: ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, stra_lng, end_lat, end_lng.

Secondly, I checked the type of every column*, but everything was imported correctly. When the dataframe was ready I started the cleaning process, which started with capitalizing the first letter in the member_casual column. Then I remove the following rows: trips with negative and cero time length, trips with less than 1 minute length because they’re potentially false starts, trips where the bikes were checked for quality (Station ID = Hubbard Bike-checking (LBS-WH-TEST)). After the cleaning the total data was around 5.14 M.


## Second step: Analysing the data


### Who uses the bikes more

![Figure 1](/g_total_rides.png)

Coming back to the business tasks, my objective was to analyze the way casual riders and members use the bikes. To answer this question, I graphed the data in various ways and performed some calculations showed in the code to get insights of the data.
In this part I wanted to determinate the proportion of rides taken by members versus casual riders. I found that more than the half of the rides in 2022 were taken by users with an annual membership. However, the relation between members and casual rides was not significantly different.

### Length of the rides


![Figure 2](/g_avg_ride_length.png)


Then I was interested on the behavior of these rides, are they short? Long? Is there a pattern? That’s why I calculated the average ride length per month. The results showed two different behaviors during the year: Members ride in average relatively shorter than casual member. One possible explanation for this phenomenon is that the annual members use the bikes primarily as commuting medium, they drive regularly, even in winter times; whereas casual members may use them for their leisure time. The length of rides doesn’t change in general so much, just in the three last months of the year, which the ride’s times for the casual users reduces by almost 10 minutes. This drastic reduction coincides with winter. Maybe they prefer not to drive when the temperatures are cold, and as a result, the average times change much. Despite that, further evidence is needed to draw any firm conclusions. 
(GRAPH 2: AVERAGE LENGTH OF RIDE)


### Busiest times of the year

![Figure 3](/g_busiest_months.png)


visuals with different time scales.
Let’s start with the general behavior of the rides during the year without distinguish the user. Figure 4** is an area chart with 12 small multiples, each represents a month of the year. In every chart it is shown the total number of rides that started at certain hour. The plots have a bi- or trimodal distribution. Again, we see the pattern in the data: in winter the total of rides reduces drastically. And we can even see the maximums on the warmer months (April-September). It can be supposed that tourists, who visit the city mostly in summer, are an important part of the big increase, as well as the residents are more likely to go out on the warm seasons for leisure. In particular, school and college vacations take place in the middle of the year, which may increase bike usage for leisure.
It is also important to highlight that there are three notable peaks on the multiples. The first and largest peak is the maximum of each month, that occurs around 17:30, at that time people go normally out of work or just go home. After 18:00 the number of the rides decreases exponentially.  On the other hand, on Saturdays and Sundays doesn’t really exist this peak, instead the maximum extends almost homogeneous throughout the afternoon, indicating that the bikes are likely being used for leisure rather than for commuting.
The second and third peak don’t stand out like the first one and in the weekend series they don’t even exist. Nevertheless, they are worth mentioning because of what they can point out. One of the peaks occurs around 6:30-7:00, a sign that a significant proportion of the users use the bikes to commute since they are typical times to go to work. The other “peak” (it’s more like a flat-topped Gaussian distribution) is not so well-defined as the first one, but occurs between 12-13:00, around this time workers/students and in general people got to lunch.

![Figure 4](/g_busiest_days_member.png)

GRAPH BUSIEST MONTHS
### Bike's preferences

![Figure 5](/g_type_bike.png)

To deepen in the behavior of the rides depending on the day, I graphed the total number of rides per day for both casual users and member. As in the past plot, weekdays present a similar tendency, while the weekend has a more constant tendency of rides during the day. It is notable that the series casual and member follow similar tendencies on each weekday. Though the rides from members are almost always higher with exception of the weekends, there the number of rides from casual users increases fast and is practically the same as members. This insight suggests that at least the half of casual riders utilize the bikes more on the weekends on their free time rather than for commuting. A last interesting observation from the graph is that rides in the night increase on Fridays and Saturdays, usual days for socializing and dining out, this just corroborates that both members and casual riders use the bike also in their free time.


### Popular stations

![Figure 6](/TOP10-1.png)


## Recommendations

## Conclusions



