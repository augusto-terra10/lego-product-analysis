# Data Model

## Tables identified in the Power BI report

### `lego_sets`

The main product-level table used by the report. It contains the source product attributes and derived analytical fields.

Fields used in report visuals include `set_id`, `name`, `year`, `theme`, `subtheme`, `pieces`, `price`, `imageURL`, `Portfolio Product Group`, `Age Range` and `Price Range`.

### `Measure Table`

A dedicated table used to organise DAX measures referenced by report visuals.

Measures observed in the report include:
- `Total Products`
- `Avg Pieces per Product`
- `Avg Recorded Price (USD)`
- `Priced Products`
- `Sum Prices`
- `Selected Product`
- `Selected Pieces`
- `Selected Price`
- `Selected Year`
- `Selected Ages`

Please refer to the dashboard file to explore all measures used in the analysis.

## Derived classifications

The report uses additional fields to make the source catalogue easier to analyse:

- `Portfolio Product Group` – consolidated product grouping used in the decomposition tree and slicers.
- `Age Range` – age bands used for filtering.
- `Price Range` – price bands used for the product price distribution.
- `price` – price field used by report visuals.

The decomposition tree uses this analysis path:

`Total Products → Portfolio Product Group → Theme → Subtheme → Name`

## Relationship documentation

There is only a single source table in this project. The primary objective was to focus on creating meaningful measures, calculations, and visualisations to support the analysis.
