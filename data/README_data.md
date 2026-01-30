# Dataset Documentation (analysis_dataset.csv)

## Overview
`analysis_dataset.csv` (DOI: 10.5061/dryad.7pvmcvf7r) contains the anonymized analytical dataset used to generate the descriptive figures and to train/evaluate the predictive models reported in the manuscript.


Each row corresponds to a single annual observation of a rural water service (aggregated at the service-year level, e.g., waterpoint-year or scheme-year depending on infrastructure type).

All monetary values are in USD.

---

## Column Dictionary

### A) Identifiers and basic descriptors
- `year`  
  Calendar year of the observation.

- `wp_type_cat`  
  Infrastructure category (e.g., Handpump, Scheme).

- `country_name`  
  Country identifier used in modeling. In the public dataset, this field may be label-encoded or otherwise anonymized (see “Anonymization” below).

- `wp_revenue_model`  
  Categorical descriptor of the revenue model (as recorded in source data; e.g., tariff model / payment structure).

- `volume_method`  
  Method used to estimate or measure volume (e.g., metered, estimated, etc., as recorded).

- `quarters_used`  
  Number of quarters within the year used/available for aggregation (data completeness indicator).

---

### B) Location and scale variables
- `lat`, `lon`  
  Geographic coordinates. In the public dataset these are anonymized placeholders (e.g., set to 0.0) for privacy/contractual reasons.

- `num_taps`  
  Number of taps associated with the service (where applicable).

- `num_hh`  
  Number of households served/associated (where available).

- `wp_pop_last`  
  Population served estimate used in analysis (latest available for the observation).

- `num_kiosks`  
  Number of kiosks (where applicable).

- `num_scheme_tanks`  
  Number of scheme tanks (where applicable).

---

### C) Revenue and volume outcomes (primary outcomes)
- `wp_revenue_USD`  
  Annual revenue collected by the service (USD). Primary outcome used in descriptive analysis and modeling.

- `wp_m3`  
  Annual volume (m³). Used for volumetric normalization and derived metrics (e.g., revenue per m³).

---

### D) Rainfall covariates (previous-year monthly rainfall)
- `month_1` … `month_12`  
  Monthly rainfall covariates (mm). These represent rainfall from the previous year relative to the observation year (e.g., for an observation in 2024, months correspond to 2023), as described in the manuscript.

---

### E) Local service density (nearby waterpoints counts)
- `wp_count_within_500m`
- `wp_count_within_1000m`
- `wp_count_within_2000m`
- `wp_count_within_10000m`
- `wp_count_within_20000m`  
  Counts of other waterpoints within the specified radius.

---

### F) Nearby service coverage (population served by other waterpoints)
- `pop_served_last_within_500m`
- `pop_served_last_within_1000m`
- `pop_served_last_within_2000m`
- `pop_served_last_within_5000m`
- `pop_served_last_within_10000m`
- `pop_served_last_within_20000m`  
  Sum of populations served by other waterpoints within the specified radius (derived from the server dataset).

---

### G) Background population context (population within radius buffers)
- `Population_Within_500m`
- `Population_Within_1000m`
- `Population_Within_2000m`
- `Population_Within_5000m`
- `Population_Within_10000m`
- `Population_Within_20000m`  
  Population estimates within the specified radius buffers (derived from gridded population data, as described in the manuscript).

---

## Anonymization and Public-Release Notes
To protect sensitive infrastructure locations and comply with contractual constraints:
- `lat` and `lon` are anonymized placeholders in the public dataset (e.g., set to 0.0).
- `country_name` may be label-encoded in the public dataset.

As a result, while the released data and code reproduce the full analytical workflow and model structure, exact numerical replication of location-dependent results may differ slightly from those reported in the manuscript.

---

## Intended Use
This dataset is intended to support:
- Reproduction of descriptive figures and tables
- Replication of the modeling workflow (two-stage model, LOCO calibration, drift analysis, learning curves)
- Transparency of analytical methods used in the paper

It is not intended to replace raw contractual or operational datasets.
