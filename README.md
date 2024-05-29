# Sparks-Fund-Analysis
### **Overview**
This repository contains an analysis for Spark Funds, an asset management company, to help identify the best sectors, countries, and suitable investment types for their investment strategy. The analysis uses real investment data from Crunchbase and focuses on understanding global trends in investments.

### **Objective**
Spark Funds has specific investment constraints:
- Invest between 5 to 15 million USD per round of investment.
- Invest only in English-speaking countries to ease communication.

> The primary goal is to identify the best sectors, countries, and investment types where Spark Funds should focus their investments.

### **Business and Data Understanding**

**Strategy**
Spark Funds aims to invest where most other investors are investing, which is a common strategy among early-stage startup investors.

**Data Sources**
The data for this analysis has been sourced from Crunchbase and is divided into three main tables:

> Companies: Details about various companies.
> Rounds2: Information on funding rounds.
> Mapping: Mapping of numerous sub-sectors to eight main sectors.

**Business Objectives**

- Investment Type Analysis: Determine the most suitable type of investment (venture, seed, angel, private equity, etc.) for Spark Funds.
- Country Analysis: Identify the countries with the most investments to align with Spark Funds’ favorites.
- Sector Analysis: Understand the distribution of investments across the eight main sectors.

### **Data Preparation and Preprocessing**

**Preprocessing for Companies Data**

> Handle null values by dropping records with missing critical information (country_code and category_list).
> Fill remaining null values with the most frequent value to avoid errors during analysis.

**Preprocessing for Rounds Data**

> Handle null values by dropping records with missing raised_amount_usd.
> Rounds of investment are only done for Venture but in order to generalize our data and avoid errors, Fill null values in funding_round_code with 'A' to indicate the first round of investment,

**Preprocessing for Mapping Data**

> No null values handling required as this is a mapping dataset.

**Data Normalization and Merging**

> Normalize permalink fields to lowercase.
> Merge companies and rounds datasets on permalink.

**Filtering Data**

> Filter data to include only investments in English-speaking countries and between 5 to 15 million USD.

### **Analysis**
**Investment Type Analysis**
Analyze the average investment amounts for each type within the specified range.
Identify that venture type investments are the most common and recommend limiting to six rounds (A to F) to avoid low investment amounts in later rounds.
**Country Analysis**
Aggregate total investments by country.
Highlight the top countries (USA, GBR, IND) favored by investors.
**Sector Analysis**
Map sub-sectors to main sectors and analyze investment distribution across these sectors.

### **Visualization**
Use matplotlib and seaborn for visualizing the distribution of investments by type, country, and sector.

### **Conclusion**
Investment Type: Venture type is the most suitable for investments within the 5 to 15 million USD range.
Country: USA, Great Britain, and India are the top countries for investment.
Sector: Detailed sector analysis provided based on mapping data.

  1. Primary Investment: Focus on Cleantech / Semiconductors.
  2. Secondary Investment: Allocate 25% of investments to sectors like Social, Finance, Analytics, Advertising, News, Search, and Messaging.
  3. Tertiary Investment: The remaining 25% should be diversified across Manufacturing, Health, Entertainment, Automotive, and Sports sectors.

### **Repository Contents**
Sparks Fund Analysis.ipynb: Jupyter notebook containing the full analysis.
companies.csv: Dataset containing company details.
rounds2.csv: Dataset containing funding round details.
mapping.csv: Dataset for mapping sub-sectors to main sectors.
