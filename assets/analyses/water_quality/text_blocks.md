#### Water quality monitoring (Dashboard)

In this project, I develop a Power BI dashboard to analyze and monitor water quality data form Florida’s gulf coast through visualization techniques. The goal is to provide a concise and easy to understand dashboard with visualizations that inform about the water quality of economically important areas.



#### Water quality monitoring (Dashboard)

The Data 
Data visualization techniques are used to show current and past water quality indicators and predict trends in kew water indicators over a large area. The visualization of water parameters and associated analyses allow to make decisions about water quality for the public (is it safe to swim), nature conservation policies (do we have to change something), and also the local property values (good water quality mean higher property values). The analysis integrates synthetic data generation and visualization to interpret large and complex, multifaceted ecological data. This project translates large-scale datasets into accessible insights and guiding evidence-based decision-making.



#### Introduction
Florida's Gulf Coast is one of the most breathtaking and idyllic regions in the world. Its shoreline is defined by white sandy beaches, warm waters, palm trees, and vast mangrove forests. The central and southern sections, stretching from Marco Island to Clearwater Beach, are particularly renowned for their wide, endless beaches with fine, powdery sand. It's no surprise that some of the most stunning beachfront mansions can be found here.<br>
This paradise comes with its own challenges. Devastating hurricanes make insuring these valuable properties a daunting task. Residents and tourists yet face another, often invisible threat—the very waters they admire so much. Pollutants such as heavy metals, red tide events, and harmful algal blooms (HABs) pose a persistent and growing risk to Florida’s tranquil Gulf Coast.<br>
This fictitious project monitors the water quality of Florida's scenic Gulf Coast. The collected data is presented through interactive dashboards and detailed reports published online, providing the public with a clear overview of current water conditions as well as in-depth insights into trends and patterns.


#### Scenario (fictitious)
Following the phosphate mine leak in 2023, residents of Florida’s central and southern Gulf Coast were deeply concerned about the potential health hazards and  its negative impact on their property value posed by contaminated waters near their homes. Recognizing the urgency, they decided to implement a monitoring system that tracks critical water parameters related to health risks, such as algal blooms and dangerous levels of pollution. The community coalition secured the necessary funding and permits to install water quality monitoring stations at seven locations along the Sunshine State’s coast, from Clearwater Beach in the north to Sanibel Island in the south.

The Oceanic Engineering Firm, which developed and installed the monitoring stations, tasked me with creating dashboards and reports to visualize the collected data. The goal was to provide intuitive and detailed insights, helping residents, the general public, and environmental conservation organizations make informed decisions regarding recreational activities and data-driven conservation actions to reduce health hazards and plumbing property values.

##### Scope
Through a comprehensive requirements analysis with stakeholders, we identified the following key requirements for the dashboards and reports:

* Dashboards and reports will be developed using Microsoft Power BI, a leading tool for advanced visualizations.
* One dashboard will display the locations of the seven monitoring stations on a map, with current water quality shown using a gauge diagram.
* The dashboard is interactive: by selecting a location (drilldown), users will be directed to a detailed report displaying the current water parameters for that location. Each parameter is presented with a visual scale indicating whether it is within good, critical, or high values.
* The report is interactive: by selecting a parameter value (drillthrough), users will be taken to a detailed report showing recorded values in a table, along with a line plot that reveals patterns and trends over time.


#### Data
Water quality data are readily accessible online, with many sources offering free use. However, complying with the policies set by data owners can be challenging, as these policies can change over time. For this project, it was essential to share both the original data and its derivatives. To ensure compliance with current and future data policies and to avoid potential violations, I opted to use synthetically generated data.<br>
The Python script used for data generation is provided below and is set up to ensure reproducibility. This means that every time the script is run, the same synthetic data will be produced.


Wastewater phosphate mine
https://www.floridamuseum.ufl.edu/earth-systems/blog/a-rundown-of-the-piney-point-wastewater-leak/
