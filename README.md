# Project 01: Seattle PD Funding Eligibility
> The analysis aims to gain insight about the logs of emergency 911 calls from the Seattle Police Department reported on March 26, 2016 - March 28, 2016. In addition, the study discusses whether the department will be eligible for additional funding if the minimum standard of 2.5 officers onsite per incident is met.

General Information
---
The project is part of a graduate course (_Fundamentals of Data Analytics_) at Western Governor's University. The data will not be provided, but rather an explanation of key findings of the project. The raw data set contains 1,046 observations and 20 features which is later reduced to 6 features. 

**To expand the project even further as a business use case, how can the police department increase the chances of their eligibility for funding if not eligible?**

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
(https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/images/Average%20Number%20of%20Officers%20Per%20Event.png?raw=true)
![header image](https://sangtvo.github.com/account/Seattle-PD-Funding-Eligibility/images/districts.png)

Summary
---

Technologies
---
* Microsoft Excel
* Tableau

Key Takeaways
---
* Focus on zones with less average offier per site and the ones with the most ticketed.

References
---
