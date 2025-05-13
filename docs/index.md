---
layout: home
title: Home
---

- Bence Gattyán, s204773
- João Diogo Silva Oliveira, s250263
- Kristóf Muhi, s240194

# Introduction

As cities grow and change, mobility demands can increase and change along with it.
Understanding traffic patterns is essential for efficient and sustainable urban planning.
This is especially true in cities like Copenhagen, which has made significant investments in cycling infrastructure and green mobility.

## Basic distributionss of data

![Holiday traffic](/assets/images/basic_distributions.png)

## Motivation

We were interested in investingating traffic patterns in Copenhagen.
Knowing when people choose to drive can give us insight into how demand for transportation changes and help us deploy alternaive modes of transportation more effectively.

Understanding traffic patterns in an urban setting can be critical to city planning, sustainability efforts and improving public safety.
We analyze a dataset, detailing traffic in Copenhaven between 2004 and 2014. Data was recorded with inductive traffic loops embedded in the road surface at 22 stations around the city
giving us measures of traffic flow in cars/hour.
By extending this dataset with additional information, such as weather data, dates of holidays etc, we are able to explore a lot of different factors that may influence traffic.

## Data sources

Data was gathered from:
- **Traffic data:** [City of Copenhagen - Faste Trafiktællinger](https://www.opendata.dk/city-of-copenhagen/faste-trafiktaellinger)
- **Weather data:** [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api?start_date=2005-01-01&end_date=2014-12-31&timezone=auto&latitude=55.6806&longitude=12.5492&hourly=temperature_2m,relative_humidity_2m,rain,snowfall,wind_speed_10m,weather_code,apparent_temperature,cloud_cover)
- **Holiday data:** [Denmark Holidays - Time and Date](https://www.timeanddate.com/holidays/denmark/)
  - Holidays couldn't be directly obtained as CSV, so we scraped each relevant year by hand into a CSV file.
- **Bike rides data:** [Bike Traffic Counts in Copenhagen - Kaggle](https://www.kaggle.com/datasets/emilhvitfeldt/bike-traffic-counts-in-copenhagen)
- **Accidents data:** [StatBank Denmark - UHELD4](https://www.statbank.dk/UHELD4)

## Traffic station availability

![Online/offline status](/assets/images/onlinestatus.png)

One important limitation of the dataset is the inconsistency in data availability from the induction loops. These sensors, which record traffic counts, occasionally go offline—sometimes for short periods, such as days, and in other cases for months or even permanently. This results in gaps in the dataset that can affect both the spatial and temporal coverage of our analysis. The plot above illustrates the distribution of active sensors over time, highlighting these interruptions. When interpreting results, especially those involving long-term trends or spatial comparisons, it is essential to account for these missing data periods.

# Traffic patterns

## Weekdays, Weekends, Long term trends

![Station Map](/assets/images/stationmaps3.png)

This visualizes the locations of the traffic stations, the id they are refferred by,
which direction the station is facing and traffic patterns in each direction for weekdays and weekends separately.

- **Weekend/Weekday pattern:** We can clearly see that weekends have a different traffic pattern than weekdays.
Weekends usually have lower traffic counts and follow a much smoother curve, weekdays have more traffic and there are two peaks at 8:00 and 16:00.
This can be explained by a lot of people travelling for work on weekdays, most having their shifts between 8:00 and 16:00, while for the weekend, they
usually have more freedom in choosing when they want to travel, so traffic is more evenly distributed.
There are also patterns in which direction people travel on weekdays. The traffic spike at 8:00 is usually higher for people travelling towards the city
center than for people going out of it while this pattern reverses in the afternoon. This tells us that there are more people living outside the city center who work inside,
than people who love in the center, but work outside of it.

These trends can be observed on all stations, however each station also has it's own unique was of manifesting this trend.
For example, the pattern in directionality does not hold for all stations, but holds for almost all stations that are on roads directly leading to the city center.


![Long term trend](/assets/images/longterm.png)
- **Long term trends:** On these plots we show how each stations traffic pattern changes over the span of the dataset.
Because the stations keep going offline and online, only 8 stations have data complete enough to make this plot,
other stations had at least 1 year where they were online for less than a week.

We can observe that most stations keep their unique characteristic over long periods of time, with a common change being a slight decrease in traffic.
A unique case here is station 562 with it's weekend trend completely changing for the years of 2008,2009 and 2010.
This traffic trend resembles a typical weekdays traffic trend instead.
After some research we found the change was likely due to the construction of the SEB Domocile on the street corner, which has been finished in 2010.
So the change in traffic was there because of all the people involved with the project was working on it over the weekends.

![Construction](/assets/images/construction.PNG)

## Holidays

![Holiday traffic](/assets/images/december_holiday_traffic.png)

This heatmap visualizes the total daily vehicle counts for the month of December from 2006 to 2014. Each cell represents the vehicle count for a given day and year. Darker red shades indicate higher traffic, while lighter shades represent lower traffic volumes. Vertical dashed lines highlight holidays (Dec 24–27).

- **High Early December Traffic (2006–2008):** These years show consistently high vehicle counts in early December, with particularly dark red cells across most days.

- **Holiday Dip (Around Dec 24–26):** Across nearly all years, traffic volume drops significantly during the holiday period (Christmas Eve through Dec 26), as marked by lighter-colored cells. This dip aligns with the dashed vertical lines indicating holidays.

- **Post-Holiday traffic:** Traffic usually rebounds slightly after Dec 27, though not to pre-holiday levels.

Note that for 2014, data shows less traffic counter activity, which could explain the lower traffic through all December in 2014.

## Shift in Traffic Trends: Cars to Bikes in Copenhagen (2005–2014)

![Bikes vs. Cars](/assets/images/bikes_vs_cars.png)

The stacked area chart illustrates the proportional share of road traffic (motor vehicles) versus bike traffic in Copenhagen over a 10-year period, from 2005 to 2014. The red area represents road traffic, while the green area represents bike traffic, shown as a percentage of the total traffic volume each year.

From the visualization, a clear trend emerges: road traffic has steadily decreased in proportion, while bike traffic has gained ground. In 2006, road traffic accounted for the overwhelming majority of total traffic—over 90%. However, by 2014, its share had dropped to just over 80%, with bike traffic growing correspondingly.

This shift suggests a gradual but meaningful transition in urban mobility habits in Copenhagen, aligning with the city’s efforts to promote sustainable transportation. Investments in bike infrastructure, such as dedicated lanes and bike-friendly urban planning, likely contributed to this change. Although road traffic remains dominant, the consistent growth in bike usage indicates a cultural and infrastructural shift towards more environmentally friendly and health-conscious commuting options.

Overall, this data highlights how policy and infrastructure changes can influence transportation behavior, making Copenhagen a model for sustainable urban transit development.

## Daily Accident Patterns by Day of the Week in Copenhagen

<iframe src="assets/plots/accidents_by_hour.html" width="100%" height="500px"></iframe>

The interactive line chart displays the number of traffic accidents in Copenhagen across different hours of the day, with the ability to select each day of the week. This visualization reveals distinct daily traffic patterns that reflect human behavior, commuting routines, and differences between weekdays and weekends.

A consistent trend can be observed on weekdays (Monday to Friday): accident numbers spike during morning (around 7–9 AM) and evening rush hours (around 3–6 PM). These peaks correlate with times when people commute to and from work or school, resulting in increased road activity and a higher likelihood of accidents.

In contrast, weekends (Saturday and Sunday) show a significantly lower volume of accidents throughout the day. This is likely due to reduced traffic as fewer people commute for work. On weekends, the peaks—though smaller—tend to occur in the afternoon hours, suggesting more recreational or leisure travel rather than routine commutes.

This pattern highlights the impact of urban activity and human mobility on road safety. Rush hours during the workweek present higher risks, emphasizing the need for targeted traffic management, road safety campaigns, and perhaps infrastructure adjustments to reduce accident occurrences during these periods.

![Accidents heatmap](/assets/images/heatmap_accidents.png)

The heatmap illustrates the normalized accident rate per hour during heavy rain conditions, adjusted relative to the number of vehicles on the road. This means it highlights not just when most accidents happen, but when the risk of accidents is highest in proportion to traffic volume.

Peak risk hours occur in the afternoon between 14:00 and 17:00, with the normalized accident rate reaching the maximum value of 1.00. This indicates that even though traffic may be high during these hours, accidents occur disproportionately more often during heavy rain.

Morning rush hours (7:00 to 9:00) also show elevated accident risk, with normalized values between 0.57 and 0.73. Rain significantly increases the chances of accidents during these busy commute hours.

The lowest accident risks are seen in the early morning (0:00 to 5:00) and late evening (20:00 to 23:00), where normalized values drop below 0.35. These times naturally have less traffic, and the impact of rain appears to be less severe.

The data reveals how heavy rain disproportionately increases the likelihood of traffic accidents during already busy periods, especially in the afternoon. Even if the number of cars is not at its highest, wet conditions make driving more hazardous during these hours.

## Effects of rain

![Fluctuations by rain](/assets/images/fluctuations_by_rain.png)

This line plot shows how average vehicle counts vary by hour of the day under different rainfall conditions: Heavy Rain, Moderate Rain, Light Rain, and No Rain.

- **Morning Peak (7–9 AM):**
  - All rainfall categories show a sharp increase in traffic during morning commute hours.
  - Heavy Rain leads to the highest peak around 8 AM, exceeding 50,000 vehicles; potentially due to delayed or condensed travel patterns.

- **Evening Peak (4–6 PM):**
  - A secondary traffic peak is visible for all rainfall types, though it is less pronounced than the morning peak.
  - Light and moderate rain conditions show slightly higher vehicle counts during this period compared to heavy rain.

- **Late Night & Early Morning (0–5 AM):**
  - Vehicle counts are lowest for all categories, with heavy rain showing slightly higher volumes around midnight compared to other conditions.

Rainfall does not drastically alter the general shape of daily traffic patterns, but heavy rain tends to amplify the morning peak** more than other conditions.

## Danish weather

![Weather types in traffic count](/assets/images/weather_type_traffic_count.png)

This horizontal bar chart shows the average vehicle count under various weather conditions in Denmark. The conditions are ranked from highest to lowest traffic volume.

- **Wet Weather Dominates Traffic Volumes:**
  - Moderate rain leads with the highest average traffic (~30,000 vehicles).
  - Other wet conditions — slight rain and various intensities of drizzle — also show high traffic volumes.
  - These patterns suggest that rain is a frequent part of daily life and does not strongly deter travel.

- **Cloudy and Mixed Conditions Maintain Moderate Traffic:**
  - Overcast, partly cloudy, and mainly clear conditions see slightly lower but still substantial vehicle counts (~25,000–26,000).

- **Snow Reduces Travel:**
  - Snowfall, regardless of severity, correlates with reduced traffic volumes—likely due to safety concerns or travel disruptions.

- **Clear Weather Has the Lowest Traffic:**
  - Surprisingly, clear days, which are less common in Denmark, show the lowest average vehicle count in this dataset.

Denmark experiences **frequent rainfall** and **relatively few sunny days** throughout the year. This plot reflects that reality—rain and drizzle are associated with high traffic volumes, indicating that Danes continue commuting and traveling regardless of wet conditions.

## Contributions

| Person | Assigned task |
|:----------|:----------|
| Bence Gattyan | Finding datasets, combining and formatting them |
| Bence Gattyan | Weekends and weekdays, Unique station patterns |
| João Diogo Silva Oliveira | Bokeh plot, Daily Accident Patterns by Day of the Week in Copenhagen, Accident heatmap  |
| Kristof Muhi | Holidays, Effects of Rain, Danish weather |
| Kristof Muhi | Making the website in Github Pages |