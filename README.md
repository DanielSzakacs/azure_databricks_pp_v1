# 🌍 Global Earthquake Data Pipeline & Analytics Dashboard

This project demonstrates an end-to-end data engineering pipeline built with **Azure Databricks** and **Azure Data Lake Storage Gen2**, using public earthquake data from the **USGS Earthquake API**.

The solution follows the **Medallion Architecture** pattern: **Bronze → Silver → Gold**, and ends with an analytics dashboard built in **Databricks SQL**.

---

## Project Overview

- **Data Source:** [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)
- **Ingestion Schedule:** Daily at 06:00
- **Processing Engine:** Azure Databricks
- **Storage:** Azure Data Lake Storage Gen2
- **Architecture:** Medallion Architecture
- **Visualization:** Databricks SQL Dashboard

---

## Architecture

The pipeline processes earthquake data through three structured layers:

- **Bronze Layer:** raw API data
- **Silver Layer:** cleaned and structured data
- **Gold Layer:** analytics-ready data for reporting

<p align="center">
  <img src="docs/img/architecture-diagram.png" width="850">
</p>

---

## Pipeline Flow

1. A scheduled Databricks Job runs every morning at **06:00**.
2. The **Bronze notebook** calls the USGS Earthquake API and saves raw data into the Bronze layer.
3. The **Silver notebook** reads from Bronze, cleans and structures the data, then writes the result to Silver.
4. The **Gold notebook** reads from Silver, prepares dashboard-ready data, and writes it to Gold.
5. The **Databricks SQL Dashboard** reads from the Gold table and visualizes the results.

---

## Databricks Workflow

The pipeline is orchestrated as a Databricks Workflow with Bronze, Silver, and Gold notebook tasks.

<p align="center">
  <img src="docs/img/databricks-workflow.png" width="850">
</p>

---

## Dashboard

The final dashboard provides a concise overview of global earthquake activity across location, magnitude, and significance.

<p align="center">
  <img src="docs/img/dashboard-overview.png" width="900">
</p>

---

## Dashboard Highlights

### Global Earthquake Map

<p align="center">
  <img src="docs/img/earthquake-map.png" width="850">
</p>

### Magnitude Distribution

<p align="center">
  <img src="docs/img/magnitude-distribution.png" width="700">
</p>

### Top Countries by Earthquake Count

<p align="center">
  <img src="docs/img/top-countries-chart.png" width="750">
</p>

### Top Earthquake in USA

<p align="center">
  <img src="docs/img/top-earthquake-events-table.png" width="850">
</p>

---

## Dashboard Export

A PDF export of the dashboard is available here:

```text
dashboard/earthquake-dashboard.pdf
```
