# Data Description
## DimLocation
The .csv table 'DimLocation.csv' contains GPS locations (WGS84) of ficticious sample sites retrieved from Google Maps on February 4th, 2025.<br>
The table contains seven data rows (locations) and four columns.
#### Rows (locations)
* Boca Grande
* Clearwater Beach
* Indian Shores
* Sanibel Island
* Siesta Key
* St. Pete Beach
* Venice Beach
#### Columns
* **Location ID:** Primary key. Unique identifier for each location.
* **Location Name:** Name of the closest landmark in natural language.
* **Latitude:** Latitude, precision: 6 digits.
* **Longitude:** Longitude, precision: 6 digits.
#### Relation
* **Primary Key:** 'Location ID'
* **Relates to:**
  * Table: 'FactData', Foreign Key: 'Location ID', Cardinality: 'one-to-many', Direction: 'single'

## DimParameter
The .csv table 'DimParameter.csv' contains water parameters measured in this ficticious project.<br>
The table contains 12 data rows (parameters) and xxx columns.
#### Rows (parameters)
* **Water Temperature:** Surface Water Temperature, measured in °Celcius.
* **Salinity:** Salinity of water, measured in parts per million.
* **pH:** Nutrient indicator for water acidity, recorded as power of the Hydrogen ion (pH)
* **Dissolved Oxygen:** Key indicator for water quality. Records the amaount of dissolved oxygen in the water, measured in mg per Liter.
* **Nitrate:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Phosphate:** Key nutrient indicator for trophy level, recorded as mg per Liter.
* **Silicia:** Nutrient indicator for water quality, measured in mg per Liter.
* **Karenia brevis:** Algae species responsible for red tide events, measured in cells per Liter.
* **Biochemical Oxygen Demand:** BOD. Amount of oxygen consumed by microorganism in a defined space over a defined periode of time, measured in mg per Liter.
* **Escherichia coli:** Bacteria present in fecies of mamals, measured as colony forming units.
* **Enterococcus:** Bacteria present in fecies of mamals, measured as colony forming units.
#### Columns
* **Parameter ID:** Primary key. Unique identifier for each Parameter.
* **Parameter Name:** Name of the closest landmark in natural language.
#### Relation
* **Primary Key:** 'Parameter ID'
* **Relates to:**
  * 'FactData.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-many', Direction: 'single'
  * 'DimParameterDescription.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-many', Direction: 'single'
 
## DimParameterDescription
The .csv table 'DimParameterDescription.csv' contains descriptions of the meaning of measured water parameters and their impact on potential health hazards.<br>
The table contains 12 data rows (parameters) and two columns:
#### Columns
* **Description ID:** Primary key. Unique identifier for each Description.
* **Parameter ID:** Foreign key. Unique identifier for each Parameter.
* **Parameter Description:** Description of meaning and impact on potential health hazards in natural language.
#### Relation
* **Primary Key:** 'Description ID'
* **Foreign Key:** 'Parameter ID'
* **Relates to:**
  * 'DimParameter.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-one', Direction: 'both'

## FactData
The .csv table 'FactDada.csv' contains synthetically generated water parameter measurements for seven locations detailed in the 'DimLocation.csv' file. The dataset contains 30,660 rows (one daily measurement over 365 days for seven locations and 12 parameters each), and 12 columns:
#### Columns
* **Date:** Date of measurement.
* **Location ID:** Links the measurement to a unique location. Key for 'DimLocation.csv' tabel with column 'Location ID'.
* **Parameter ID:** Links the measurement to a unique water parameter. Key for 'DimParameter.csv' tabel with column 'Parameter ID'.
* **Value:** Value of the water parameter measurement.
#### Relation
* **Foreign Keys:** 'Location ID', 'Location ID'
* **Relates to:**
  * 'DimParameter.csv', Foreign Key: 'Parameter ID', Cardinality: 'one-to-one', Direction: 'both'



| Table Name | Column Name  | Data Type      | Constraints          | Description                  |
|------------|-------------|---------------|----------------------|------------------------------|
| Customers  | CustomerID  | INT           | PK, AUTO_INCREMENT  | Unique identifier for customer |
| Customers  | FirstName   | VARCHAR(50)   | NOT NULL            | Customer's first name         |
| Customers  | LastName    | VARCHAR(50)   | NOT NULL            | Customer's last name          |
| Customers  | Email       | VARCHAR(100)  | UNIQUE, NOT NULL    | Customer's email              |
| Customers  | Phone       | VARCHAR(15)   | NULLABLE            | Customer's phone number       |
| Customers  | CreatedAt   | TIMESTAMP     | DEFAULT NOW()       | Timestamp of creation         |
| Orders     | OrderID     | INT           | PK, AUTO_INCREMENT  | Unique identifier for order   |
| Orders     | CustomerID  | INT           | FK (Customers)      | Associated customer           |
| Orders     | OrderDate   | DATE          | NOT NULL            | Date of the order             |
| Orders     | TotalAmount | DECIMAL(10,2) | NOT NULL            | Total order amount            |
