# COVID 19 Analysis Project

**Team 11: DS 310 - Data Mechanics**

## Project Overview

This project encompasses a comprehensive analysis of the impact of various COVID-19 policies on the progression of the pandemic, using real-world data and robust data processing tools. We aim to understand how different policies, specifically those related to public transportation and testing, influence key metrics such as confirmed cases, recoveries, and deaths.

### Data Collection and Integration
We extracted COVID data from multiple sources and consolidated it in a data lake using Azure Data Factory. This centralized collection includes detailed records of cases, deaths, recoveries, policy implementations, and supplementary data such as population density and economic indicators.

### Transformation and Storage
The raw data underwent a transformation process to structure it into fact and dimension tables within an operational data store (ODS). The tables were then loaded as external tables into Azure Synapse for advanced big data processing.

### Data Modeling and Analysis
Our team structured the data into a schema suitable for Power BI analysis. We designed and implemented a star/snowflake schema, ensuring proper relationships among the fact and dimension tables. This schema facilitated our examination of the effectiveness of COVID policies over time and across different geographies.

### Visualizations and Insights
Using Power BI, we created visualizations that represent the trends and correlations in the data. We analyzed the effectiveness of our assigned policies - closing public transportation and testing policy for symptomatic individuals - against the backdrop of overall policy measures and their impact on pandemic trends.


## Repository Structure

- `Azure Data Factory/`: Contains the Azure Data Factory resources including credentials, dataflows, datasets, and pipelines necessary for the ETL processes.
  - `credential/`: Credentials required for accessing different services.
  - `dataflow/`: Dataflow definitions for data transformation.
  - `dataset/`: Definitions of datasets used in the data factory.
  - `factory/`: Configuration files for the Azure Data Factory instance.
  - `integrationRuntime/`: Runtime environment for data integration.
  - `linkedService/`: Connection strings and service links.
  - `pipeline/`: Data processing pipelines.
- `Azure Synapse Analytics`:
  - `sqlscript/`: SQL scripts for data manipulation and management.
- `Data Architecture/`: Visual representations of the data architecture, including diagrams in different formats for easy viewing and editing.
- `Data Schema/`: Detailed descriptions and visualizations of the data schema used in the project, including markdown and mermaid diagram files.
- `Power BI/`: Power BI files and related resources for data visualization and reporting.

## Data Schema Description

### Fact Tables

- **CASES**: Records of COVID-19 cases with details on confirmed cases and the changes over time.
- **DEATHS**: Records of COVID-19 related deaths and the changes over time.
- **RECOVERIES**: Records of COVID-19 recoveries and the changes over time.
- **LOBSTER-DATA**: Records of lobster exports, which are events that can be measured over time.

### Dimension Tables

- **DATE**: Attributes related to dates, which can be used for temporal analysis.
- **GEOGRAPHY**: Descriptive information about locations for geographic analysis.
- **POLICIES**: Descriptive attributes regarding COVID-19 policies that can be used to analyze their impact on the fact tables.
- **POPULATION-DENSITY**: Descriptive information about the population density of regions.

### Schema Type

The schema is a **Hybrid Starflake** schema, which exhibits characteristics of both star and snowflake schemas. It maintains a central focus on fact tables with dimensions around them, while allowing for some normalization in dimensions such as `GEOGRAPHY` and `POLICIES`.

## Datasets

The analysis is based on the following datasets from Azure SQL, Azure Cosmos DB, and also a virtual machine within the Azure Resource Group environment:
- **Cases**: COVID-19 confirmed cases, including daily updates on the number of confirmed cases globally.
- **Deaths**: COVID-19 related deaths, detailing the daily death toll across different regions.
- **Recoveries**: COVID-19 recoveries, tracking the number of individuals recovering from the virus.
- **Policies**: Various COVID-19 policies implemented by countries, covering aspects like lockdowns, mask mandates, and social distancing regulations.
- **Dates**: A dataset representing time dimensions, with details like date keys, weekdays, and fiscal quarters, critical for time-series analysis.
- **Geography**: Geographical data that includes country names, codes, and geospatial coordinates, which is used for mapping and location-based analysis.

For a comprehensive and multifaceted analysis, we also incorporate two additional datasets:
- **Population Density**: Information about the population density of various regions, providing context for the spread and impact of COVID-19.
- **Lobster Exports**: Data on lobster exports, which may be used to analyze economic impacts related to the pandemic and policy decisions.

These datasets are transformed and loaded into Azure Synapse for big data processing and analyzed using Power BI.

## Tools and Technologies

- Azure SQL Database
- Azure Cosmos Database
- Azure Data Factory
- Azure Synapse Analytics
- Microsoft Power BI
- Git and GitHub

## Team Members
- George Jiang
- Hannah Choe
- Jaden Hsiao
- Riya Parikh
- Tracy Cui
- Xiang Fu