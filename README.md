# West-Nile-Virus-Prediction-Model
A Machine learning model to predict presence of West Nile Virus at a particular location facing specific weather conditions. This prediction model will be useful as it can allow for targeted spraying of specific neighbourhoods of The City of Chicago facing higher threat of West Nile Virus


## Problem Statement

Recognising that the West Nile Virus could develop into an endemic, we aim to improve the cost-effectiveness of existing strategies to control adult mosquito populations and mitigate the spread of the virus. Considering the past weather data and locations, this model will predict presence of West Nile Virus at a particular location facing specific weather conditions. This can help the City of Chicago achieve cost savings and more efficiently allocate resources towards preventing transmission of this potentially deadly virus.

## Data Dictionary

The datasets obtained from [Kaggle](https://www.kaggle.com/c/predict-west-nile-virus/data) are are as follows. 

|Data|Description|
|:---:|:---|
|[`train.csv`](/assets/train.csv)|There are 10,505 raw observations. Each observation contains location details on the traps, the number of mosquitoes collected and an indication of whether the West Nile Virus is present. The data is for traps tested in years 2007, 2009, 2011 and 2013.| 
|[`test.csv`](/assets/test.csv)|There are 116,293 raw observations. Each observation contains location details on the traps, the number of mosquitoes collected and an indication of whether the West Nile Virus is present. The data is for traps tested in years 2008, 2010, 2012, and 2014.| 
|[`weather.csv`](/assets/weather.csv)|Weather data collected from 2 weather stations between 1 May and 31 Oct from 2007 to 2014. For further descriptions, see [pdf](/assets/noaa_weather_qclcd_documentation.pdf).|
|[`spray.csv`](/assets/spray.csv)|Data contains the date, time and location of spray in 2011 and 2013. This dataset will only be used for the benefit and costs analysis of pesticide use (see Book 5) and will not be used to build the prediction model.|

The data dictionary of the newly engineered features is found below. 

|Feature|Type|Description|
|:---|:---:|:---|
|Tmin_L0|*float*|Average minimum temperature of the weather station closest to the trap within the same month.| 
|Tmin_L1|*float*|Average minimum temperature of the weather station closest to the trap in the previous month.| 
|Tmax_L0|*float*|Average maximum temperature of the weather station closest to the trap within the same month.| 
|Tmax_L1|*float*|Average maximum temperature of the weather station closest to the trap in the previous month.| 
|SeaLevel_L0|*float*|Average atmospheric pressure of the weather station closest to the trap within the same month.| 
|SeaLevel_L1|*float*|Average atmospheric pressure of the weather station closest to the trap in the previous month.| 
|RelativeHumidity|*float*|Relative humidity computed based on dewpoint and average temperature using the formula found [here](https://www.calcunation.com/calculator/humidity-calculator.php).| 
|RelativeHumidity_L0|*float*|Average relative humidity of the weather station closest to the trap within the same month.| 
|RelativeHumidity_L1|*float*|Average relative humidity of the weather station closest to the trap in the previous month.| 
|PrecipTotal_L0|*float*|Average total precipitation reading of the weather station closest to the trap within the same month.| 
|PrecipTotal_L1|*float*|Average total precipitation reading of the weather station closest to the trap in the previous month.| 
|DewPoint_L0|*float*|Average dewpoint temperature reading of the weather station closest to the trap within the same month.| 
|DewPoint_L1|*float*|Average dewpoint temperature reading of the weather station closest to the trap in the previous month.| 
|AvgSpeed_L0|*float*|Average wind speed reading of the weather station closest to the trap within the same month.| 
|AvgSpeed_L1|*float*|Average wind speed reading of the weather station closest to the trap in the previous month.| 
|PIPIENS|*integer*|Dummy variable = 1 if Pipiens species is found within the trap and = 0 if otherwise.| 
|RESTUANS|*integer*|Dummy variable = 1 if Restauns species is found within the trap and = 0 if otherwise.| 
|WnvRisk_very low|*integer*|Dummy variable = 1 if between 0 and 2 cases of WNV were detected in the past and = 0 if otherwise.| 
|WnvRisk_low|*integer*|Dummy variable = 1 if between 2 and 6 cases of WNV were detected in the past and = 0 if otherwise.| 
|WnvRisk_medium|*integer*|Dummy variable = 1 if between 6 and 10 cases of WNV were detected in the past and = 0 if otherwise.| 
|WnvRisk_high|*integer*|Dummy variable = 1 if more than 10 cases of WNV were detected in the past and = 0 if otherwise.| 
|Rain|*integer*|Dummy variable = 1 if there was an event of either torrential storm, rain, drizzle or shower and = 0 if otherwise.| 
|Mist|*integer*|Dummy variable = 1 if there was an event of either fog, mist, haze or smoke and = 0 if otherwise.| 
