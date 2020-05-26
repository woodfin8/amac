# Home Buyers and How to Find Them

## Table of contents

* [Objectives](#Objectives)
* [Methodology](#Methodology)
* [Findings Summary](#Findings-Summary)
* [Targeting by Zip Code](#Targeting-by-Zip-Code)
* [Charts and Tables](#Charts-and-Tables)
* [Tech](#Tech)

## Objectives
This study attempts to identify demographic traits of US home buyers. What factors make a head of household more likely to rent vs own? Once we identify these traits, where can we find potential these home buyers?

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

