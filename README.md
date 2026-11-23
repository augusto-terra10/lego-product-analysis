# LEGO Product Analysis

A Power BI portfolio project exploring the LEGO product catalogue through interactive product discovery, hierarchical exploration, historical release trends and pricing analysis.

> **Data notice:** This project uses a LEGO product dataset supplied for portfolio analysis. The report is an independent analytical exercise and is not affiliated with, endorsed by or sponsored by the LEGO Group. Product information and historical retail prices are presented as provided in the source dataset; missing values have not been treated as zero.

## Dashboard preview

The report contains three interactive pages:

1. **LEGO Set Finder** – search and filter products, inspect product attributes and view available product images.
2. **Product Explorer** – explore the catalogue through a decomposition tree, moving from product group to theme, subtheme and individual product.
3. **Collection Insights** – analyse product counts, release trends, price distribution, average recorded prices and the relationship between price and piece count.

Add exported screenshots to the `Screenshots/` folder and update these links:

- [LEGO Set Finder](screenshots/Lego%20Set%20Finder.png)
- [Product Explorer](screenshots/Product%20Explorer.png)
- [Collection Insights](screenshots/Collection%20Insights.png)

## Business objective

The report is designed to help users explore the LEGO product portfolio and answer questions such as:

- How is the product catalogue distributed across product groups and themes?
- Which themes and product groups contain the largest number of products?
- How has the number of recorded product releases changed over time?
- How are products distributed across retail price bands?
- Which themes have higher average recorded retail prices?
- How does retail price vary with the number of pieces?
- What are the details of an individual product, including its set ID, theme, release year, age range, piece count, price and available image?

## Dashboard contents

### 1. LEGO Set Finder

An interactive product discovery page with:
- Product search and a detailed product table.
- Filters for Portfolio Product Group, Theme, Age Range and Price Range.
- A numeric price filter.
- A selected-product panel showing available product details and an image.
- KPI cards for total products, average pieces per product and average recorded price.

### 2. Product Explorer

A decomposition tree that supports interactive exploration through:

`Total Products → Portfolio Product Group → Theme → Subtheme → Name`

Users can select a product group and progressively investigate the themes, subthemes and individual products contributing to the catalogue.

### 3. Collection Insights

A portfolio-level analytical page containing:
- Total product, average pieces and average recorded price KPIs.
- Product counts by theme.
- Average recorded product price by theme.
- Product price distribution.
- Product releases by year.
- LEGO set price versus number of pieces.
- Filters for product group, theme, subtheme, age range and release year.

## Data and model

The repository includes the source dataset and its data dictionary:

- `data/lego_sets.csv`
- `data/lego_sets_data_dictionary.csv`

The source dataset contains **18,457 records and 14 original fields**. It covers release years from **1970 to 2022** and includes **154 distinct themes**.

The original fields include:
- `set_id` – official LEGO item number.
- `name` – product name.
- `year` – release year.
- `theme` and `subtheme` – product theme classifications.
- `themeGroup` – broader theme grouping.
- `category` – source category.
- `pieces` and `minifigs` – product piece and minifigure counts.
- `agerange_min` – minimum recommended age.
- `US_retailPrice` – US retail price at launch.
- `bricksetURL`, `thumbnailURL` and `imageURL` – product reference and image links.

The Power BI report also uses derived fields for analysis, including:
- `Portfolio Product Group` – a consolidated product classification created for this project.
- `Age Range` – age bands used for filtering and analysis.
- `Price Range` – retail price bands used for distribution analysis.
- `price` – the price field used in the report.

The model uses a main `lego_sets` data table and a dedicated `Measure Table` for report measures. Measures referenced by report visuals include Total Products, Avg Pieces per Product, Avg Recorded Price (USD), Priced Products and selected-product detail measures.

See the [data model documentation](documentation/data-model.md), [data dictionary](documentation/data-dictionary.md) and [measures catalogue](documentation/measures-catalog.md).

## Data quality considerations

The source dataset contains missing values in several descriptive and numeric fields. In particular, the source CSV has missing values for subtheme, pieces, minifigs, minimum age, retail price and product image URLs.

These missing values are meaningful limitations of the source data. They should not be interpreted as zero, and price or piece-count analysis should be understood as applying to records where the relevant value is available.

The report includes classifications such as `Not specified` to make missing age or price information visible in the user experience. The source dataset is retained in the repository so that the analysis can be traced back to the supplied data.

## Tools and techniques

- Microsoft Power BI
- DAX measures
- Power Query data preparation
- Data classification and derived columns
- Interactive slicers and filtering
- Decomposition tree analysis
- Product catalogue exploration
- KPI design and data visualisation
- Scatter plot and distribution analysis
- CSV data handling

## Repository structure

```text
lego-product-portfolio-analysis/
├── README.md
├── report/
│   ├── LEGO_Product_Portfolio_Analysis.pbix
│   └── README.md
├── screenshots/
│   └── README.md
├── data/
│   ├── lego_sets.csv
│   ├── lego_sets_data_dictionary.csv
│   └── README.md
├── documentation/
│   ├── project-overview.md
│   ├── data-model.md
│   ├── data-dictionary.md
│   └── measures-catalog.md
└── .gitignore
```

## Author

**Augusto Terra**  
Business Intelligence & Data Analytics

- GitHub: [@augusto-terra10](https://github.com/augusto-terra10)
