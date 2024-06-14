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
1. Prepare the Database and Table:

2. Create the database and table if they do not exist using the following SQL script in MySQL Workbench:
CREATE DATABASE IF NOT EXISTS netflix_db;
USE netflix_db;

CREATE TABLE IF NOT EXISTS netflix_shows (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255),
    director VARCHAR(255),
    cast TEXT,
    country VARCHAR(100),
    date_added DATE,
    release_year INT,
    rating VARCHAR(10),
    duration VARCHAR(50),
    listed_in TEXT,
    description TEXT
);
3. Open MySQL Workbench:

Connect to your MySQL database.
Open Table Data Import Wizard:

Right-click on the netflix_db database.
Select Table Data Import Wizard.
4. Select the CSV File:

Click Browse to select your CSV file (netflix_shows.csv).
Click Next.
5. Configure Import Settings:

Ensure the correct table (netflix_shows) is selected.
Set Field Separator to ,.
Set Line Endings to \n.
Check First Row Contains Column Names.
Click Next.
6. Map Columns:

Ensure CSV columns are correctly mapped to table columns.
Click Next.
7. Import Data:

Review settings and click Next to start the import.
Wait for the import to complete.
## Repository Contents
- `README.md`: This file.
- Additional scripts 

## Conclusion
This repository contains the initial setup and observations for analyzing the Netflix Shows dataset. Further analysis can be conducted to explore various trends and insights within the dataset.

## Data Fun

### Cool Facts

#### Most Common Show Ratings
`
SELECT rating, COUNT(*) AS count
FROM netflix_titles
GROUP BY rating
ORDER BY count DESC
LIMIT 600;`

Explanation: This query counts the number of shows for each rating and orders them in descending order to find the most common ratings.

Findings:
The most common ratings are "TV-MA," "TV-14," "TV-PG," and "PG-13.

#### Average duration of tv shows
`
SELECT AVG(duration) AS average_duration
FROM netflix_titles
WHERE duration LIKE '% min';`

Explanation: This query calculates the average duration of TV shows that are listed in minutes.

Findings:
The average duration of TV shows is approximately 100.727272 minutes .

## Ask Away
### Question 1: What are the popular shows in different countries?
`SELECT country, title, COUNT(*) AS show_count
FROM netflix_titles
GROUP BY country, title
ORDER BY show_count DESC, country ASC
LIMIT 10;`
Explanation: This query groups the shows by country and title, counts the number of shows per title in each country, and orders the results by the count in descending order.

Findings 

### Qusetion 2 Number of Shows Released After 2000
`
SELECT COUNT(*) AS shows_after_2000
FROM netflix_titles
WHERE release_year > 2000;`

Explanation: This query counts the number of shows that were released after the year 2000.

Findings:
The number of shows released after 2000 is 92,



