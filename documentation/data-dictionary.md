# Data Dictionary

The supplied `lego_sets_data_dictionary.csv` describes the original 14 source fields.

| Field | Description |
|---|---|
| `set_id` | Official LEGO item number |
| `name` | Name of the LEGO set |
| `year` | Release year |
| `theme` | LEGO theme the set belongs to |
| `subtheme` | Subtheme within the theme |
| `themeGroup` | Overall group of the theme |
| `category` | Type of set |
| `pieces` | Number of pieces in the set |
| `minifigs` | Number of minifigures included in the set |
| `agerange_min` | Minimum recommended age |
| `US_retailPrice` | US retail price at launch |
| `bricksetURL` | URL for the set on Brickset |
| `thumbnailURL` | Small image of the set |
| `imageURL` | Full-size image of the set |

The Power BI report adds derived fields for product grouping, age bands and price bands. Those derived fields are documented separately in the [data model documentation](data-model.md).
