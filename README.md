# Final Assignment for Group 60: Traffic Data of Copenhagen

## Data Sources

The following datasets were used in this project:

- **[Traffic Data](https://www.opendata.dk/city-of-copenhagen/faste-trafiktaellinger):** City of Copenhagen’s permanent traffic counting stations.
- **[Weather Data](https://open-meteo.com/en/docs/historical-weather-api?start_date=2005-01-01&end_date=2014-12-31&timezone=auto&latitude=55.6806&longitude=12.5492&hourly=temperature_2m,relative_humidity_2m,rain,snowfall,wind_speed_10m,weather_code,apparent_temperature,cloud_cover):** Historical weather data retrieved from Open-Meteo API.
- **[Holiday Data](https://www.timeanddate.com/holidays/denmark/):** Public holiday data for Denmark.
  - Note: This dataset was not available in CSV format, so we manually scraped each relevant year and compiled it into a CSV file.
- **[Bike Rides Data](https://www.kaggle.com/datasets/emilhvitfeldt/bike-traffic-counts-in-copenhagen):** Bicycle traffic counts in Copenhagen from Kaggle.
- **[Accidents Data](https://www.statbank.dk/UHELD4):** Road traffic accident data from Statistics Denmark (StatBank).

---

## Data Processing

### `trafficconverter.ipynb`

- Removes the initial non-data rows from the original traffic dataset.
- Converts UTM32 coordinates to latitude and longitude.
- Splits and saves data into separate CSV files per year.

### `datacombiner.ipynb`

- Merges the cleaned traffic data with the weather and holiday datasets.
- Reshapes the traffic data:
  Originally, each row represented a `(station, date)` pair and columns represented hourly counts.
  In the new format, each row represents a specific **datetime**, and **each station** is represented as its own set of columns.

- Handles missing data:
  Since not every station has data for every year, missing values are indicated with a traffic count of `-1`.

---

## Final Dataset Format

The final merged dataset contains the following columns:

| Column | Description |
|--------|-------------|
| `datetime` | Date and time in `YYYY-MM-DD HH:MM:SS` format |
| `stationX +` | Incoming traffic count for station X |
| `stationX -` | Outgoing traffic count for station X |
| `stationX T` | Total traffic count for station X |
| `temperature_2m (C)` | Air temperature at 2 meters above ground |
| `relative_humidity_2m (%)` | Relative humidity at 2 meters |
| `rain (mm)` | Hourly rainfall sum |
| `snowfall (cm)` | Hourly snowfall sum |
| `wind_wind_speed_10m (km/h)` | Wind speed at 10 meters |
| `weather_code (wmo code)` | Weather condition code (WMO standard) |
| `apparent_temperature (C)` | Feels-like temperature (based on wind, humidity, etc.) |
| `cloud_cover (%)` | Cloud cover as area fraction |
| `DayOfWeek` | Day of the week (e.g., "Monday") |
| `isHoliday` | Boolean indicating whether the date is a holiday |
| `isWeekend` | Boolean indicating weekend |
| `isWeekday` | Boolean indicating weekday |
| `holidayName` | Name of the holiday (e.g., "New Year's Day") |
| `holidayType` | Type of holiday (e.g., "National Holiday") |

> *Note:* Station identifiers are based on their IDs, not literal names like `station1`.

---

## Notes

- All code is structured to ensure reproducibility.
- Missing data is handled consistently and clearly marked.
- The dataset is now suitable for further analysis, such as time series forecasting, traffic trend visualization, or correlation analysis with weather and holiday variables.