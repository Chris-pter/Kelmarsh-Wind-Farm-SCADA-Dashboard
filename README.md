# Kelmarsh-Wind-Farm-SCADA-Dashboard

**Project Overview**
<p align="justify">
I created this interactive dashboard in Power BI to mimic a real SCADA (Supervisory Control and Data Acquisition) and GIS (Geographic Information System) monitoring dashboard for a wind turbine farm. The primary goal was to transform raw, operational data into a powerful tool for monitoring key performance indicators (KPIs), identifying trends, and optimizing the performance and maintenance of each turbine. By providing an intuitive interface, the dashboard empowers operations managers and maintenance teams to make data-driven decisions, proactively address issues, and ultimately maximize the wind farm's energy production.


**Data Source and Modeling**
* The data for this project is based on **secondary SCADA data**. This dashboard is designed to reflect the dynamic nature of SCADA systems, where data is updated frequentyly. While primary SCADA system provides real-time, high-freq data for immediate control and monitoring, this dashboard utilizes a pre-processed version of that data, which is updated every 10 minutes.

* The dataset was sourced from a research repository on [**Zenodo**](https://zenodo.org/records/5841834), where the raw data was provided in separated .xlsx/.csv files. These files contained a rich set of yearly variables, including **Wind Speed (m/s)**, **Power Output (kW)**, **Rotor Speed(RPM)**, and etc.

To prepare the data for analysis, I performed a data wrangling step. Using Excel, I first refined the yearly data from all six turbines to focus on the month of **January 2021** and then combined them into a single file. I then  uploaded this data to **Power Query** for further filtering and data modeling, a process essential for cleaning up missing values and ensuring consisten data types, which are vital for the dashboard's relevant and responsve analysis.

Within Power BI, I then built a simple **data model** with a **one-to-many relationship** ERD data model:
* **Fact Table:** Stores all the time-series data.
* **Dimension Table:** Holds static details for each turbine.

The design separates the data, ensuring efficiency, scalability, and seamless filtering while avoiding data duplication.

</p>
