# Displacement Pulse

An interactive Power BI analysis of forced displacement by country of origin, built with official UNHCR Refugee Population Statistics data.

The dashboard follows 19 named origins plus one `Unknown` origin bucket from 2015 to 2025 and separates the scale and composition of refugees, asylum-seekers, and internally displaced people. Its purpose is to help humanitarian analysts move quickly from a global overview to an origin-specific briefing.

> **Default-view note:** headline cards show the latest year in the current Year selection (2025 when all years are selected). Line charts still show each annual stock. The data covers 19 named origins and an `Unknown` bucket; it is not a whole-world estimate.

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
- Selection: 19 named origins plus an `Unknown` bucket in the supplied extract. The underlying full-source ranking and selection query were not preserved, so a strict “top 20 countries” claim cannot be verified. The `Unknown` bucket must not be presented as a country.
- Data retrieved: 10 August 2026

## Limitations

UNHCR notes that figures may be provisional and subject to revision. Availability varies by population type, country, and year. The dashboard total is an analytical sum of the categories presented in this model; it should not be substituted for UNHCR’s separately published global forced-displacement headline, which may reconcile additional mandates and data sources.

The dashboard describes recorded displacement patterns and does not infer causality. Its CSV is an extract rather than a fully reproducible API result: the exact request parameters, extraction script and response identifiers are absent. The stated retrieval date is from the supplied project documentation and cannot be verified from the CSV alone.


## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel

## Open and inspect the report

- [Preview the dashboard PDF](Displacement_Pulse_Dashboard.pdf). A PDF is a static export; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/displacement-pulse-dashboard/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`DisplacementPulse.pbip`](project/DisplacementPulse.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository's public `main` branch. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

**Category correction:** The model total now sums refugees, asylum-seekers, and IDPs only. The CSV source also has an `Other People in Need` column (27.662 million across all origin-years), which the old total included. The earlier PDF export shows an old 795.2 million multi-year aggregate. The corrected 2025 three-category stock for this extract is 90,573,559 people. The model now uses the latest year in the Year filter for headline cards and ranking visuals, while time-series charts retain annual context. Re-export the PDF from Power BI Desktop.
