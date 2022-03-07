# flood-prediction-via-logistic-regression

# Flood Prediction Based on Historical Weather Information and Flood Records By Using Logistic Regression Based on real weather and flood related data of Selangor State, Malaysia from 2013 to 2021 



# 1.	INTRODUCTION

# 1.1.	Malaysia Geography and Weather

  Malaysia is a country of Southeast Asia, lying on few degrees north of the Equator. It is separated by the South China Sea into two parts, Peninsular Malaysia at the west and Borneo's East Malaysia at the east, each occupies 40% and 60% of the total area respectively. Malaysia does not have four seasons like South Korea. Its tropical weather happens all year round with sunny skies and humid rain falls. As a tropical country, the temperatures fluctuate between 23 and 32 degrees during the year and the average rainfall is 2540mm annually. [1]
  
  Malaysia always suffers from two monsoon winds seasons, the Southwest Monsoon from May to September, and the Northeast Monsoon from October to March as shown in Figure 1. The weather usually is very rough in these months. There are some tropical islands even not allowing tourists to enter during the monsoon period. During the monsoon period, it can sometimes rain for days continuously. The Northeast Monsoon causes more rainfall than the Southwest Monsoon because the Peninsular Malaysia is partly protected by Sumatera Island from the Southwest Monsoon. Yet, floods are still a regular natural disaster in Malaysia which happen nearly every year especially during the monsoon season. 
 
# 1.2.	Flood in Malaysia

Malaysia is mostly surrounded by sea, and there is total of 189 river basins, with the main channels flowing directly to the South China Sea and 85 of them are prone to become recurrent flooding. The estimated area vulnerable to flood disaster is approximately 29,800 km2 or 9% of the total Malaysia area and is affecting almost 4.82 million people which is around 22% of the total population of the country. [2]
There are several causes which lead to floods in Malaysia. 
(a)	Rainfall: The average annual rainfall for the Peninsula is 2,500 mm and for Sabah and Sarawak it is 3,500 mm.
(b)	High tide: Water cannot flow directly into the sea when it collides with high tide. This will result in floods, especially in areas near the sea.
(c)	Size of river basin: The large size of the river basin will retain a lot of runoffs when it rains heavily. If the capacity of the river is not sufficient, floods will occur.
(d)	Man-made factors such as uncontrolled urban development, inadequate drainage infrastructure, unorganized garbage disposal, imperfect drainage system maintenance, etc.
Duties of Department of Irrigation and Drainage under Ministry of Environment and Water Malaysia are management of river basin and coastal zone, water resources and hydrology management, flood management, and eco-friendly drainage. They have a platform called as “InfoBanjir” (English translation: Flood Info) which provide water level and rainfall notification to residents throughout Malaysia. Via this platform, people can check the flood casting warning up to following three days. Figure 2 shows the main page of the official website, where the location of water level station and rainfall station are labelled 
In addition, the Department of Irrigation and Drainage in each state also provide the local “InfoBanjir” and geographic information system (GIS) to residents. Through these two platforms, the residents can even look at the map to check the location where a flood is happening or expected to happen. 

# 1.3.	Research Field

In this research, the relationship between historical weather information and the occurrence of floods is investigated. Instead of the whole Malaysia, the Klang District, Selangor State of Malaysia is set as the research target. Klang, officially Royal Town of Klang, is a royal town and former capital of the state of Selangor, Malaysia. Klang is divided into North Klang and South Klang, which are separated by the Klang River. Klang has a tropical monsoon climate with heavy rainfall year-round, especially on March, April, October, November, and December. The total rainfall in these months is usually over 200mm and this has caused floods in Klang District frequently. 
There are 413 rivers gazetted in Selangor, and the main river, of course, is Klang river. The Klang river flows through Klang Valley, which is a heavily populated area of more than four million people. Nowadays, heavy development has narrowed certain stretches of the river to the point that it resembles a large storm drain in some places. This contributes to flash floods usually after heavy rain. Figure 3 shows all the rivers in Klang District, Selangor.  
This historical record of floods that occurred in every district of Selangor State can be obtained through GIS data centre under the Department of Irrigation and Drainage Selangor State. The GIS Data Centre Selangor has created a platform which is called as “JPSSelGIS”, a uniform, comprehensive and competent data platform for monitoring, operation, control, planning and development activities in the management of the Department of Irrigation and Drainage 's key functions. From this platform, record of floods that occurred from year 2013 to year 2021 are obtained. From the statistic, a total of 1,293 cases of floods have been recorded within nearly 9 years. Figure 4 shows the page of “JPSSelGIS” platform. 
 
Figure 4 JPSSelGIS Platform by GIS Data Centre Selangor [4]
Besides the flood records, the weather information includes temperature, humidity, cloud coverage percentage, air pressure, and rainfall depth are also important in this research to be used in predicting the flood occurrence. As the historical weather information of Malaysia is not provided by government to community for free, therefore, the weather information which is recorded at “World Weather Online” is scraped by using web scraping method. 
These two data are then combined according to the dates to find out the relationship between weather information and flood occurrence. In this study, the method that is used to predict the occurrence of flood is logistic regression, which will be explained in detail in the following sections.  



# 2.	APPLICATION OF BIG DATA IN FLOOD MONITORING

# 2.1.	DATA SOURCES

First, the flood records of Selangor State can be found on “JPSSelGIS” platform. Every flood occurred from year 2013 to October 2021 is recorded in table by year. Among the criteria are date, time, location, longitude, latitude, water level of river involved, duration of flood, area of flood, depth of rain, etc. However, the data is only in Malay language, which is not foreigner friendly. The data is then copied to a Microsoft Excel file for further use. Figure 5 shows the example of flood records of Selangor State in year 2021 while Figure 6 refers to the data sheet which the data is transferred from the “JPSSelGIS” platform. The highlighted rows represent the flood records of Klang District, Selangor State. 

After getting the flood records of Klang District, the historical weather information is obtained from “World Weather Online” — a weather forecasts platform for worldwide locations. Ministry of Environment and Water Malaysia does not provide the historical weather information for free, and the free database provided by Department of Statistic Malaysia is not complete enough for the purpose of this study. Therefore, web scraping technique is used to extract the historical weather information of Klang District, Selangor State on the “World Weather Online” website. Because only the flood records of Selangor from 2013 to 2021 are available, the historical weather data from 1st January 2013 to 27th November 2021 are scraped and transferred to a Microsoft Excel file too. Figure 7 shows the weather data sample of Klang, Selangor on 1st January 2013. The date, time, temperature, rain, humidity, cloud, and pressure are scraped. Figure 8 shows the Excel file of the scraped data. The weather data of one whole day at interval 3 hours is recorded.

# 2.2.	DATA VISUAIZATION

To provide interactive visualizations of flood data with clearly shown location information, Microsoft Power BI is used. A dashboard is created as shown in Figure 9 (a) and (b) to let the users check the location of floods by year, by month, or by district. Figure 9 (b) is the interface when the flood records of Klang area is specified to be mentioned. The size of the circle refers to the amount of rainfall, while each colour represents different district as well. From the dashboard, the users can easily get know the popular flood risk areas. In 2020, Klang is the region with highest cases of floods, followed by Gombak and Hulu Langat District. The month with highest cases of floods is April, which is in the middle of Southwest Monsoon.  
Besides, the Microsoft Power BI was also used to visualize the weather information of Klang District and to find out the relationship between occurrence of floods and the weather. The dashboard users can choose the data of a specific year and month, or even day to be visualised. The top graph shows the sum of rainfall by month, while the bottom graph shows the average of the total rainfall by day in a month. On the right side of the dashboard, the upper box shows how the rainfall will affect the coverage area of cloud, temperature, and humidity. While the bottom box is the summary of the dashboard which is generated automatically according to what the user is viewing. Figure 10 (a) is the dashboard summarizing the historical weather data of Klang District from 2013 to 2021. From the summary report, we can notice that the rainfall in November is the highest, followed by December, January, and April. Coverage area of cloud is most influential to the rainfall, followed by temperature and humidity. While the Figure 10 (b) shows the dashboard about the weather information on April 2020. 



# 3.	FLOOD PREDICTION USING LOGISTIC REGRESSION

3.1.	Introduction of Logistic Regression

In statistics, the logistic model is mainly used to find out the probability of a certain class or event existing such as pass or fail, win or lose, and other issues with positive and negative outcomes. Logistic regression is used to obtain odds ratio in the presence of more than one explanatory variable. The procedure is quite similar to multiple linear regression, with the exception that the response variable is binomial. The result is the impact of each variable on the odds ratio of the observed event of interest. The main advantage is to avoid confounding effects by analysing the association of all variables together. [6] In deep learning, this even can be extended to differentiate several classes of events such as determining whether an image contains a specific object such as an apple, a dog, a human, etc. Each object being detected in the image would be assigned a probability between 0 and 1, with a sum of one. In the logistic model, the log-odds for the value labelled "1" is a linear combination of one or more independent variables ("predictors"); the independent variables can each be a binary variable (two classes, coded by an indicator variable) or a continuous variable (any real value). The corresponding probability of the value labelled "1" can vary between 0 and 1, hence the labelling; the function that converts log-odds to probability is the logistic function, hence the name. Figure 11 shows the graphs of linear regression and logistic regression. 

# 3.2.	Research Procedures and Results

As mentioned above, the historical weather information and flood records of Klang District, Selangor State from year 2013 to 2021 are used to make a flood prediction model. First of all, the average value of temperature, depth of rain, humidity, coverage area of clouds is calculated. Then, with matching to the date respectively, a new column is added to the Excel file with the title “Occurance (1:YES; 0:NO)”. “1” is given when flood is present, while ‘0’ means there is no flood recorded in the day. The Excel file is then uploaded to Google Collaboratory and opened using the Pandas library. Figure 12 shows the code of reading the Excel file, while Figure 13 shows the data being read by Pandas. 
There are 3252 rows of data. Since the main purpose of this study is not to evaluate the performance of prediction model itself, but to make a usable flood prediction model based on the historical data, all the rows are used for training the model, and half of the data as test and validation data. All the values are then normalized to make the interpretation of the model easier by looking at its weights. 
The logistic regression algorithm provided by Scikit-learn is called to train the model. The weight of the class is set as {0:1, 1:15}. As mentioned, ‘0’ means flood is absent, while ‘1’ refers to present of flood. From 1st Jan 2013 to 26th Nov 2021, there were 137 days when flood happened, and another 3115 days were safe. Therefore, more weight should be placed on ‘1’, otherwise the model will only give negative result which is ‘0’. The ‘saga’ solver which is able to handle multiclass problems and suitable for large dataset is used in this study. For regularization, the ‘L2’ regularization technique is used as penalty to make the Ridge Regression model. ‘L1’ is useful for feature selection, and it encourage model coefficients to shrink to zero. ‘L2’ is useful when we have collinear/co-dependent features. After that, the accuracy of the model is evaluated by using the validation data. From Figure 13, we can notice that the accuracy of this logistic regression model for predicting the occurrence of flood is around 81%, which is considered as high percentage.
As the accuracy of this model is satisfying, the step of model interpretation is carried out. From Figure 14, we can notice that the rainfall has the most influence on the occurrence of flood (36.07%), followed by temperature (25.46%), coverage area of cloud (19.85%), and humidity (18.62%). 
 
Then we can start to predict the occurrence of flood by using the known weather data. First, a new column is added at the end of the Pandas Data Frame with title ‘Flood Prediction(%)’. Then the prediction results are written to the new column as shown in the Figure 15. From the figure, we can notice that the performance of the prediction model is quite good. Among the 16 days we use to check the prediction result using logistic regression, there were two days when flood occurred. However, according to the prediction result of the custom model made using logistic regression, there are 5 days when floods are expected to happen. Figure 16 shows the code and result when the average temperature, rainfall, humidity, and coverage area of cloud are given manually. For example, if the values 30˚C, 25mm, 89%, 87% are given respectively, then the probability of flood is 88.05%.
The previous prediction model is based on the average value of weather information in a day. To investigate the performance of prediction model when using all the weather information at 3 hours interval instead of average value, another experiment is done.  Similar, the step of model interpretation is carried out as what have been done in first model. Figure 17 shows the importance of each feature: temperature, rainfall, humidity, cloud coverage area, pressure at 12am, 3am, 6am, 9am, 12pm, 3pm, 6pm, and 9pm, to the probability of flood occurrence. Unlike the first model, we can notice that there are some features give negative value of importance, which mean that based on the weather data of Klang District from 2013 to 2021, the changes of these features will bring negative impact to the accuracy of the model. Figure 17 shows the importance rank of all rainfall, temperature, coverage area of cloud, humidity, and pressure information at 3 hours interval in a day to the probability of flood. Figure 18 is the flood prediction result using the second logistic regression model.
To compare the logistic model 1 and model 2, some days are randomly chosen to check the difference of the prediction result. Table 1 shows the comparison between 2 models: first is when only average values are used, second is when all collected values are used. The first model gives the accuracy at 80.88%, while the second model’s accuracy reaches 88.24%, which is much higher than the model 1.
Date	Occurrence
(0: No; 1:Yes)	Prediction percentage when average values only are used (%)	Prediction percentage when all values are used (%)
Wed 11, Aug 2021	0	43	30
Thu 12, Aug 2021	0	32	21
Fri 13, Aug 2021	0	36	13
Sat 14, Aug 2021	0	38	14
Sun 15, Aug 2021	0	44	39
Mon 16, Aug 2021	0	52	54
Tue 17, Aug 2021	0	77	43
Wed 18, Aug 2021	1	74	63
Thu 19, Aug 2021	1	84	56
Fri 20, Aug 2021	0	32	17
Sat 21, Aug 2021	0	35	24
Sun 22, Aug 2021	1	41	52
Mon 23, Aug 2021	0	30	31
Tue 24, Aug 2021	0	33	13
Wed 25, Aug 2021	0	41	38
Thu 26, Aug 2021	0	25	4
Fri 27, Aug 2021	0	32	5
Sat 28, Aug 2021	0	28	9
Sun 29, Aug 2021	0	36	16
Mon 30, Aug 2021	0	36	36
Tue 31, Aug 2021	0	36	21
Wed 01, Sep 2021	0	35	24
Thu 02, Sep 2021	0	26	5
Fri 03, Sep 2021	0	27	18
Sat 04, Sep 2021	0	18	6
Sun 05, Sep 2021	0	26	17
Mon 06, Sep 2021	0	24	15
Tue 07, Sep 2021	0	27	9
Wed 08, Sep 2021	0	26	15
Thu 09, Sep 2021	0	21	12
Model Accuracy	80.88	88.24

 
4.	CONCLUSION

In Malaysia, two main causes of flooding are natural causes and human activity. Flooding caused by natural factors is due to the high intensity of rainfall in a short period of time causing flash floods. Heavy rain also caused flooding stagnant in certain places which will cause flooding. Human activity also plays an important role in causing flooding, for example disposal of solid waste into the river, sediment from land clearing and construction and the increase in impervious areas and obstacles in rivers. Coupled with natural factors such as heavy monsoon rainfall, intense convection rainstorms, poor drainage and other local factors, floods have become a common feature in the lives of a significant number of Malaysians. 
This study was conducted in order to make a flood prediction model by using the historical weather information so as to warn people around the high-risk area and if possible, to avoid damages. The findings of this study shows that all weather information such as temperature, rainfall, humidity, area or clouds cover, and pressure can be used to predict the occurrence of flood. Although the performance of this prediction model is not perfect yet, but it is verified that the implementation of logistic regression in predicting the floods show a good result. 
In fact, the flood prediction is very difficult by using single source or data. As mentioned above, there are so many factors that can lead to flood. However, this still does not deny the soundness of this idea of predicting the possibility of flood by using historical weather information and flood records with the implementation of logistic regression.  

 
Reference

1.	Climate of Malaysia. (n.d.). Retrieved from https://www.britannica.com/place/Malaysia/Climate
2.	Sani G. D/iya, Muhd Barzani Gasim, Mohd Ekhwan Toriman & Musa G. Abdullahi. (2014.) Floods in Malaysia: historical reviews, causes, effects and mitigation approach. International Journal of Interdisciplinary Research and Innovation 2: 59-65.
3.	Durumin Iya, Sani. (2014). FLOODS IN MALAYSIA Historical Reviews, Causes, Effects and Mitigations Approach. International Journal of Interdisciplinary Research and Innovations. Vol. 2. pp: 59-65.
4.	Department of Irrigation and Drainage. Ministry of Environment and Water. (n.d.). Retrieved from https://publicinfobanjir.water.gov.my/?lang=en
5.	(n.d.). Retrieved from http://jpsselgis.selangor.gov.my/portal/apps/webappviewer/index.html?id=bc18227c23b04dd9810d2f26ef8c2457
6.	Klang Historical Weather. (n.d.). Retrieved from https://www.worldweatheronline.com/klang-weather-history/selangor/my.aspx
7.	Sperandei, S. (2014). Understanding logistic regression analysis. Biochemia Medica, 12-18. doi:10.11613/bm.2014.003
8.	[ML] 6편 - Linear tasks : Logistic Regression. (n.d.). Retrieved from https://velog.io/@jeromecheon/ML-6편-Linear-tasks-Logistic-Regression과-Gradient-Decent


