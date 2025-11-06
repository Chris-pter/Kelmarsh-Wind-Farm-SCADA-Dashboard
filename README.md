# Kelmarsh-Wind-Farm-SCADA-Dashboard

<p align="center">
  <img src="Images/Kelmarsh Wind Farm Scada Overview.jpg" width="1000">
</p>

**Project Overview**
<p align="justify">
I created this interactive dashboard in Power BI to mimic a real SCADA (Supervisory Control and Data Acquisition) and GIS (Geographic Information System) monitoring dashboard for a wind turbine farm. The primary goal was to transform raw, operational data into a powerful tool for monitoring key performance indicators (KPIs), identifying trends, and optimizing the performance and maintenance of each turbine. By providing an intuitive interface, the dashboard empowers operations managers and maintenance teams to make data-driven decisions, proactively address issues, and ultimately maximize the wind farm's energy production.
  
---
**Key Features and Visualizations**

This dashboard provides a comprehensive look at the wind farm's operations through several key visualizations:

1. **Turbine Locations:** An Esri map provides a geographical overview, simulating GIS integration for asset management. Users can click on individual turbines to filter the dashboard and gain detailed, localized performance view.
2. **Key Performance Indicators (KPIs:** At-a-glance cards show essential metrics like total power output and average wind speed. They serve as a quick reference for daily performance checks, informing decisions on total energy generated and overall operational efficiency.
3. **Comparative Performance:** Bar charts compare each turbine's average power output and uptime, enabling quick identification of underperforming units and supporting targeted maintenance investigations.
4. **Operational Trends:** A time-series line graph visualizes how total power output, offline time, and wind speed have changed over the month. This helps in revealing operational patterns and trends, which supports future performance forecasting and scheduling.
5. **Performance Curve:** A scatter plot demonstrates the relationship between  wind speed and power output. This visualization is crucial for confirming that turbines are operating efficiently and align with their expected power curve.

---

<p align="center">
  <img src="Images/Kelmarsh Wind Farm SCADA Overview.gif" width="1000">
</p>

---

**Data Source and Modeling**
* The data for this project is based on **secondary SCADA data**. This dashboard is designed to reflect the dynamic nature of SCADA systems, where data is updated frequently.

* While primary SCADA system provides real-time, high-freq data for immediate control and monitoring, this dashboard utilizes a pre-processed version of that data, which is updated every 10 minutes.

* The dataset was sourced from a research repo on [**Zenodo**](https://zenodo.org/records/5841834), where the raw data was provided in separated .xlsx/.csv files. These files contained a rich set of yearly variables, including **Wind Speed (m/s)**, **Power Output (kW)**, **Rotor Speed(RPM)**, and etc.

To prepare the data for analysis, I performed a data wrangling step. Using Excel, I first refined the yearly data from all six turbines to focus on the month of **January 2021** and then combined them into a single file. I then  uploaded this data to **Power Query** for further filtering and data modeling, a process essential for cleaning up missing values and ensuring consisten data types, which are vital for the dashboard's relevant and responsve analysis.

Within Power BI, I then built a simple **data model** with a **one-to-many relationship** ERD data model:
* **Fact Table:** Stores all the time-series data.
* **Dimension Table:** Holds static details for each turbine.

You can find the raw data files in the [Data Folder](Data) in this repo

The design separates the data, ensuring efficiency, scalability, and seamless filtering while avoiding data duplication.

<p align="center">
  <img src="Images/Kelmarsh Wind Farm  Data Model.jpg" width="700">
</p>

---

**A Story From The Data**
1. The data from January 2021 tells a clear  story about the Kelmarsh Wind Farm. Overall, the KPI cards shows a steady month of operation. However, the line graph of operational trends revelas that total power output followed the changes in average wind speed, which is exactly what we want to see.

2. By looking at the bar charts, we can see that most turbines performed weoo, but some, like the KWF4, had lower power output and more downtime. This is an important clue that KWF4 might have needed maintenance or had an ongoing issue.

3. The scatter plot confirms that all turbines are operating efficiently. As the wind speed went up, so did the power output, proving the farm's design is working correctly. This view also helps us understand why the total power output changed throughout the month as it was tied directly to the available wind.

4. The Esri Map provides the physical context fir all of this data. If we were managing the farm, we would click on KWF4 on the map to get a closer look at its specific details and plan a maintenance check for it.

---

**Visualization Logic**

I choose each visualization to present the data in the clearest and most effective way:
* **Esri Map:** This map provides a geographical overview, which is essential for a physical asset like a wind farm. It helps users quickly see the location of each turbine and allows them to click on a specific one to see its performance.
* **KPI Card:** These are used for a quick, at-a-glance health check. By putting the most important numbers in a clear, card format, users can see the current status of the farm instantly.
* **Bar Charts:** Bar charts are ideal for comparing values across different categories. In this case, they make it easy to directly compare the performance of each individual turbine against the others.
* **Line Graph:** A line graph is the best way to show how data changes over a period of time. This helps in spotting trends and patterns in power output, downtime, and wind speed.
* **Scatter Plot:** A scatter plot is perfect for showing the relationship between two different data points. This visualization clearly shows if a turbine's power output is increasing with wind speed, confirming that it's operating correctly.

---

**Technologies and Skill Used**
* **Power BI**: Used for building a powerful and easy-to-use dashboard.
* **Power Query**: Used to clean and prepare the raw data.
* **Data Modeling**: Designed a simple model to make the dashboard efficient.
* **Esri**: Used for adding geographical data and location-based insights.
* **Data Analysis**: Focused on finding key trends and issues to provide useful insights.

---

**How to View the Dashboard**

1. **View the Screenshot**: You can see a high-res image of the dashboard in this repo.
2. **Open the .pbix File**: If you have Power BI Desktop, you can download from the [Dashboard Folder](Dashboard) or clone this repo to your machine and open the Kelmarsh Wind Farm SCADA Overview.pbix file to interact with the dashboard yourself.
