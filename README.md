# Displacement Pulse

An interactive Power BI analysis of forced displacement by country of origin, built with official UNHCR Refugee Population Statistics data.

The dashboard follows 20 major displacement situations from 2015 to 2025 and separates the scale and composition of refugees, asylum-seekers, and internally displaced people. Its purpose is to help humanitarian analysts move quickly from a global overview to an origin-specific briefing.

> **Default-view note:** headline cards aggregate the selected origin-year rows across 2015–2025. Select one year to read an annual stock. Coverage is limited to the 20 largest origins by the 2025 dashboard total and is not a whole-world estimate.

## Analytical questions

- Which origin countries account for the largest recorded displaced populations?
- How has the composition of displacement changed over time?
- Where is displacement primarily internal, and where is it cross-border?
- How do refugee and asylum-seeker trends compare with internal displacement?
- What does the latest available year show for a selected origin or region?

## Dashboard pages

### Executive Overview

A situation-room view of total recorded displacement, population composition, the 2015–2025 trajectory, and the largest origin-country situations. Region and year controls update the analytical view.

### Displacement Dynamics

An animated origin-year analysis designed to reveal changes in displacement scale and composition through time, supported by a ranked pressure view.

### Origin Explorer

A focused briefing for a selected country of origin, combining headline measures, historical movement, and a benchmark table for cross-country comparison.

### Methodology & Sources

Definitions, calculation logic, source coverage, refresh date, analytical assumptions, and limitations are documented inside the report.

## Measures

- Refugees under UNHCR’s mandate
- Asylum-seekers with pending cases
- Internally displaced people reported in the source dataset
- Total displayed displacement, calculated as the sum of the dashboard’s displayed population categories
- Origin count and latest reporting year
- Internally displaced share and selected-origin share

## Design and development

- Power BI Project (`.pbip`) format for transparent, version-controllable report and semantic-model definitions
- Power Query ingestion from a documented local CSV extract
- DAX measures for totals, shares, coverage, and filter-aware calculations
- Editorial humanitarian visual system using an asymmetric situation-room layout
- Interactive region, origin, and year controls
- Four-page information hierarchy from global monitoring to country-level exploration

## Data source

- UNHCR Refugee Population Statistics API documentation: https://api.unhcr.org/docs/refugee-statistics.html
- Population endpoint: https://api.unhcr.org/population/v1/population/
- Dashboard coverage: 2015–2025
- Selection: 20 largest origins by the latest-year dashboard total
- Data retrieved: 10 August 2026

## Limitations

UNHCR notes that figures may be provisional and subject to revision. Availability varies by population type, country, and year. The dashboard total is an analytical sum of the categories presented in this model; it should not be substituted for UNHCR’s separately published global forced-displacement headline, which may reconcile additional mandates and data sources.

The dashboard describes recorded displacement patterns and does not infer causality.

## Open the project

1. [Download the Power BI project archive](Displacement_Pulse_Power_BI_Project.rar) and extract it.
2. Open `DisplacementPulse.pbip` using a recent version of Power BI Desktop.
3. If Power Query requests the source location, select `data/displacement_by_origin.csv` from the extracted project folder.

Preview the completed dashboard: [open the PDF](Displacement_Pulse_Dashboard.pdf).

## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel
