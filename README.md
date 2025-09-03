# Kelmarsh-Wind-Farm-SCADA-Dashboard

**Project Overview**
<p align="justify">
I created this interactive dashboard in Power BI to mimic a real SCADA (Supervisory Control and Data Acquisition) and GIS (Geographic Information System) monitoring dashboard for a wind turbine farm. The primary goal was to transform raw, operational data into a powerful tool for monitoring key performance indicators (KPIs), identifying trends, and optimizing the performance and maintenance of each turbine. By providing an intuitive interface, the dashboard empowers operations managers and maintenance teams to make data-driven decisions, proactively address issues, and ultimately maximize the wind farm's energy production.

---

**Data Source and Modeling**
* The data for this project is based on **secondary SCADA data**. This dashboard is designed to reflect the dynamic nature of SCADA systems, where data is updated frequently.

* While primary SCADA system provides real-time, high-freq data for immediate control and monitoring, this dashboard utilizes a pre-processed version of that data, which is updated every 10 minutes.

* The dataset was sourced from a research repo on [**Zenodo**](https://zenodo.org/records/5841834), where the raw data was provided in separated .xlsx/.csv files. These files contained a rich set of yearly variables, including **Wind Speed (m/s)**, **Power Output (kW)**, **Rotor Speed(RPM)**, and etc.

To prepare the data for analysis, I performed a data wrangling step. Using Excel, I first refined the yearly data from all six turbines to focus on the month of **January 2021** and then combined them into a single file. I then  uploaded this data to **Power Query** for further filtering and data modeling, a process essential for cleaning up missing values and ensuring consisten data types, which are vital for the dashboard's relevant and responsve analysis.

Within Power BI, I then built a simple **data model** with a **one-to-many relationship** ERD data model:
* **Fact Table:** Stores all the time-series data.
* **Dimension Table:** Holds static details for each turbine.

The design separates the data, ensuring efficiency, scalability, and seamless filtering while avoiding data duplication.

---

**Key Features and Visualizations**

This dashboard provides a comprehensive look at the wind farm's operations through several key visualizations:

1. **Turbine Locations:** An Esri map provides a geographical overview, simulating GIS integration for asset management. Users can click on individual turbines to filter the dashboard and gain detailed, localized performance view.
2. **Key Performance Indicators (KPIs:** At-a-glance cards show essential metrics like total power output and average wind speed. They serve as a quick reference for daily performance checks, informing decisions on total energy generated and overall operational efficiency.
3. **Comparative Performance:** Bar charts compare each turbine's average power output and uptime, enabling quick identification of underperforming units and supporting targeted maintenance investigations.
4. **Operational Trends:** A time-series line graph visualizes how total power output, offline time, and wind speed have changed over the month. This helps in revealing operational patterns and trends, which supports future performance forecasting and scheduling.
5. **Performance Curve:** A scatter plot demonstrates the relationship between  wind speed and power output. This visualization is crucial for confirming that turbines are operating efficiently and align with their expected power curve.

</p>
