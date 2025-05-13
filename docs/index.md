---
layout: home
title: Home
---

- Bence Gattyán, s204773
- João Diogo Silva Oliveira, s250263
- Kristóf Muhi, s240194

# Introduction
## Motivation
## Data sources
## Basic distributionss of data

# Traffic patterns 1
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
| Bence Gattyan | Researching for possible data story |
| Bence Gattyan | Heatmaps |
| João Diogo Silva Oliveira | Bokeh plot |
| Kristof Muhi | Traffic patterns #1 holidays, traffic patterns #2 effects of rain, danish weather |
| Kristof Muhi | Making the website in Github Pages |