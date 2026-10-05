# Vaping France (English edition): municipal map and observatory

Two municipal predictive models on one interactive map.

**1. Vaping.** Daily vaping rate among 18-75 year-olds for every French municipality
(34,852 municipalities, 45 municipal districts, 16,086 IRIS neighbourhoods), with vaper
profiles and uncertainty ranges. Small-area estimation: national surveys (EROPP 2023,
Santé publique France Barometers 2021 and 2024) × INSEE census, multi-wave regional
calibration with partial pooling.

**2. Propensity for protest action.** A 0-100 index of the propensity to sign a petition
or take part in a demonstration, at the same scales. Weights derived from the Boulianne &
Earl meta-analysis (*Science Advances*, 2026, 181 studies), French anchoring on the TeO2
survey (INSEE-INED), and the observed left-wing vote (2022 presidential election).

## Pages

- **`index.html`**: four-level interactive map, France → department → municipality →
  IRIS neighbourhood (districts for Paris, Lyon and Marseille). High-definition boundaries
  (`geo/`) load on click. Colour the map by one indicator or cross two; the full profile of
  the selected territory, including its 2014-2024 trajectory, appears below the map.
- **`belgium.html`**: the same map for the 565 Belgian municipalities (Belgium → province →
  municipality → neighbourhood, 19,783 statistical sectors): estimated current vaping among
  adults, estimated smoking, projected vaper profiles, civic engagement and a five-type
  strategic typology. The "Country" switch at the top right moves between the two maps. The
  Belgian rate is current use among adults, the French rate is daily use among 18-75
  year-olds: compare relative positions, not levels.
- **`observatory.html`**: detailed profile for each French municipality, with rankings.
  Direct link to a municipality: `observatory.html#c=35238`.
- **`data/`**: the full estimates as CSV (`;` separator, UTF-8 with BOM, French column names).

The pages load detailed base maps with `fetch()`: serve them over HTTP.

## Reading the estimates

The rates are expected values given the socio-demographic make-up, calibrated on the
observed regional prevalence. Differences between regions and departments are validated
(surveys and market signals); fine differences between neighbouring municipalities are
risk profiles, to be read with their `taux_p05`-`taux_p95` range (median width ±0.6 point).

Sources: OFDT / Santé publique France (EROPP 2023, Barometers 2021 and 2024), INSEE (census
2022/2023, Filosofi), Sciensano and Statbel for Belgium. Public survey data; estimates
produced by modelling, September 2026. French edition:
https://jeangigounon.github.io/vapotage-france/
