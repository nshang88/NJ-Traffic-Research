# NJ-Traffic-Research

1. Data: The department of New Jersey provide the summary of the traffic crashes data from 2001-2019 at https://www.state.nj.us/transportation/refdata/accident/crash_statistics.shtm  for each counties (21 total)  of the state.

On the other hand, it is worth noting that the Kaggle website provides a 3 million traffic accidents of US from February 2016 to December 2020 at https://www.kaggle.com/sobhanmoosavi/us-accidents. But the estimation by the NHTSA says that 6 million car accidents happen in the U.S. every year, 3 million cases in almost 5 years is only a small portion of the total accidents. If we look closer at the state of NJ, the Kaggle dataset provided 8,435 cases in year of 2019 while the DOT of NJ reported 276,861 accidents. The sampling ratio is only 3.05%. If we look at each county, it become even more problematic. As the graph below shows, the sampling ratio from each county varies significantly: the lowest is Sussex County, only 1.15% of the cases were sampled into the Kaggle dataset, the highest is Warren County with a 11.3% ratio. My conclusion is the Kaggle dataset is non-representative and good for practice of the machine learning skills but not good for the real data project research. 

2.	Data Cleaning 
NJ Department of Transportaion provides Crashes, Drivers, Vehicles, Occupants and Pedestrians datasets in text format for each year at https://www.state.nj.us/transportation/refdata/accident/rawdata01-current.shtm. 
The datasets of Crashes, Drivers and Vehicles of 2017-2019 were selected, joined and merged together for the data research.  

3. Exploratory Data Analysis 
Daily accidents (found all of the 3 highest accident days had snow weather conditions)
Accidents of each month during 2017-2019
Accidents of each hour during 2017-2019 (4-5am lowest, 5-6pm highest)
Average accidents on each day of week (Friday highest, Sunday and holiday lowest)
Accidents in each hour on different weekdays (workdays have double peaks, weekends and holidays have single peaks)

4. Machine Learning
