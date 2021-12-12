Use Git Update it.

# NJ-Traffic-Research

1. Data: The department of New Jersey provide the summary of the traffic crashes data from 2001-2019 at https://www.state.nj.us/transportation/refdata/accident/crash_statistics.shtm  for each counties (21 total)  of the state. 
On the other hand, it is worth noting that the Kaggle website provides a 3 million traffic accidents of US from February 2016 to December 2020 at https://www.kaggle.com/sobhanmoosavi/us-accidents. But the estimation by the NHTSA says that 6 million car accidents happen in the U.S. every year, 3 million cases in almost 5 years is only a small portion of the total accidents. If we look closer at the state of NJ, the Kaggle dataset provided 8,435 cases in year of 2019 while the DOT of NJ reported 276,861 accidents. The sampling ratio is only 3.05%. If we look at each county, it become even more problematic. As the graph below shows, the sampling ratio from each county varies significantly: the lowest is Sussex County, only 1.15% of the cases were sampled into the Kaggle dataset, the highest is Warren County with a 11.3% ratio. My conclusion is the Kaggle dataset is non-representative and good for practice of the machine learning skills but not good for the real data project research. 

2.	Data Cleaning:
NJ Department of Transportaion provides Crashes, Drivers, Vehicles, Occupants and Pedestrians datasets in text format for each year at https://www.state.nj.us/transportation/refdata/accident/rawdata01-current.shtm. 
The datasets of Crashes, Drivers and Vehicles of 2017-2019 were selected, joined and merged together for the data research.  

3. Exploratory Data Analysis:
Daily accidents (found all of the 3 highest accident days had snow weather conditions)
Accidents of each month during 2017-2019
Accidents of each hour during 2017-2019 (4-5am lowest, 5-6pm highest)
Average accidents on each day of week (Friday highest, Sunday and holiday lowest)
Accidents in each hour on different weekdays (workdays have double peaks, weekends and holidays have single peaks)

4. Machine Learning: Among the 46,536 cases recorded in Camden County from 2017-2019. There are 34,543 cases only caused property damages, 11,853 cases inccured personal injuries and 140 cases resutled in fataities. 
I built a prediction model to predict the severity of the accidents: if the accident caused injury and fatalities (1, positive) or only proprety damages (0, negative). This model can help us understand what kind of accidents are more likely to incur personal injuries or even fatalities. 
Since most of the traffic accident features are categorical variables, I found Catboost worked well for the prediction model. Although getting a accuracy score of 0.79, the initial prediction model was imbalanced due to the imlalanced training data. To fix this problem, I used the SMOTE method to make a 1:1 ratio of the positive and negative training data. I got a balanced prediction and slightly lower accuracy score (0.76). Other algorithm liek Random Forest and Gradient Boost were also tried and foudn to be slightly lower than CatBoost. 
The SHAP was used to show the importance of the features' impacts:

![image](https://user-images.githubusercontent.com/73204188/125385652-e56a8780-e368-11eb-91fe-44488c2c9d56.png)

The major factors can cause injuries or fatalties in traffic accidents are Crash Types, Extent of Damage, Principal Damage Location, Road Intersection or not, Accident Location (municipality) and Total Vehicles involved in the accidents. Other factors such as drivers' age, sex and vehicles' age do not have significant influence on the severity of the accidents (another proof that there should be no age or sex discrimination!). 

