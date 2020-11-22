# Surfs_up

## Overview of the analysis: 
Analyze weather data from Oahu, Hawaii in order to determine if opening a surf and shakes shop is sustainable year-round.
## Results: 
From the two analysis deliverables three major points can be observed:
1.	There are 1700 temperatures taken from June, and there are 1517 temperatures taken from December. 
2.	The average temperature during June is 74F and the average temperature during December is 71F.
3.	The highest temperature registered during June (2017) was 85F, while the highest temperature during December (2017) was 83F.

![](https://github.com/KatiuscaQ/Surfs_up/blob/main/Resources/June_temps.PNG)
![](https://github.com/KatiuscaQ/Surfs_up/blob/main/Resources/Dec_temps.PNG)

  
## Summary: 
The temperatures for Oahu do not change drastically through the year. When typically, June is considered a Spring-Summer month and December is considered a Winter month (in the northern hemisphere), thanks to being located close to the equator Oahu-Hawaii doesn’t present drastic changes on its temperature.

In addition to the temperature analysis during June and December, it is advisable to analyze the precipitation during both months to see the differences between them. See two additional queries below:
```html
# Precipitation  during June
june_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==6)
june_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==6).all()
june_prcp_df = pd.DataFrame(june_prcp, columns=['June Precipitation'])
june_prcp_df.describe()
```
The data frame from this code is:

![](https://github.com/KatiuscaQ/Surfs_up/blob/main/Resources/June_prcp.PNG)

 
```html
# Precipitation during December
dec_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==12)
dec_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==12).all()
dec_prcp_df = pd.DataFrame(dec_prcp, columns=['December Precipitation'])
dec_prcp_df.describe()
```
The data frame from this code is:

![](https://github.com/KatiuscaQ/Surfs_up/blob/main/Resources/Dec_prcp.PNG)

 
Thanks to the analysis on the temperatures and precipitations, W. Avy will have more information to back up his decision.
