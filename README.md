# Home Buyers and How to Find Them

## Table of contents

* [Objectives](#Objectives)
* [Methodology](#Methodology)
* [Findings Summary](#Findings-Summary)
* [Targeting by Zip Code](#Targeting-by-Zip-Code)
* [Tech](#Tech)

## Objectives
This study attempts to identify demographic traits of US home buyers. What factors make a head of household more likely to rent vs own? Once we identify these traits, where can we find these potential home buyers?

## Methodology
I used the most recent [American Community Survey 5 Year Data](https://www.census.gov/data/developers/data-sets/acs-5year.html) from the US Census to collect demographic data on home owners and renters. This data set, released January 2020, uses data collected from 5 years of Census surveys (2014-2018) to estimate "social, economic, demographic, and housing characteristics of the U.S. population."

Rent vs Ownership was examined for the following factors: age, children, education, income, household size, marital status and move-in date. Once the important features were indentified, I filterd for zip codes which had the demographic traits associtated with home buyer candidates.  

Data was called via api, cleaned and transformed with pandas and charted with matplotlib.

## Findings Summary

In summary, the following traits show positive correlation with home ownership: age, marital status, education-level, income and move-in date.

Once a household becomes larger than one person, household size had little correlation with levels of ownership. In this data set, having children did not have an impact on home ownership. However, the census data as it's presented does not control for the age of the parents (i.e. households with young children might have low rates of home ownership becuase the partents are young). More granular data is needed to determine the impact of children on home ownership. 

### Age

There is a clear correlation between age and home ownership rates up to 75 years of age. 

![age](/images/Age.png)

### Marital Status

When controlling for age, married couples have much higher rates of home ownership compared to singles.'

![34married](/images/Marital_Status_15-34.png)

![64married](/images/Marital_Status_35-64.png)litt

### Education Level

Households with a High School Degree or higher have higher rates of home ownership.

![education](/images/Education.png)

### Income

A strong positive correlation between annual income and home ownership. 

![income](/images/Income.png)

### Move-In Date

Across all age groups, households who have moved to new homes recently had lower rates of home ownerships vs their peers. 

![young_move](/images/Move_in_Date_15-34.png)

![mid_move](/images/Move_in_Date_35-64.png)

![senior_move](/images/Move_in_Date_65_+.png)

### Household Size

Beyond one-person households, household size showed little to no correlation with rates of ownership. 

[!size](/images/Household_Size.png)

### Children

Having children present in the house did not have a big impact on home ownership. In fact, households with children 6 years and under had relatively low ownership rates compared to non-child households. However, this could be due to the fact that parents of young children are also young, and as we saw above age correlates with home ownership rates. Unfortunately this census data does not break down children by parent age. 

[!child](/images/Children.png)

## Targeting by Zip Code

With the above findings in hand, we can search for areas that have populuations of likely homebuyers. The Census data allows us to zoom in as close as the Zip Code Level

### New Home Owner Filter

This filter looks for zip codes that have a high percentage of young renters (ages 25-44). As seen above, these are the age groups that see the biggest jumps from renting to ownership. I narrowed these results by filtering for zip codes with in the top quartile of both  education (HS diploma or above) and income. This list can be used to find households looking to buy their first home. 

The resulting 902 zip codes are in [this csv file](/data/owner_final.csv)



### New Mover Filter

The move-in date analysis showed that households who have recently moved to are more likely to be renters than owners. This filter identifies zip codes that have seen a relatively high number of households moving in. It then filters for zip codes in the top quartile of both education and income. This list can be used to find potential home buyers as they settle in to their new surroundings of as they move from temporary to permanent housing. 

The resulting 651 zip codes are in [this csv file](/data/mover_final.csv)

## Tech
* Python - version 3.7.3

### Python Dependencies
* Pandas - version0.25.3
* Matplotlib - version 3.1.1
* Requests - version 2.23.0
