# Displacement Pulse

## Files

- [Open the Power BI dashboard](DisplacementPulse.pbix) in Power BI Desktop.
- [Read the PDF analytical preview](Displacement_Pulse_Dashboard.pdf). This PDF summarises independently checked figures; it is not yet a page-for-page export of the PBIX. A matching PDF export is pending verification in Power BI Desktop.

The PBIX is the single-file dashboard. A data refresh may need network access to its saved source URLs.

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

- Power BI Desktop (`.pbix`) report and semantic model
- Power Query ingestion from a documented local CSV extract
- DAX measures for totals, shares, coverage, and filter-aware calculations
- Editorial humanitarian visual system using an asymmetric situation-room layout
- Interactive region, origin, and year controls
- Four-page information hierarchy from global monitoring to country-level exploration

## Data source

- UNHCR Refugee Population Statistics API documentation: https://api.unhcr.org/docs/refugee-statistics.html
- Population endpoint: https://api.unhcr.org/population/v1/population/
- Dashboard coverage: 2015–2025
- Selection: 19 named origins plus an `Unknown` bucket in the supplied extract. The underlying full-source ranking and selection query were not preserved, so a strict “top 20 countries” claim cannot be verified. The `Unknown` bucket must not be presented as a country.
- Data retrieved: 10 August 2026

## Limitations

UNHCR notes that figures may be provisional and subject to revision. Availability varies by population type, country, and year. The dashboard total is an analytical sum of the categories presented in this model; it should not be substituted for UNHCR’s separately published global forced-displacement headline, which may reconcile additional mandates and data sources.

The dashboard describes recorded displacement patterns and does not infer causality. Its CSV is an extract rather than a fully reproducible API result: the exact request parameters, extraction script and response identifiers are absent. The stated retrieval date is from the supplied project documentation and cannot be verified from the CSV alone.


## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel
