# Data Description
The data structure follows a snowflake scheme.<br>
 → Primary Key referencing Foreign Key<br>
 ← Foreign Key referencing Primary Key

## DimLocation
The 'DimLocation' table is a dimensional table of the fictitious water monitoring stations. It contains seven rows (locations) and four column. GPS data have been retrieved from GoogleMaps on February 4th, 2025.

| Column Name   | Data Type     | Constraints          | Reference             | Cardinality | Direction | Description                             |
|---------------|---------------|----------------------|-----------------------|-------------|-----------|-----------------------------------------|
| Location ID   | INT           | PK                   | FactData(Location ID) | 1:M         | ←         | Unique identifier for each location     |
| Location Name | VARCHAR(50)   | UNIQUE, NOT NULL     |                       |             |           | Location of monitoring station          |
| Latitude      | DECIMAL(8,6)  | UNIQUE, NOT NULL     |                       |             |           | Latitude (WGS84) of monitoring station  |
| Longitude     | DECIMAL(8,6)  | UNIQUE, NOT NULL     |                       |             |           | Longitude (WGS84) of monitoring station |


## DimParameter
The 'DimParameter' table is a dimensional table of the water parameters that are measured at each location via sensors. The table contains 12 rows (parameters) and two columns.

| Column Name    | Data Type     | Constraints          | Reference              | Cardinality | Direction | Description                          |
|----------------|---------------|----------------------|------------------------|-------------|-----------|--------------------------------------|
| Parameter ID   | INT           | PK                   | FactData(Parameter ID) | 1:M         | ←         | Unique identifier for each parameter |
| Parameter Name | VARCHAR(50)   | UNIQUE, NOT NULL     |                        |             |           | Name of parameter                    |

 
## DimParameterDescription
The 'DimParameterDescription' table is a dimensional table of the water parameters that are measured at each location via sensors. The table contains 12 rows (parameters) and two columns.

| Column Name      | Data Type    | Constraints          | Reference                  | Cardinality | Direction | Description                            |
|------------------|--------------|----------------------|----------------------------|-------------|-----------|----------------------------------------|
| Parameter ID     | INT          | FK, UNIQUE, NOT NULL | DimParameter(Parameter ID) | 1:1         | ←→        | Identifier for parameter               |
| Description      | VARCHAR(255) | UNIQUE, NOT NULL     |                            |             |           | Description of parameter               |


## FactData
The 'FactData' table contains synthetically generated water parameter measurements for seven locations (detailed in the 'DimLocation' table). The dataset contains 30,660 rows (one daily measurement over 365 days for seven locations and 12 parameters each), and four columns.

| Column Name  | Data Type      | Constraints          | Reference                   | Cardinality | Direction | Description                         |
|--------------|----------------|----------------------|-----------------------------|-------------|-----------|-------------------------------------|
| Date         | Date           | NOT NULL             |                             |             |           | Unique identifier for each location |
| Location ID  | VARCHAR(50)    | FK, UNIQUE, NOT NULL | DimLocation(Location ID)    | M:1         | →         | Identifier for location             |
| Parameter ID | DECIMAL(8,6)   | FK, UNIQUE, NOT NULL | DimParameter(Parameter ID)  | M:1         | →         | Identifier for parametern           |
| Value        | DECIMAL(20,10) | UNIQUE, NOT NULL     |                             |             |           | Recorded value for measurement      |
