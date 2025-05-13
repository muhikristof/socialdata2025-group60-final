---
layout: home
title: Home
---

- Bence Gattyán, s204773
- João Diogo Silva Oliveira, s250263
- Kristóf Muhi, s240194

# Introduction


## Motivation

We were interested in investingating traffic patterns in Copenhagen.
Knowing when people choose to drive can give us insight into how demand for transportation changes and help us deploy alternaive modes of transportation more effectively.

## Data sources

Data was gathered from:<br/>
Traffic data: https://www.opendata.dk/city-of-copenhagen/faste-trafiktaellinger <br/>
Weather data: https://open-meteo.com/en/docs/historical-weather-api?start_date=2005-01-01&end_date=2014-12-31&timezone=auto&latitude=55.6806&longitude=12.5492&hourly=temperature_2m,relative_humidity_2m,rain,snowfall,wind_speed_10m,weather_code,apparent_temperature,cloud_cover <br/>
Holiday data: https://www.timeanddate.com/holidays/denmark/ <br/>
Holidays couldn't be directly obtained as csv so I scraped each relevant year by hand into a csv file.<br/>

## Basic distributionss of data

## Traffic station availability

![Online/offline status](/pics/onlinestatus.png)

These traffic stations frequently go offline. This can be due to maintenance, the station getting removed, or the road getting repaved.

# Traffic patterns 1

## Weekdays, Weekends, Long term trends

![Station Map](/pics/stationmaps3.png)

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


![Long term trend](/pics/longterm.png)
- **Long term trends:** On these plots we show how each stations traffic pattern changes over the span of the dataset.
Because the stations keep going offline and online, only 8 stations have data complete enough to make this plot, 
other stations had at least 1 year where they were online for less than a week.

We can observe that most stations keep their unique characteristic over long periods of time, with a common change being a slight decrease in traffic.
A unique case here is station 562 with it's weekend trend completely changing for the years of 2008,2009 and 2010.
This traffic trend resembles a typical weekdays traffic trend instead.
After some research we found the change was likely due to the construction of the SEB Domocile on the street corner, which has been finished in 2010.
So the change in traffic was there because of all the people involved with the project was working on it over the weekends.

![Construction](/pics/construction.png)

## Holidays

![Holiday traffic](/assets/images/december_holiday_traffic.png)

This heatmap visualizes the total daily vehicle counts for the month of December from 2006 to 2014. Each cell represents the vehicle count for a given day and year. Darker red shades indicate higher traffic, while lighter shades represent lower traffic volumes. Vertical dashed lines highlight holidays (Dec 24–27).

- **High Early December Traffic (2006–2008):** These years show consistently high vehicle counts in early December, with particularly dark red cells across most days.

- **Holiday Dip (Around Dec 24–26):** Across nearly all years, traffic volume drops significantly during the holiday period (Christmas Eve through Dec 26), as marked by lighter-colored cells. This dip aligns with the dashed vertical lines indicating holidays.

- **Post-Holiday traffic:** Traffic usually rebounds slightly after Dec 27, though not to pre-holiday levels.

Note that for 2014, data shows less traffic counter activity, which could explain the lower traffic through all December in 2014.

# Traffic patterns 2

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
| Bence Gattyan | Traffic patterns #1 weekends and weekdays, unique station patterns |
| João Diogo Silva Oliveira | Bokeh plot |
| Kristof Muhi | Traffic patterns #1 holidays, traffic patterns #2 effects of rain, danish weather |
| Kristof Muhi | Making the website in Github Pages |