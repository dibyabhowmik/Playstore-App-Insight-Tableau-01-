# App Insights Unlocked: A Data Analytics Challenge

## Project Overview

**App Insights Unlocked: A Data Analytics Challenge** is a Tableau analysis of the Google Play Store dataset. The project explores app ratings, categories, installs, reviews, app size, content ratings, genres, pricing, and update activity to understand what characteristics are associated with app popularity and user engagement.

The analysis covers **10,841 app records across 34 categories** and uses multiple levels of analysis, from basic descriptive questions to deeper comparisons and relationship analysis.

## Objectives

1. Analyze the overall distribution of app ratings.
2. Identify the most common app categories and content ratings.
3. Identify the most installed and highly reviewed apps.
4. Compare free and paid applications.
5. Analyze app size and its relationship with installs.
6. Examine ratings across content ratings and genres.
7. Analyze app update patterns over time.
8. Explore relationships between ratings, installs, reviews, and app characteristics.
9. Identify highly rated and highly popular applications.

## Tools & Techniques Used

- Tableau Public
- Google Play Store dataset
- Data cleaning and standardization
- Calculated fields
- String manipulation
- Data type conversion
- Filters and sorting
- Histograms
- Bar charts
- Scatter plots
- Trendlines
- Heatmap-style comparisons
- Binned analysis
- Top-N analysis
- Aggregation using AVG, COUNT, MAX, etc.

## Data Preparation & Process

The raw dataset contained fields such as App, Category, Rating, Reviews, Size, Installs, Type, Price, Content Rating, Genres, and Last Updated.

Several calculated fields were created to make the data suitable for analysis.

### Calculated Fields

**1. Installs Numeric**

```tableau
INT(REPLACE(REPLACE([Installs], ",", ""), "+", ""))
```

**2. Size Numeric MB**

```tableau
IF CONTAINS([Size], "M") THEN
    FLOAT(REPLACE([Size], "M", ""))
ELSEIF CONTAINS([Size], "k") THEN
    FLOAT(REPLACE([Size], "k", "")) / 1024
ELSE
    NULL
END
```

**3. Category Clean**

```tableau
UPPER(TRIM([Category]))
```

**4. Genres Clean**

```tableau
TRIM([Genres])
```

**5. Type Clean**

```tableau
TRIM([Type])
```

A numeric price field was also created to support paid-app analysis.

The analysis was then divided into **Basic, Medium, and Advanced** questions covering distributions, comparisons, relationships, and popularity analysis.

## Key Insights

