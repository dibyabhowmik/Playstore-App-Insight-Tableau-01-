Project Overview:
App Insights Unlocked: A Data Analytics Challenge is a Tableau analysis of the Google Play Store dataset. The project explores app ratings, categories, installs, reviews, app size, content ratings, genres, pricing, and update activity to understand what characteristics are associated with app popularity and user engagement.

The analysis covers 10,841 app records across 34 categories and uses multiple levels of analysis, from basic descriptive questions to deeper comparisons and relationship analysis.

Objectives:
Analyze the overall distribution of app ratings.
Identify the most common app categories and content ratings.
Identify the most installed and highly reviewed apps.
Compare free and paid applications.
Analyze app size and its relationship with installs.
Examine ratings across content ratings and genres.
Analyze app update patterns over time.
Explore relationships between ratings, installs, reviews, and app characteristics.
Identify highly rated and highly popular applications.
Tools & Techniques Used
Tableau Public
Google Play Store dataset
Data cleaning and standardization
Calculated fields
String manipulation
Data type conversion
Filters and sorting
Histograms
Bar charts
Scatter plots
Trendlines
Heatmap-style comparisons
Binned analysis
Top-N analysis
Aggregation using AVG, COUNT, MAX, etc.

Data Preparation & Process:
The raw dataset contained fields such as App, Category, Rating, Reviews, Size, Installs, Type, Price, Content Rating, Genres, and Last Updated.
Several calculated fields were created to make the data suitable for analysis.

Installs Numeric:

INT(REPLACE(REPLACE([Installs], ",", ""), "+", ""))

Size Numeric MB

IF CONTAINS([Size], "M") THEN
    FLOAT(REPLACE([Size], "M", ""))
ELSEIF CONTAINS([Size], "k") THEN
    FLOAT(REPLACE([Size], "k", "")) / 1024
ELSE
    NULL
END

Category Clean:

UPPER(TRIM([Category]))

Genres Clean

TRIM([Genres])

Type Clean

TRIM([Type])

A numeric price field was also created to support paid-app analysis.

The analysis was then divided into Basic, Medium, and Advanced questions covering distributions, comparisons, relationships, and popularity analysis.

Key Insights:
The dataset contains 34 distinct app categories.
Everyone is the most common content-rating group.
Subway Surfers is among the most installed applications, with several Google applications also appearing among the highest-install apps.
Free applications overwhelmingly dominate the Google Play Store dataset compared with paid applications.
568 apps have ratings of 4.0 or above in the completed analysis.
GAME applications have the highest average size among the major categories analyzed.
A large number of applications were updated in 2018, making it a particularly active year in the dataset.
The analysis of Size vs Installs shows a slight positive relationship, but app size alone does not strongly explain installation volume.
Rating and install volume do not show a strong direct relationship, indicating that popularity is influenced by factors beyond rating.
The analysis of genres, content ratings, installs, reviews, and app type helps distinguish between user satisfaction and market popularity.
