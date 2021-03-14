# Kickstarter_Challenge
## Overview of project
Analysis of kickstarter data to evaluate the outcomes of theater and play crowdfunding campaigns by examining their launch date and fundraising goals.
## Purpose
This analysis aims to advise Louise on her kickstarter campaign for her play *Fever*
### Analysis
The data for this analysis is derived from the kickstarter website. The pivot table *Theater Outcomes by Launch date* is created from this data to evaluate the outcomes--successful,failed, and canceled--of theather campaigns based on the launch date. The fields "Parent category" and "year" is used to to filter data to show outcomes for only theater campaigns by the month it was launched.
![Theater Outcomes by Launch Date Table](/Resources/Theater_Outcomes_vs_Launch_Pivot.png)

Accompanying the pivot table is the line chart *Theater Outcomes by Launch Date* to provide visual representation of outcomes for theater campaigns based on their launch date. 
![Theater Outcomes by Launch Date Line Chart](/Resources/Theater_Outcomes_vs_Launch.png) 

The chart *Outcomes based on Goals* surveys the outcomes of play campaigns based on their fundraising goals.

![Outcomes based on Goals](/Resources/Outcomes_vs_Goals_Chart.png)
Fundraising goals are grouped into 12 ranges with the minimun range of less than $1,000 and the maximum range of greater than $50,000. The countifs() function is used to provide the number of successful, failed, and canceled plays for each fundraising goal range. the total projects is found using the sum() function, and the percentage of successful, failed, and canceled plays is found by dividing the the number of each outcome category by the total number of projects for that goal range. The chart *Outcomes based on Goals* is supplemented with the line chart *Outcomes based on Goals* to visually represent the precentage of successful, failed, and canceled plays based on their funraising goals. 
![Alt_image title](/Resources/Outcomes_vs_Goals.png) 

### Challenges
Challenges were encountered when calculating the number of successful, failed, and canceled plays based on their fundraising goal range. Manually entering the goal range withing the countifs() function for each of the 12 ranges became tedious and lead to mistakes as the function included multiple criteria, making it hard to read and debug. Additional mistake were made when countif() was accidentilly selected instead of countifs(). Both challeneges were overcome by reevaluting formula and doubling checking the correct use of expressions and number within the formula. 

### Analysis of Outcomes based on Launched Date
