# Data Description
## Locations
The .csv table 'locations.csv' contains the GPS locations (WGS84) retrieved from Google Maps on February 4th, 2025, where samples were collected. The table contains seven data rows (locations) and three columns:
#### Columns
* **Location:** Name of the closest landmark in natural language.
* **Latitude:** Latitude, precision: 6 digits.
* **Longitude:** Longitude, precision: 6 digits.

## Synthetic Data
The .csv table 'synthetic_water_quality_data' contains generated water parameters as indicators for water quality for seven locations detailed in the 'location.csv' file. The dataset contains XXX rows (one daily measurement over 365 days for seven locations) and 12 columns:
#### Columns
* **Date:** Date of measurement.
* **Location:** Name of sample site. Primary key for 'location.csv' tabel with column 'Location'.
* **Nitrate [mg/L]:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Phosphate [mg/L]:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Silicia [mg/L]:** Nutrient indicator for water quality, measured in mg per Liter.
* **Karenia brevis [cells/L]:** Algae species responsible for red tide events, measured in cells per Liter.
* **Water Temperature [°C]:** Surface Water Temperature, measured in °Celcius.
* **Salinity [ppm]:** Salinity of water, measured in parts per million.
* **Dissolved Oxygen [mg/L]:** Key indicator for water quality. Records the amaount of dissolved oxygen in the water, measured in mg per Liter.
* **pH [pH]:** Nutrient indicator for water acidity, recorded as power of the Hydrogen ion (pH).
* **Turbidity [NTU]:** Measure of water quality, recorded as Nephelometric Turbidity unit (NTU).
