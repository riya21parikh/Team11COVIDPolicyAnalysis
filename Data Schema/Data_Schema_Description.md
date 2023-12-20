# Data Schema Description

## Fact Tables

- **CASES**: Records of COVID-19 cases with details on confirmed cases and the changes over time.
- **DEATHS**: Records of COVID-19 related deaths and the changes over time.
- **RECOVERIES**: Records of COVID-19 recoveries and the changes over time.
- **LOBSTER-DATA**: Records of lobster exports, which are events that can be measured over time.

## Dimension Tables

- **DATE**: Attributes related to dates, which can be used for temporal analysis.
- **GEOGRAPHY**: Descriptive information about locations for geographic analysis.
- **POLICIES**: Descriptive attributes regarding COVID-19 policies that can be used to analyze their impact on the fact tables.
- **POPULATION-DENSITY**: Descriptive information about the population density of regions.

## Schema Type

The schema is a **Hybrid Starflake** schema, which exhibits characteristics of both star and snowflake schemas. It maintains a central focus on fact tables with dimensions around them, while allowing for some normalization in dimensions such as `GEOGRAPHY` and `POLICIES`.

## Reference

1. [Starflake schemas, IBM InfoSphere Data Architect](https://www.ibm.com/docs/en/ida/9.1.2?topic=schemas-starflake)