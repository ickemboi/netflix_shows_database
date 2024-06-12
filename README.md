# netflix_shows_database

## Dataset
I chose the Netflix Shows dataset for this analysis. It contains information about various TV shows available on Netflix, including their title, director, cast, country, date added, release year, rating, and duration.

## Importing Dataset into MySQL Workbench
### Difficulties Encountered
- **Data Types**: Ensuring the correct data types for each column was crucial. For instance, date fields needed to be properly formatted as `DATE`.
- **Data Cleaning**: Some entries required cleaning due to inconsistencies in the text fields, such as different formats for dates and missing values.

### Interesting Observation
One interesting thing I noticed about the dataset is the diversity of countries represented in the Netflix shows. This highlights Netflix's global reach and its efforts to cater to a wide audience with varied content. Additionally, the dataset shows trends in release years and the types of shows added over time.

## How to Import the Dataset into MySQL Workbench
1. Open MySQL Workbench.
2. Create a new schema for the project.
3. Go to `Server -> Data Import`.
4. Choose `Import from Self-Contained File`.
5. Select the downloaded dataset file (e.g., `netflix_shows.csv`).
6. Set your newly created schema as the "Default Target Schema".
7. Click on `Start Import`.

## Repository Contents
- `README.md`: This file.
- Additional scripts or SQL files (if any) used for the analysis.

## Conclusion
This repository contains the initial setup and observations for analyzing the Netflix Shows dataset. Further analysis can be conducted to explore various trends and insights within the dataset.

