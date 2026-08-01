# Buenos Aires Ecobici Data Warehouse and Power BI

## Overview

This project analyzes Buenos Aires Ecobici bike-sharing trips by integrating information from multiple data sources into a dimensional data warehouse and creating a Power BI dashboard for data analysis and visualization.

The project combines trip, user and station information to build a structured analytical dataset that can be used to explore usage patterns and user behavior.

## Data Sources

The project uses three main datasets:

- `Trips.csv` — Bike-sharing trip records.
- `usuarios_ecobici_2026.csv` — User information.
- `nuevas-estaciones-bicicletas-publicas.csv` — Ecobici station information.

## Data Warehouse

A dimensional model was created using a fact table and several dimension tables.

### Fact Table

**DW_Fact_Viajes**

Contains the main trip-related measures and keys:

- `Id_recorrido`
- `id_tiempo`
- `id_estacion_origen`
- `id_estacion_destino`
- `id_usuario`
- `duracion_recorrido`

### Dimension Tables

**DW_Dim_Tiempo**

Contains time-related attributes:

- Year
- Month
- Day
- Hour

**DW_Dim_Usuarios**

Contains user information and includes age ranges and gender.

**DW_Dim_Estaciones**

Contains station information such as:

- Station name
- Commune
- Neighborhood
- Address
- Latitude
- Longitude

## Data Transformation

The project uses Python and Pandas to prepare the data for the data warehouse.

Main transformations include:

- Date and time conversion
- Creation of a unique time identifier
- Extraction of year, month, day and hour
- Creation of user age ranges
- Standardization of identifier column names
- Selection of relevant attributes
- Construction of the fact table
- Removal of incomplete records
- Generation of CSV files for the dimensional model

## Power BI Dashboard

The resulting data warehouse is used as the data source for a Power BI dashboard.

The dashboard allows the analysis and visualization of Ecobici usage data from different perspectives, including trips, users, stations and time.

**Power BI file:** `PowerBIEcobicis.pbix`

## Tools and Technologies

- Python
- Pandas
- Jupyter Notebook
- Power BI
- Data Warehousing
- Dimensional Modeling
- Data Visualization

## Project Structure

```text
ba-ecobici-data-warehouse-powerbi/
│
├── BAEcobicisAnalysis.ipynb
│
├── data/
│   ├── Trips.csv
│   ├── usuarios_ecobici_2026.csv
│   └── nuevas-estaciones-bicicletas-publicas.csv
│
├── data_warehouse/
│   ├── DW_Fact_Viajes.csv
│   ├── DW_Dim_Usuarios.csv
│   ├── DW_Dim_Tiempo.csv
│   └── DW_Dim_Estaciones.csv
│
├── PowerBIEcobicis.pbix
└── README.md
