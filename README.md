# Project 01: Seattle PD Funding Eligibility
> The analysis aims to gain insight about the logs of emergency 911 calls from the Seattle Police Department reported on March 26, 2016 - March 28, 2016. In addition, the study discusses whether the department will be eligible for additional funding if the minimum standard of 2.5 officers onsite per incident is met.

General Information
---
The project is part of a graduate course (_Fundamentals of Data Analytics_) at Western Governor's University. The data will not be provided, but rather an explanation of key findings and analysis of the project. The raw data set contains 1,046 observations and 20 features which is later reduced to 6 features. 

**To expand the project even further as a business use case, how can the police department increase the chances of their eligibility for funding if not eligible?**

Summary
---

Tech Stack
---
* Microsoft Excel
* Tableau

Data Preprocessing/Cleaning
---
* Irrelevant:
  * Removed ID and event number columns since the General Offense Number can be used as the unique identifier for each event.
  * Time stamp is not neccesary for the study.
* Redundant: 
  * Event Clearing Subgroup, Event Clearing Description, Initial Type Description/Subgroup/Group are already explained by Event Clearing Group.
* Missing Data:
  * Scene Time is not all populated and therefore, removed.
  * One observation is removed due to missing data in district/sector feature which is important in the analysis. 

Data Visualization
---
![Districts](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Districts.png?raw=true)
![AvgNumPerEvent](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Average%20Number%20of%20Officers%20Per%20Event.png?raw=true)
![AvgNumPerZone](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Average%20Number%20of%20Officers%20Per%20Zone.png?raw=true)
![NumofIncidentsbyDate](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Number%20of%20Incidents%20by%20Date.png?raw=true)
![NumofIncidentsbyDistrict](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Num%20of%20Incidents%20by%20District.png?raw=true)
![NumofIncidentsByEventType](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Num%20of%20Incidents%20by%20Event.png?raw=true)

Analysis
---
* The data is dated from March 26, 2016 to March 28, 2016 which happens to be a holiday weekend, Easter Sunday. By looking at the number of events per day, one will notice that there is a high level of activity on March 27, 2016, the day before Easter Sunday. This high volume of activity shows that there are many active people on the streets or at home, possibly preparing for family gatherings which can include non- resident family members traveling to Seattle. Such events can include Easter hunts, attending mass at a cathedral, or enjoying an Easter brunch during this time. With an increase amount of people and activity in the area, it is more likely that more incidents will be reported than any other weekend.
* The top 3 incidents are disturbances, traffic related calls, and suspicious circumstances. It is highly likely that these incidents occur due to congested traffic and overflowing of family gatherings. As Seattle is becoming a booming city in the tech hub world, companies are expanding their headquarters and bringing talented employees across the globe. In turn, homelessness is increasing due to unlivable wages and high rental/home costs (Balk 2019).
* The largest number of events that has occurred is in sector H. As a quick sample test, googling the coordinates (47.600876, -122.33027) which is classified as a disturbance event, shows that this incident was located in the heart of downtown Seattle, Pioneer Square specifically. Due to the fact that downtown is a buzzing city with an immense amount of people, it would make sense that crimes are reported more often in this zone.

Modeling
---
A linear regression model is created by using Microsoft Excel Data Analysis Toolpak. The model provides a population regression parameter where the slope is β<sub>1</sub> = 1.491 and a y-intercept of β<sub>0</sub> = 21.914. The linear regression model displays an upward trend and indicates that the number of incidents in a specific district are closely related to the numbers of officers responding to the scene. However, there are two outliers that is skewing the regression line, (1,1) and (125,165) which may show that it is not necessarily the best fit.

By calculating R<sup>2</sup> for the model with and without outliers, we can see how much variability of the response data around its mean. Ideally, the higher the R<sup>2</sup>, closer to 1, the better the model fits the data. However, there are some limitations with R<sup>2</sup> and sometimes does not indicate whether a regression model is adequate. Therefore, we must also consider sum of absolute error (SAE) calculation as it shows how far the regression line is from the actual data points. The lower the SAE, the better the fit.

Linear Regression             |  Residual Plot
:-------------------------:|:-------------------------:
![LR](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/LR_outlier.gif?raw=true)  |  ![Residual](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Residual_outlier.gif?raw=true)

![ANOVA](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/ANOVA.GIF?raw=true)

x             |  E(y) |  y |  E(y) - y = e
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
83	| 145.667	| 158	| -12.333
125	| 208.289| 	165	| 43.289
37	| 77.081| 	86| 	-8.919
64| 	117.338| 	131| 	-13.662
60	| 111.374| 	121| 	-9.626
31| 	68.135| 	72	| -3.865
52	| 99.446| 	96	| 3.446
60| 	111.374	| 124| 	-12.626
44| 	87.518| 	82| 	5.518
1	| 23.405	| 1	| 22.405
41	| 83.045| 	77| 	6.045
62	| 114.356| 	120| 	-5.644
38	| 78.572	| 72| 	6.572
44	| 87.518	| 76| 	11.518
91	| 157.595	| 176| 	-18.405
53	| 100.937| 	117| 	-16.063
35	| 74.099| 	68| 	6.099
39	| 80.063| 	76| 	4.063
86	| 150.14	| 158	| -7.86
| | | SAE= | 0.048

The linear regression model with outliers demonstrate a R<sup>2</sup> = 0.8795 and SAE = 0.048 while the linear regression model without outliers have a R<sup>2</sup> = 0.9591 and SAE = 68.007 (not shown). Even though the linear regression model without outliers has a higher R<sup>2</sup>, the SAE is not minimized.

The residual plot above shows that the two outliers seem to be pulling data points away from the trend line (y=0). However, when removing the outliers in the residual plot (not shown) becomes much more randomly dispersed and the “mean of zero” assumption almost holds true, meaning the mean is approximately zero all the way across the plot. Despite this and the limited observations, the best fit for linear regression model is with outliers. 

When looking at the ANOVA table, the model demonstrates that the F value is less than 0.05 and therefore statistically significant.

<table>
  <tr><th colspan=2>Descriptive Statistics</th></tr>
  <tr><td>Mean</td><td>1.889952153</td></tr>
  <tr><td>Standard Error</td><td>0.036811154</td></tr>
  <tr><td>Median</td><td>2</td></tr>
  <tr><td>Mode</td><td>1</td></tr>
  <tr><td>Standard Deviation</td><td>1.189974282</td></tr>
  <tr><td>Sample Variance</td><td>1.416038791</td></tr>
  <tr><td>Kurtosis</td><td>-0.93853082</td></tr>
  <tr><td>Skewness</td><td>0.151756917</td></tr>
  <tr><td>Range</td><td>4</td></tr>
  <tr><td>Minimum</td><td>0</td></tr>
  <tr><td>Maximum</td><td>4</td></tr>
  <tr><td>Sum</td><td>1975</td></tr>
  <tr><td>Count</td><td>1,045</td></tr>
</table>

The current threshold to receive additional funding for the Seattle Police Department is 2.5, however, they do not meet the expected threshold. When calculating the mean of the clean data as shown in Figure 9, the mean is 1.889 which is below the 2.5 threshold. This means that the department averages 1.889 officers at the scene per incident and is ineligible for additional funding. 

Key Takeaways
---
* Focus on zones with less average offier per site and the ones with the most ticketed.
* The number of incidents on Sunday (March 27, 2016) is 2x as high as Friday and Saturday that weekend.
* The top 3 incidents are disturbances, traffic related calls, and suspicious circumstances. 

References
---
