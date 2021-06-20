# Opioids in America
*Capstone Project: Nashville Software School Data Analytics Cohort 4*

![image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR20CmONiC1OShzHataD0xDCZ7ecCl-3gs7DItI2-nW-v8WicLuHT3lrXMq5Zn9V5c-Rgo&usqp=CAU)




 # Summary
 Opioid use and abuse is a subject that is often in the news.  As a pharmacist in Tennessee, I have seen a dramatic decrease in the number of prescriptions and the amount being dispensed, but does the data reflect this? Has there been a decline in abuse with the new laws that have been put in place in some states? If so, have deaths due to overdose decreased also?
# Motivation
Opioids is a topic that has caused me distress over my years in healthcare. I have seen how patients start on a simple pain treatment for an acute surgery only to progress into chronic use or even move to heroin abuse. As a pharmacist, I have to be vigilant about timing of refills so that I would not contribute to their addiction and potential overdose. Many patients that use opioids chronically call in repeatedly to ask when they can have their next fill, even though they know the answer.  I have had patients admit that they will take heroin if they cannot get their opioids filled early and had patients overdose on street drugs while trying to overcome their addiction. I honestly hope that the data shows that the US is coming out of the opioid crisis.
# Methodology

## Data Acquistion

* Data on overdose deaths and illicit drugs was obtained from the CDC website Wonder.cdc.gov
* Opioid dispensing rate data was scraped from https://www.cdc.gov/drugoverdose/maps/rxstate2019.html using BeautifulSoup

## Cleaning

* Data cleaning was performed using Python in Jupyter Notebook. 
* Cause of death data fields were recast and irrelevant columns were dropped. A group by function on the state and year columns aggregated the deaths for specific drugs. A rate of deaths per population column was added and calculated.
* Illicit and RX data added a new column to specify which category the drug was in then the files were merged and a new column to calulate the percentage of prescriptions per population.
## Analysis
### Challenges and Limitations: 
* There were many death totals that were "Suppressed" to protect individual privacy. The suppressed values are in range of 0 - 9 so they were replaced with 5 to include these states in the analysis. A 0 value could also have been used.
* Drugs are grouped in the Wonder database, causing difficulty determining which drug caused the overdose. For cause of death data, "other synthetic narcotics" and "Other unspecified narcotics" were grouped into "Other narcotics" 
* Some ICD-10 codes are not specific enough to describe the drug that caused the overdose but the CDC has added this specificity with codes starting 3/2021.
* Some overdoses are caused by 2 drugs
* Fentanyl is a synthetic narcotic that is available by prescription (RX) but also man-made on the "street", ICD-10 codes do not differentiate which fentanyl was involved in the overdose.

## Sources

* http://pdaps.org/datasets/pdmp-implementation-date
* https://wonder.cdc.gov/
* https://www.cdc.gov/drugoverdose/maps/rxstate2019.html
## Tools Used

* Python/Pandas - to cleaning and aggregating data
* Excel - to visualize data
* Power BI - to create an interactive dashboard
* Visual Studio Code - to create markdown files
* Git - to control version