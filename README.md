# Project1_Group4
VU Data Analytics Bootcamp 2023

# Questions
We approached this project from the aspect of a private insurance compnay looking to expand clientele. We have been tasked with identifying demographics that will be the best for a marketing campaign to increase business. Answering the following questions will help identify those demographics. 

What factors determine insurance coverage for Americans? Does race, sex, location, age or poverty level indicate the probability of an individual having insurance coverage? 

# Data
Data was retreived from the U.S. Census Bureau Small Area Health Insurance Estimates. This models health insurance coverage by combining survey data with administrative records and other Census data sources.(source: https://www.census.gov/data/developers/data-sets/Health-Insurance-Statistics.html ). An API was used to retrieve the data, pulling the categories that are being analyzed for the year 2020.

# Data Analysis
The basis of all analyses will be the percentage of insured Americans. This is a column added to the dataframe with a calculation using the "Number of Insured" and "Number of Uninsured" from the API. The results of the API contain summary amounts and individual group amounts for each category. To eliminate duplication of the populations in the analysis, new dataframes are created for each category that breaks out each group in the category while using the summary data of all other categories. Being that the percentage of insured Americans is the most important variable, it is determined that box plots are the best graphing option to visualize this data. The box plots will show how each group compares to the summary group and where there are outliers. And to visualize the insured by state, a bar graph is used to show how insurance coverage varies by location.

Using each dataframe created for the categories, ANOVA tests were performed based on that category to identify any demographics that have signficant differences. The most significant differences based on P-Values were noted in Race (P=3.34e-29) and Age range(5.39e-18), leading us to take a further look at these areas.

First, looking at the by race box plot, the Hispanic race appeared most different from all other races. We individually compared Hispanic group to all groups, and found a statistically significant decrease in percent insured among the Hispanic group (P=5.40e-15 by Student's t-test). 

Next, looking at the by age box plot, the under 19 age group stood out the most. This group has the highest median of insured Americans. We also compared this group to all ages and found a significant increase in percent insured (P= 7.37e-12 by Student's t-test).

Lastly, a look at the bar graph for coverage based on state shows some areas with visible lower amounts that most states. To determine a significant differnce by state, a chi-squared test was performed. With there being 50 data points for the states, there is a large degree of freedom. Therefore, the chi-square test does not show a significant difference. To further visualize the locations, we plotted the insurance coverages on the map using color variations applied to the insured percentage. Being that the darkest color plots have the highest percentage of insurance coverage, we can see that the darkest colors are primarily in the Northeast region of the country.

# Conclusion
Based on the statistical analyses, the best factors for determining insurance coverage are Race, Age Range and location. For a private insurance company that may be looking to provide coverage to the uninsured, the Hispanic race would be the ideal demographic as this is the group with the lowest insurance coverage. This company would also benefit from appealing to individuals that live in the Southwest region of the country, specifically Texas. Americans that fall in the Under 19 age range, are above 138% of the poverty line, or live in the Northeast region have the highest probability of being insured. For these 2 demographics, a private insurance company would want to target these demographics by advertising better premiums and/or coverage packages to gain more business. The individuals in the under 19 age range are also more likely to be a dependent on a family members plan, so advertising better dependent plan coverage would also be a great marketing aspect to cover.

# Member Contributions:
Kennatha Williams - Data retrieval, data cleaning, created bar graph, Powerpoint preparation, and ReadMe preparation

Kirill Zavalin - performed statistical calculations, created summary table of statistical results, formatted and graphed box plots for individual comparisons, data analysis

Alexe Zechman - Created summary dataframes, created all Box plots, created map of state coverage, defined labels for state bar graph
