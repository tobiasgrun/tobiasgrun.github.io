# Data Description
## DimLocation
The .csv table 'DimLocation.csv' contains GPS locations (WGS84) of ficticious sample sites retrieved from Google Maps on February 4th, 2025.<br>
The table contains seven data rows (locations) and four columns:
#### Columns
* **Location ID:** Primary key. Unique identifier for each location.
* **Location Name:** Name of the closest landmark in natural language.
* **Latitude:** Latitude, precision: 6 digits.
* **Longitude:** Longitude, precision: 6 digits.
#### Relation
* **Primary Key:** 'Location ID'
* **Relates to:**
  * 'FactData.csv', Foreign Key: 'Location ID', Cardinality: 'one-to-many', Direction: 'single'.

## DimParameter
The .csv table 'DimParameter.csv' contains water parameters measured in this ficticious project.<br>
The table contains 12 data rows (parameters) and xxx columns:
#### Columns
* **Parameter ID:** Primary key. Unique identifier for each Parameter.
* **Parameter Name:** Name of the closest landmark in natural language.
#### Relation
* **Primary Key:** 'Parameter ID'
* **Relates to:**
  * 'FactData.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-many', Direction: 'single'.
  * 'DimParameterDescription.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-many', Direction: 'single'.
 
## DimParameterDescription
The .csv table 'DimParameterDescription.csv' contains descriptions of the meaning of measured water parameters and their impact on potential health hazards.<br>
The table contains 12 data rows (parameters) and two columns:
#### Columns
* **Parameter ID:** Primary key. Unique identifier for each Parameter.
* **Parameter Description:** Description of meaning and impact on potential health hazards in natural language.
#### Relation
* **Primary Key:** 'Parameter ID'
* **Relates to:**
  * 'DimParameter.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-one', Direction: 'both'.

## FactData
The .csv table 'FactDada.csv' contains synthetically generated water parameter measurements for seven locations detailed in the 'DimLocation.csv' file. The dataset contains 30,660 rows (one daily measurement over 365 days for seven locations and 12 parameters each), and 12 columns:
#### Columns
* **Date:** Date of measurement.
* **Location ID:** Links the measurement to a unique location. Key for 'DimLocation.csv' tabel with column 'Location ID'.
* **Parameter ID:** Links the measurement to a unique water parameter. Key for 'DimParameter.csv' tabel with column 'Parameter ID'.


* **Nitrate [mg/L]:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Phosphate [mg/L]:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Silicia [mg/L]:** Nutrient indicator for water quality, measured in mg per Liter.
* **Karenia brevis [cells/L]:** Algae species responsible for red tide events, measured in cells per Liter.
* **Water Temperature [°C]:** Surface Water Temperature, measured in °Celcius.
* **Salinity [ppm]:** Salinity of water, measured in parts per million.
* **Dissolved Oxygen [mg/L]:** Key indicator for water quality. Records the amaount of dissolved oxygen in the water, measured in mg per Liter.
* **pH [pH]:** Nutrient indicator for water acidity, recorded as power of the Hydrogen ion (pH).
* **Turbidity [NTU]:** Measure of water quality, recorded as Nephelometric Turbidity unit (NTU).
