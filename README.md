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

By calculating R2 for the model with and without outliers, we can see how much variability of the response data around its mean. Ideally, the higher the R2, closer to 1, the better the model fits the data. However, there are some limitations with R2 and sometimes does not indicate whether a regression model is adequate. Therefore, we must also consider sum of absolute error (SAE) calculation as it shows how far the regression line is from the actual data points. The lower the SAE, the better the fit.

Key Takeaways
---
* Focus on zones with less average offier per site and the ones with the most ticketed.
* The number of incidents on Sunday (March 27, 2016) is 2x as high as Friday and Saturday that weekend.
* The top 3 incidents are disturbances, traffic related calls, and suspicious circumstances. 

References
---
