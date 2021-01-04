# Project 01: Seattle PD Funding Eligibility
> The analysis aims to gain insight about the logs of emergency 911 calls from the Seattle Police Department reported on March 26, 2016 - March 28, 2016. In addition, the study discusses whether the department will be eligible for additional funding if the minimum standard of 2.5 officers onsite per incident is met.

General Information
---
The project is part of a graduate course (_Fundamentals of Data Analytics_) at Western Governor's University. The data will not be provided, but rather an explanation of key findings and analysis of the project. The raw data set contains 1,046 observations and 20 features which is later reduced to 6 features. 

**To expand the project even further as a business use case, how can the police department increase the chances of their eligibility for funding if not eligible?**

Summary
---

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
The data is dated from March 26, 2016 to March 28, 2016 which happens to be a holiday weekend, Easter Sunday. By looking at the number of events per day, one will notice that there is a high level of activity on March 27, 2016, the day before Easter Sunday. This high volume of activity shows that there are many active people on the streets or at home, possibly preparing for family gatherings which can include non- resident family members traveling to Seattle. Such events can include Easter hunts, attending mass at a cathedral, or enjoying an Easter brunch during this time. With an increase amount of people and activity in the area, it is more likely that more incidents will be reported than any other weekend.

![NumofIncidentsbyDistrict](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Num%20of%20Incidents%20by%20District.png?raw=true)
![NumofIncidentsByEventType](https://github.com/sangtvo/Seattle-PD-Funding-Eligibility/blob/main/images/Num%20of%20Incidents%20by%20Event.png?raw=true)

Analysis
---
* 

Technologies
---
* Microsoft Excel
* Tableau

Key Takeaways
---
* Focus on zones with less average offier per site and the ones with the most ticketed.

References
---
