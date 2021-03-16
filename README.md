# Kickstarter_Challenge
## Overview of project
Analysis of kickstarter data to evaluate the outcomes of theater and play crowdfunding campaigns by examining their launch date and fundraising goals.
### Purpose
This analysis aims to advise Louise on her kickstarter campaign for her play *Fever*.

### Analysis
The data for this analysis is derived from the kickstarter website. A pivot table is created from this data to evaluate the outcomes--successful,failed, and canceled--of theather campaigns based on the launch date. The fields "Parent category" and "year" is used to to filter data to show outcomes for only theater campaigns by the month it was launched. Accompanying the pivot table is the line chart *Theater Outcomes by Launch Date* to provide visual representation of outcomes for theater campaigns based on the launch date. 

A chart is created based on the kickstarter data to survey the outcomes of play campaigns based on their fundraising goals. Fundraising goals are grouped into 12 ranges with the minimun range of less than $1,000 and the maximum range of greater than $50,000. The countifs() function is used to provide the number of successful, failed, and canceled plays for each fundraising goal range. the total projects is found using the sum() function, and the percentage of successful, failed, and canceled plays is found by dividing the the number of each outcome category by the total number of projects for that goal range. The line chart *Outcomes based on Goals* is supplemented to visually represent the relationship between precentage of successful, failed, and canceled play campaigns and their funraising goals. 

### Challenges
Challenges were encountered when calculating the number of successful, failed, and canceled plays based on their fundraising goal range. Manually entering the goal range withing the countifs() function for each of the 12 ranges became tedious and lead to mistakes as the function includes multiple criteria making it hard to read and debug. Mistakes were also made when countif() was accidentilly selected instead of countifs(). 

### Analysis of Outcomes based on Launch Date
The pivot tabel created to evaluate theater outcomes based on launch date filters the kickstarter date using the fields "Parent category" and "years". "Outcomes" is the input for columns and "Date Created Coversion" is input for the rows. "Count of outcomes" is input for the values. The resulting pivot table shows the number of theater campaigns that were either successful, failed, or canceled for each month of the year. Campaign outcomes were sorted in descending order so "successful" is displayed first. The line chart titled "Theater Outcomes Based on Launch Date" visualizes the relationship between outcomes and launch month.

![Theater Outcomes by Launch Date Table](/Resources/Theater_Outcomes_vs_Launch_Pivot.png)

![Theater_Outcomes_vs_Launch](/Resources/Theater_Outcomes_vs_Launch.png) 


### Analysis of Outcomes Based on Goals

The tabel created to survey play outcomes based on fundraising goals breaks down the kickstarter data into eight columns--Goal, Number Successful, Number Failed, Number Canceled, Total projects, Percentage Successful, Percentage Failed, and Percentage Canceled. The Goal column is divided into 12 dollar-amount ranges so projects can be grouped based on their goal amount. The Countifs() function is used to determine the "Number Successful," "Number Failed," and "Number Canceled" columns using hte Kickstarter "outcome" column, the "goal" amount column using the ranges created, and the "Subcategory" column using "plays" as the criteria. The Sum() function is used to find the "Total Projects" for row of successful, failed, and canceled projects. The percentage of successful, failed, and canceled projects for each row was calculated by dividing the number of successful projects by the total number of projects, the number of failed projects by the total number of projects, and the number of cancled projects by the number of total projects. The line chart "Outcomes Based on Goal" provides the visual relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, or canceled projects on the y-axis.

![Outcomes based on Goals Chart](/Resources/Outcomes_vs_Goals_Chart.png)

![Outcomes_vs_Goals](/Resources/Outcomes_vs_Goals.png)

### Challenges
Challenges and difficulties were encountered while utilizing the Countifs() function to populate the chart "Outcomes Based on Goals". Manually entering the goal range withing the countifs() function for each of the 12 ranges became tedious and lead to mistakes as the function includes multiple criteria making it hard to read and debug. For example,the following line of code shows the multiple criteria and ranges that need to be utilize to calulate the number of failed plays that had the a fundraising goal between $10,000 and $14,999:

=COUNTIFS('Kickstarter Data'!D:D,">=10000",'Kickstarter Data'!D:D,"<=14999",'Kickstarter Data'!F:F,"failed",'Kickstarter Data'!R:R,"plays")

Overall, it became challenging to debug a line of code like this due the various criteria needed for this one function. Additionally, challeneges were encountered when Countif() was mistaken for Countifs() and an error message was displayed citing "too many agruments were entered for this function". Ultimately, both of these challenges were overcome overcome by diligently reevalutings formula and double checking the correct use of expressions, criteria, and ranges within the each formula. 

## Results

### Theater Outcomes Based on Launch Date
The data analysis for theater outcomes based on launch date indicated that theater campaigns that launched during the month of May see the most success. 111  out of 166 campaigns , or 67% (111/166) saw success during the month of May while 55, or 33% (55/166), of those campaigns either failed or were canceled. Moreover, theater campaigns during the month of Decemeber are the least likely to successed where only 37 out of 75 campaigns--49% (37/75)--were successful, and 38 out of 75 campaigns, or 51% (38/75), either failed or were canceled. 

### Play Outcomes based on Goals
The data analysis for play outcomes based on fundaising goals indicated that play campaigns with the fundrasing goal less than $1,000 were most likely to succeed, where 141 campaigns out of 186, or 76% (141/186), were sucessful in meeting their fundraisning goals while only 24% (45/186) of campaigns failed to meet their fundraising goal. 

### Limitation
Limitation for this data set is seen primarly in it's source. Data is only derived from Kickstarter and does not include the various other crowdfunding platforms used to support startsups, artists, and non-profits. Including data from a wider variety of crowdfunding sources such as Indiegogo, GoFundMe, and Patreon would help curb biases in the data set. Moreover, the data set used in limited in its scope in that it only has data up 2017. A more accurate and percises analysis would be found if the data set included more recent data past 2017.

### Additional Tables and Graphs
To supplement this analysis an additional table evaluting the relationship amoung the outcomes of theater campaigns, the campaigns fundraising goal, and the average donor amount could be provided. Examining this relationship would help Louise develope a minimun donation amount to ask for when her campagin launches. A bar chart representing this table can also be provided to help the client visualize the data. 
