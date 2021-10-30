# Determining the Healthiest Counties in Texas


## Introduction
The COVID-19 pandemic introduced a lot of changes for most people across the globe. Some took it as an opportunity to improve their cleanliness and personal hygiene. Others capitalized on the opportunity to work remotely and explore living in different cities. This project investigates the health and the socioeconomic factors that contribute to each county’s overall health with a specific emphasis on Texas. 


## Questions
Before we take a deep dive into various datasets and run statistical analysis, let’s first define “health”. For this case study, health will primarily be defined by evaluating life expectancy. Life expectancy is a measure of the average number of years a person can expect to live from birth. 

Now let’s establish a baseline of a few core questions that we want to answer: 
1.	What are the top 5 healthiest counties in Texas?
2.	How do health factors correlate to overall life expectancy?
3.	What are the relationships between socioeconomic factors? 


## Data Sources
The bulk of data used for this project was retrieved from County Health Rankings & Roadmaps We also pulled data using the Google Maps API and COVID Act Now API. 

- https://www.countyhealthrankings.org/
- https://developers.google.com/maps/apis-by-platform
- https://apidocs.covidactnow.org/
- https://covidactnow.org/


## Data Exploration & Cleanup
In cleaning the data, we sifted through over 500 health and socioeconomic factors from our various datasets to determine which would have the greatest impact on determining the health of a county. We further filtered down our dataset and decided to focus 5 key factors for our analysis:

- Median household income across the county
-	Total number of primary care physicians in the county
-	Total number of unemployed people in the county
-	Total number of people in the county that graduated high school 
-	Total number of people who lack adequate access to food; also referred as food insecure

We created a health factor dataframe after we imported our initial csv file. Using the .count() function, we analyzed each column to view how many values each column contained to help us determine if we needed to remove any null values. After we removed the null values, we decided to further filter down our dataset and focus on Texas. Texas has 255 counties, 88 have a population below 10,000. We filtered out the counties below 10,000 to ensure that our analysis would produce consistent results and minimize outliers. 


# Analysis & Methodology
Our dataset contained mostly raw numbers such as the total number of primary care physicians in a county. We decided to convert most of these values into percentages by dividing them against the total population of the county. We determined that this would help us to quickly identify trends and effectively determine the correlation between health factors and how they impact life expectancy. One of the last stages in our analysis process was to compare the impact of these health factors and see what trends we could identify when comparing the top 5 counties with the highest life expectancy vs the bottom 5 with the lowest life expectancy. 


## Result of Analysis 
We created a box plot to demonstrate the average life expectancy measured in years in the southern US by state. Texas ranked in the top 5 when comparing life expectancy across the southern states. Presidio County (TX) had the highest life expectancy across all southern counties at 88.80 years. Though we did determine that it was an outlier primarily based on its low population of 6,704 residents in the county and only having 2 primary care physicians in the entire county. 

Virginia had 4 counties ranked in the top 10 for highest life expectancy; 3 were outliers:
-	Manassas Park City – 86.49 (outlier)
-	Arlington – 85.92 (outlier)
-	Fairfax – 85.63 (outlier)
-	Loudoun – 84.67

Texas had 3 counties ranked in the top 10 for highest life expectancy; all were outliers:
-	Presidio – 88.80 (outlier)
-	Hudspeth – 84.48 (outlier)
-	Jeff Davis – 84.23 (outlier)

Florida had 2 counties ranked in the top 10 for highest life expectancy, 1 was an outlier:
-	Collier – 86.11
-	Glades – 84.14 (outlier)

Maryland had 1 county ranked in the top 10 for highest life expectancy which was also an outlier:
-	Montgomery – 84.60 (outlier)


We created scatter plots with linear regression lines to analyze bivariate data so that we could determine the correlation between each health factor and life expectancy in Texas. Higher income was associated with greater longevity. Life expectancy increased as access to food increased. The percentage of primary care physicians in a county per 100,000 residents increased as life expectancy increased. The percentage of unemployed people and the percentage of residents in a county with a high school diploma had minimal effects on a county’s life expectancy. 

W used a bar graph to compare the result between top 5 counties and bottom 5 counties in Texas by health factor to further illustrate some of the correlations that we previously analyzed.


## Conclusion
We expected to find a direct correlation between health and socioeconomic factors and their impact on a county’s life expectancy. The factors that we analyzed displayed both positive and negative correlations to life expectancy. Average household income, food insecurity and percentage of primary care physicians had the greatest impact on life expectancy. 

We determined that the top 5 healthiest counties in Texas with a population of 10,000+ residents are:
-	Fort Bend – 83.01 years
-	Collin – 82.67 years
-	Williamson – 82.10 years
-	Denton – 82.01 years
-	Travis – 80.69 years
