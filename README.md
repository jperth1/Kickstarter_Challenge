# Kickstarter Challenge

## Overview of project
Analysis of Kickstarter data to evaluate the outcomes of theater and play crowdfunding campaigns by examining their launch dates and fundraising goals.

### Purpose
This analysis aims to advise Louise on her Kickstarter campaign for her play *Fever*.

### Analysis and Challenges 
The data for this analysis is derived from the Kickstarter website. A pivot table is created from this data to evaluate the outcomes--successful, failed, and canceled--of theater campaigns based on the launch date. The fields "Parent category" and "Year" is used to filter data to show outcomes for only theater campaigns by the month it was launched. Accompanying the pivot table is the line chart *Theater Outcomes by Launch Date* to visually represent the relationship between outcomes for theater campaigns and their launch dates. 
 
A table is created based on the Kickstarter data to survey the outcomes of play campaigns based on their fundraising goals. Fundraising goals are grouped into 12 ranges so projects can be grouped based on their goal amount. The countifs() function is used to provide the number of successful, failed, and canceled plays for each fundraising goal range. The total projects is found using the sum() function, and the percentage of successful, failed, and canceled plays is found by dividing the number of each outcome category by the total number of projects for each goal range. The line chart *Outcomes based on Goals* is supplemented to visually represent the relationship between the percentage of successful, failed, and canceled play campaigns and their fundraising goals. 

Challenges were encountered when calculating the number of successful, failed, and canceled plays based on their fundraising goal range. Manually entering the goal range withing the countifs() function for each of the 12 ranges became tedious and lead to mistakes as the function includes multiple criteria making it hard to debug. Mistakes were also made when countif() was accidentally selected instead of countifs(). 

### Analysis of Outcomes based on Launch Date
The pivot table created to evaluate theater outcomes based on launch date filters the Kickstarter date using the fields "Parent category" and "Years". "Outcomes" is the input for the columns of the pivot table, "Date Created Conversion" is input for the rows of the pivot table, and "Count of Outcomes" is input for the value. The resulting pivot table shows the number of theater campaigns that were either successful, failed, or canceled for each month of the year. Campaign outcomes were sorted in descending order so "successful" is displayed first. The line chart "Theater Outcomes Based on Launch Date" visualizes the relationship between theater outcomes and launch dates.

![Theater Outcomes by Launch Date Table](/Resources/Theater_Outcomes_vs_Launch_Pivot.png)

![Theater_Outcomes_vs_Launch](/Resources/Theater_Outcomes_vs_Launch.png) 


### Analysis of Outcomes Based on Goals

The table created to survey play outcomes based on fundraising goals breaks down the Kickstarter data into eight columns--Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled. The “Goal” column groups projects into 12 dollar-amount ranges with the minimum range of “less than $1,000” and the maximum range of “greater than $50,000”. The countifs() function is used to determine the "Number Successful," "Number Failed," and "Number Canceled" columns using the Kickstarter "outcome" column, "goal" column, and “plays” from the "subcategory" column as criteria for the function. The sum() function is used to find the "Total Projects" for each row of successful, failed, and canceled projects. The percentage of successful, failed, and canceled projects for each row is calculated by dividing the number of successful projects by the total number of projects for that goal range, the number of failed projects by the total number of projects for that goal range, and the number of canceled projects by the number of total projects for that goal range. The line chart "Outcomes Based on Goals" provides the visual relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, or canceled plays on the y-axis.

![Outcomes based on Goals Chart](/Resources/Outcomes_vs_Goals_Chart.png)

![Outcomes_vs_Goals](/Resources/Outcomes_vs_Goals.png)

### Challenges
Challenges and difficulties were encountered while utilizing the countifs() function to populate the table for outcomes based on goals. Manually entering the goal range within the countifs() function for each of the 12 ranges became tedious and lead to mistakes as the function includes multiple criteria making it hard to reread and debug. For example, the following line of code shows the multiple criteria needed to calculate the number of failed plays with fundraising goals between $10,000 and $14,999:![image](https://user-images.githubusercontent.com/80020390/111395194-a9f9ce00-8692-11eb-9764-eaa0dc460edd.png)

=COUNTIFS('Kickstarter Data'!D:D,">=10000",'Kickstarter Data'!D:D,"<=14999",'Kickstarter Data'!F:F,"failed",'Kickstarter Data'!R:R,"plays")

Overall, it became challenging to debug a line of code like this due to the various criteria needed for this one function. Additionally, challenges were encountered when countif() was mistaken for countifs() and an error message was displayed citing "too many arguments were entered for this function". Ultimately, both of these challenges were overcome by diligently reevaluating formulas and double checking the correct use of expressions, criteria, and ranges. 

## Results

### Theater Outcomes Based on Launch Date
 The data analysis for theater outcomes based on launch date indicated that theater campaigns that launched during the month of May see the most success. 111 out of 166 campaigns, or 67% (111/166) saw success during the month of May while 55, or 33% (55/166), of those campaigns either failed or were canceled. Moreover, theater campaigns during the month of December are the least likely to succeed where only 37 out of 75 campaigns--49% (37/75) --were successful, and 38 out of 75 campaigns, or 51% (38/75), either failed or were canceled. 
 
### Play Outcomes based on Goals
The data analysis for play outcomes based on fundraising goals indicated that play campaigns with the fundraising goal less than $1,000 were most likely to succeed. 141 campaigns out of 186, or 76% (141/186), were successful in meeting their fundraising goals while only 24% (45/186) of campaigns failed to meet their fundraising goal. 

### Limitation
Limitation for this data set is seen primarily in its source. Data is only derived from Kickstarter and does not include the various other crowdfunding platforms used to support startups, artists, non-profits, etc. Including data from a wider variety of crowdfunding sources such as Indiegogo, GoFundMe, and Patreon would help curb potential biases that skew the data. Moreover, the data set used in limited in scope in that it only provides data up 2017. A more accurate and precises analysis could be found if the data set included data from more recent years.

### Additional Tables and Graphs
To supplement this analysis an additional table evaluating the relationships among the outcomes of theater campaigns, their fundraising goal, and the average donor amount could be provided. Examining these relationships would help Louise develop a minimum donation amount to ask for when her campaign launches. A bar chart representing this table can also be provided to help the client visualize these relationships and plan how much to request from donors. 
