<div align="center">

![banner](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Title_Image.PNG)

# Final Project - Common Issues & Delays in Air Travel

</div>



## Table of Contents

* [Introduction](#Introduction)<br>
* [Description of Source Data](#Description-of-Source-of-Data)<br>
* [Main Topics We Hope to Address with the Data](#Main-Topics-We-Hope-to-Address-with-the-Data)<br>
* [Database](#Database)<br>
* [Data Cleaning](#Data-Cleaning)<br>
* [Dashboard](#Dashboard)<br>
     * [Storyboard](#Storyboard)<br>
     * [Tableau Visualizations](#Tableau-Visualizations)<br>
* [Air Travel Overview](#Air-Travel-Overview)<br>
* [Flight Delays and Cancellations](#Flight-Delays-and-Cancellations)<br>
     * [Flight Delay Prediction Model](#Flight-Delay-Prediction-Model)<br>
     * [Flight Cancellation Prediction Model](#Flight-Cancellation-Prediction-Model)<br>
* [Flight Accidents and Incidents](#Flight-Accidents-and-Incidents)<br>
     * [Accidents Weather Analysis](#Accidents-Weather-Analysis)<br>
          * [Types of Weather Conditions and Their Association with Aviation Accidents](#Types-of-Weather-Conditions-and-Their-Association-with-Aviation-Accidents)<br>
          * [Frequency of Aviation Accidents with Different Weather Conditions](#Frequency-of-Aviation-Accidents-with-Different-Weather-Conditions)<br>
* [Analysis of Mishandled Baggage](#Analysis-of-Mishandled-Baggage)<br>
* [Summary and Future Analysis](#Summary-and-Future-Analysis)<br>



## <b>Introduction</b>

For the past century, air travel became the most popular and convenient means of travel for long distances. Nevertheless, it is not uncommon to encounter various problems along the way, including aircraft technical issues and mishandled luggage. Additionally, the most common issue travelers face are delays and cancellations that can be caused by inclement weather or overbooking. 

Despite all of these issues, air travel still remains as the most popular choice for many people, therefore, understanding these issues and the data behind it can be hugely beneficial for future travel.  

<div align="center">

![plane_sunset](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Plane_sunset.jpg)

</div>



## <b>Description of Source of Data</b>

We will explore multiple datasets of flight information and use statistical and machine learning techniques to predict whether an issue may arise while traveling.

The primary source of the data will be exported from raw CSV files by the [Bureau of Transportation](https://transtats.bts.gov/Fields.asp?gnoyr_VQ=FGK), the [Federal Aviation Administration](https://www.asias.faa.gov/apex/f?p=100:1::::::), the [Department of Homeland Security](https://www.dhs.gov/tsa-claims-data), and the [National Transportation Safety Board](https://www.ntsb.gov/safety/data/Pages/Data_Stats.aspx).



## <b>Main Topics We Hope to Address with the Data</b>

With the datasets provided, we hope to create comprehensive analysis and visualizations to:

* Understand air traffic volume and trends over past years
* Explore and compare the most common US airlines and the issues they face
* Create a Machine Learning model that can predict future flight delays and cancellations based off of past data
* Investigate flight accidents in correlation to different airlines, aircraft manufacturers, and airport locations
* Understand the severities of flight accidents based on month, day of the week, and carrier
* Evaluate how the frequency and severity of aviation accidents varies with different weather conditions
* Examine the different causes of flight accidents and incidents, such as environmental issues, human factors, and aircraft performance
* Research how TSA and security lines affect overall air travel experience based on different airports
* Assess mishandled baggage data in comparison to different months and airlines



## <b>Database</b>

For our project, we decided to use PGAdmin SQL as our database. PGAdmin SQL is a powerful and scalable database management database system which means it can handle large amounts of data and high volumes of transactions. It is also compatible with a wide range of tools and technologies making it easy to integrate with other systems and applications which will be useful when connecting to our Machine Learning Model.

The <b>Entity Relationship Diagram (ERD)</b> can be found below.

<div align="center">

![ERD](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Connections_Quickdbd.PNG)

</div>



## <b>Data Cleaning</b>

Data cleaning is an important part of our analysis process to ensure the data is accurate, complete, and ready for analysis. The first step was to check for missing or incomplete data. Any missing or incomplete data was either removed or filled in with appropriate values. For example, when building the Machine Learning model, all the rows with null values were dropped. The next step was to check for outliers or extreme values in the data. Any outliers were either removed or transformed to make the data more representative of the overall population. The data was then checked for consistency and any inconsistencies were corrected. For example, many name variations for the same airline and airport were corrected to reflect only one consistent name. Finally, the data was formatted and structured in a way that was suitable for analysis.



## <b>Dashboard</b>

Dashboards and storyboards are important for data analysis because they provide a way for users to quickly and easily understand complex data sets so they can help users make better decisions by providing them with a clear and concise view of the data.



### <b>Storyboard</b>

An initial draft of our Storyboard created on Google Slides can be found [here](https://docs.google.com/presentation/d/16ui3_aKnWDj3g7POys37TOuYBOLekHT9SUnBKHB52M0/edit#slide=id.gcb9a0b074_1_0). 



### <b>Tableau Visualizations</b>

The main elements and visualizations on the Storyboard were created using Tableau Public. All of the visualizations on Tableau Public can be viewed [here](https://public.tableau.com/app/profile/william.kim4690/viz/WeatherDelaysbyAirline_16734964116180/Story1?publish=yes). All of these vizualizations are interactable by filtering them through desired airlines, aircraft manufacturers, years, and injury severity.



## <b>Air Travel Overview</b>

Air travel has seen significant growth, with the number of passengers increasing steadily in the recent years. In the US there is a vast network of airports and airlines, with the largest airlines being American Airlines, Delta Air Lines, and United Airlines. The high season for air travel is during the summer, with July having the highest number of travelers, 81 million passengers on average. The low season is during the winter, with February averaging at 61.5 million passengers. Airfare prices tend to be higher during the summer high season and lower during the winter low season. 

<div align="center">

![Number of Air Travel Passengers in US](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Number%20of%20Air%20Travel%20Passengers%20in%20US.png)

</div>



## <b>Flight Delays and Cancellations</b>

In 2022 in the US there was a total of 5,625,620 flights operated. Out of these flights 4,335,485 arrived on time and 1,132,113 were delayed. This means that an enormous 20.12% of all flights were delayed. Additionally, 144,515 flights were cancelled, which is about 2.57% of all flights.

Recent data from the US Bureau of Transportation Statistics for 2021 shows that air carrier delay is the primary cause, accounting for 40% of all flight delays. This means that issues such as overbooking, crew scheduling, and other operational issues within the airline are the primary reason for delays. Another significant cause of delays, accounting for 35% is categorized as aircraft arrives late. This includes situations where a holdup of a previous flight with the same aircraft causes delay for subsequent flight. Additionally, 17% of all delays were caused by National Airspace System (NAS) issues, which include problems with air traffic control systems and air traffic congestion. Extreme weather, such as strong winds, thunderstorms, and other severe weather conditions, is another notable source of flight delays, accounting for 7% of all delays. Interestingly, security delay, which includes issues with airport security and TSA procedures, is the least major cause of all flight delays, accounting for less than 1%. 

<div align="center">

![Flight Delays](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Delay.PNG)

</div>



### <b>Flight Delay Prediction Model</b>

For our analysis, we decided to use Supervised Machine Learning in order to predict whether a flight would arrive with a delay of 15 minutes or more. Supervised Machine Learning is a type of machine learning where the model is trained on labeled data. In the context of predicting airline delays, this means that the model is trained on a dataset that includes information about past flights, such as departure and arrival times, airline, and whether or not the flight was delayed. The goal of the model is to learn from this labeled data and make predictions about whether future flights will be delayed.

Before implementing a machine learning model, we performed a number of steps to prepare the data for analysis. This process, known as data preprocessing, involved cleaning and transforming the raw data to make it more suitable for modeling. In our case we have decided to drop any rows with null values as well as any columns where all values are null.

In order to successfully run our machine learning model, a wide range of preliminary features were selected, such as: 

* Day of the week/Day of the month: Certain days may be more prone to delays due to factors such as holidays, weather patterns, or air traffic volume

* Airline/Flight Number: This can help identify specific flights or airlines that are more subjective to delays

* Flight origin and destination: Delays at certain airports may be more common due to factors such as congestion or maintenance issues

* Departure time: Flights that depart during peak travel times or in adverse weather conditions may be more prone to delays

Once the data was in a suitable format, we split it into a training set and a testing set. The training set was used to build the model, while the testing set was used to evaluate its performance. This separation is important because it allows us to test the model's ability to adapt to new, unseen data.

To achieve our goal, we decided to test several different approaches to train and evaluate data models. We started with Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifier. We then oversampled the data using the RandomOverSampler and SMOTE algorithms, and then under sampled the data using the ClusterCentroids algorithm. Afterwards, a combinatorial approach of over- and under sampling using the SMOTEENN algorithm was deployed.

After comparing all of the models, Balanced Random Forest Classifier performed the best with a balanced accuracy score of 91.5%. The main benefit of this model is its ability to achieve a high level of accuracy, which means that it is able to make correct predictions for a large proportion of the samples in the dataset. Additionally, a Balanced Random Forest Classifier is designed to handle imbalanced datasets, which means that it can perform well even when there is a disproportionate number of samples in one class compared to the other. It is important to note that this model also has its limitations such as overfitting, which means the model might perform well on the training data but poorly on new, unseen data.

This approach allows us to automate the process of predicting delays and to potentially improve upon it over time as new data becomes available.

Please see [here](https://github.com/billywkim/Final_Project/blob/main/Machine_Learning/Delays_ML.ipynb) for our Machine Learning code.



### <b>Flight Cancellation Prediction Model</b>

Using the same logic as the Flight Delay Prediction Model, the Flight Cancellation Prediction Model was built by analyzing historical flight data and identifying patterns. Balanced Random Forest Classifier model was the most successful with a 75% accuracy score. The model uses a set of features and data parameters that are believed to be indicative of flight cancelations. Some of the features used would include data on flight schedules, such as departure and arrival times, as well as information on flight origins and destinations. The model then used an algorithm to identify the most important features and the relationships between them, which allows for more accurate predictions of flight cancelations.

Overall, the model achieved some positive results, however there is still room for improvement. To increase the prediction index, it would be useful to incorporate additional data parameters in the analysis. These can include real-time weather data, air traffic control information, aircraft maintenance schedules, airport infrastructure, and security and TSA procedures. By including these additional data parameters, the model could more accurately predict flight cancelations and improve the prediction index.

Please see [here](https://github.com/billywkim/Final_Project/blob/main/Machine_Learning/Cancellations_ML.ipynb) for our Machine Learning code.

<div align="center">

![multiple_planes](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Multiple_planes.jpg)

</div>



## <b>Flight Accidents and Incidents</b>

Aviation incidents and accidents are a major concern for the industry and the general public. In this analysis, we will delve deeper into the data to identify patterns and trends in flight incidents and accidents. We will examine the number of accidents by airlines, aircraft manufacturers, and the most common airports where incidents occur. This information can help us to understand key risk factors for future travelers. 
From the data gathered by the National Transportation Safety Board (NTSB) between 2011 to 2021, the following analysis can be made for commercial air travel:
* Delta Air Lines, accounted for more incidents and accidents than any other airline with 65, followed by Southwest with 55. SkyWest Airlines had the lowest count with only 1 incident. Moreover, Boeing aircrafts count for 56% of all commercial incidents and accidents.
* California has the highest number of incidents and accidents with 28, closely followed by Texas and Georgia with 25, and Florida with 22.
* The cities that experiences the most issues are similar among departures and arrival amounts. Atlanta encounters the most incidents, followed by Chicago, Los Angeles, Denver, and Dallas.
* Incidents and accidents occur seasonally, peaking during June and December when air travel is most frequent. The lowest incidents occur on January, April, and November. Furthermore, travelers are 72% more likely to experience an issue on Mondays than on Sundays.
* Environmental factors, such as inclement weather, are the primary cause of incidents and accidents. The second most common cause is human error and actions performed incorrectly. Intriguingly, faulty aircrafts and structural concerns only accounts for 17% of all incidents and accidents experienced during this period.

<div align="center">

![Broken_plane](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Broken_airplane.jpg)

</div>

## <b>Accidents Weather Analysis</b>

Aviation accidents in relation to weather is a significant concern for the aviation industry. Weather conditions such as thunderstorms, icing, and turbulence can greatly affect the safety of flights and increase the risk of accidents. In this section, we will explore the types of weather conditions most commonly associated with aviation accidents, the frequency of aviation accidents with different weather conditions, whether certain types of aircraft are more prone to accidents in certain weather conditions, and human error.

The dataset for the analysis can be found [here](https://github.com/billywkim/Final_Project/blob/main/Resources/AviationData_Weather.csv), it contains approximately 18,000 entries. For the purpose of this analysis the following contains all data where: 

- Airplane_Category = 'Airplane'
- Event_Type = 'Accident'
- Country = 'USA'
- Year = 2000 to 2021

#### <b>Data Cleaning</b>
* Check % missing data and drop columns >35% missing
* Filter the dataset where:
	- Aircraft_Category = Airplane
	- Country = United States
	- Investigation_Type = Accident
* Change date 'objects' to 'datetime'
* Change latitude and longitude from strings to float
* Split Location into City and State
* Bucket Airport_Names with same labels
* Bucket Airport_Code with same labels
* Added Day/Month/Season columns
* Bucket Registration_Numbers with same labels
* Change 'Make' column to 0s and 1s instead of Y/N
* Merged Injury_Severity labels
* Filter Report_Status for analysis
* Drop noisy columns

This data contains all kinds of flights, from commercial to instructional to skydiving and everything in between.

<div align="center">

![image](https://user-images.githubusercontent.com/110706169/212215561-207c0b20-a926-49e9-b7de-bfe5a69e55f1.png)

</div>



#### <b>Types of Weather Conditions and Their Association with Aviation Accidents</b>

In the United States, the seasons are generally defined as spring (March-May), summer (June-August), fall (September-November), and winter (December-February). The specific weather conditions can vary greatly depending on the region of the country, but here is a general overview of what you might expect during each season:

Spring: As the weather begins to warm up, many areas of the country will see increasing rainfall and thunderstorms. The northern regions may still see some snow and cold temperatures, while the southern regions will start to experience warmer weather.

Summer: This is typically the warmest time of year in the US, with high temperatures and humidity in many regions. The southern and central regions of the country are particularly known for their hot and humid summers. Thunderstorms and hurricanes are also more common during this time in some areas.

Fall: As the weather starts to cool down, many regions will experience changing foliage and mild temperatures. Rainfall and thunderstorms can still be common, but the weather is generally more stable than during spring.

Winter: This is typically the coldest time of year in the US, with snow and ice storms in many northern regions, and freezing temperatures in many other areas of the country. Some southern regions may see milder temperatures, but heavy rainfall can still be a possibility.

<div align="center">

![Seasons](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Weather_Graphs.png)

</div>
As we can see from the data, the majority of airplane accidents occur during the summer months, with over 35% of accidents happening during this season. This may suggest that warmer weather conditions and increased air traffic during the summer months contribute to a higher risk of accidents.


#### <b>Frequency of Aviation Accidents with Different Weather Conditions</b>

There are two main weather conditions when it comes to aircraft control: VMC (Visual Meteorological Conditions) and IMC (Instrument Meteorological Conditions). VMC refers to conditions where the pilot is able to fly the aircraft using visual cues outside the cockpit, while IMC refers to conditions where the pilot must rely on instruments inside the cockpit to fly the aircraft safely. This could be caused by poor visibility, clouds, or inclement weather. Pilots must be trained and qualified to fly in both VMC and IMC conditions.

<div align="center">

![Freq WC](https://user-images.githubusercontent.com/110706169/214718930-f93e065a-feec-44b2-8ce9-17ccb0ae4f36.png)
</div>

17,000 or about 95% of recorded accidents happened under VMC conditions. This data suggests that flying under VMC conditions, where pilots can rely on visual cues to navigate and make decisions, is more prone to accidents than flying under IMC conditions.This could be due to factors such as pilot error or lack of experience flying in adverse weather conditions.



#### <b>Relationship Between Engine Configuration and Accident Risk in Different Weather Conditions</b>
    
In this section, we examine the relationship between engine configuration and the risk of accidents in different weather conditions.We found that the fewer engines a plane has, the more likely it is to have an accident. This trend could suggest that single-engine and twin-engine aircraft may be more prone to accidents in certain weather conditions. It this case we must note that we are only looking at the number of engines and not the performance of bigger or smaller engines.

 <div align="center">
   
![Engines](https://user-images.githubusercontent.com/110706169/213612139-172411ee-40a7-4308-a238-14fcfb969b42.png)
    
It's important to note that while the number of engines on a plane can be a significant factor in the risk of accidents, it is not the only factor to consider. Other factors such as pilot error and maintenace also play a role; However, for the purpose of our analysis we will only take into account pilot error in a following section.   
![image](https://user-images.githubusercontent.com/110706169/214722439-e6ebbb42-1323-40e2-b6ef-60397a04f729.png)</div>
  
 From the data shown above we can see the Top Ten Manfucaturers by weather condition. Most of these manufacturers produce 1 and 2 small engine aircrafts specially Cessna, Piper, and Beech; who are the top 3 contenders for most their airplanes accounting for about 55.5% of total accidents from 2000-2021. Other large manufacturers, such as Boeing, offer a variety of different aircraft from 1, 2, and 4 engines. Boeing had a total of 239 accidents from 2000 - 2021.

#### <b> Role of Human Factor in Aviation Accidents </b>

In this section we analyzed what role pilot error plays in different weather conditions. We did this by filtering reports into 5 categories where the report indicated the cause being:

* Pilot Error - keywords used  "pilot"
* Weather - keywords used "weather", "climate", "rain", "snow", "thunder", "cloud"
* Probable Cause - keywords used "Probable Cause"
* Unknown - keywords used "Unknown"
* Other - Any report that does not contain the keywords above.

<div align = "center">
    
![image](https://user-images.githubusercontent.com/110706169/214713050-fbfb9b1f-973e-432a-82c4-716e633a4704.png)

</div>

“Unknown” category are airplanes that were never found.
“Other” category includes aircraft failure and events not related to the pilot or weather.


Human error is the leading cause of airplane accidents, with 60.6% of reports attributed to pilot error or inadequate training. Even reports attributed to weather often mention human error as a secondary factor, highlighting the importance of continued training and safety measures in the aviation industry. 

![image](https://user-images.githubusercontent.com/110706169/214714847-011990ea-cc8b-4cf0-8af8-41534297d9b8.png)

Approx. 14.61% or 2,630 of these accidents were fatal.
## <b>Analysis of Mishandled Baggage</b>

Mishandled baggage is one of the common issue faced by travelers all around the world. When baggage is not handled properly, it can lead to inconvenience and frustration for the traveler, who may be left without essential items or personal belongings for an extended period of time. Using data from the Bureau of Transportation for 2019, 2020, and 2021, an analysis was created to discover the following key points: 
* In 2019, 0.6% of all checked baggage was mishandled. This percentage decreased in 2020 to 0.42%  most likely due to the global pandemic and general decrease in travel. In 2021 there was a significant increase, with approximately 0.5% of checked baggage being mishandled.
* According to the analysis, the percentage of mishandled baggage varied throughout the year, with the highest percentage occurring in June at 0.63% and the lowest percentage occurring in September at 0.43%. Higher mishandled baggage percentages can be observed during the summer and winter but lower during the spring and fall seasons.
* The percentage of mishandled baggage also fluctuates based on the airline. Allegiant Air had the lowest percentage of mishandled baggage at 0.16%, while Envoy Air had the highest percentage at 0.86%. 
* Interestingly, Southwest Airlines had one of the highest number of enplaned baggage while maintaining one of the lowest mishandled baggage percentage at 0.37%. American Airlines has similar enplaned baggage amounts to Southwest Airlines but has the second highest mishandled baggage rate at 0.76%.

<div align="center">

![bag_delay](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/baggage_delay.jpg)

</div>



## <b>Summary and Future Analysis</b>

In conclusion, the data analysis of Common Issues & Delays in Air Travel has highlighted several key areas that contribute to flight disruptions. By understanding air traffic volume and trends over past years, we were able to explore and compare the most common US airlines and the issues they face. A Machine Learning model was also created that can predict future flight delays and cancellations based off of past data. We also investigated flight accidents in correlation to different airlines, aircraft manufacturers, and airport locations, and weather conditions.

Furthermore, the research explored how TSA and security lines affect the overall air travel experience based on different airports and assessed mishandled baggage data in comparison to different months and airlines. These findings provide valuable insights that can be used to improve the overall air travel experience for passengers and enhance the safety of air travel.

Some potential areas for future analysis to improve this project related to common issues and delays in air travel include:

* Incorporating more data sources: In order to get a more comprehensive understanding of common issues and delays in air travel, it would be beneficial to incorporate data from a wider range of sources, such as passenger feedback and maintenance records.

* Incorporating real-time data: To improve the accuracy and relevance of the analysis, it would be beneficial to incorporate real-time data and develop systems for monitoring flight performance and weather conditions in real-time.

* Collaboration with other stakeholders: To improve the analysis of common issues and delays in air travel, it would be beneficial to collaborate with other stakeholders in the industry such as airlines, airports, and regulators to share data, insights, and develop solutions together.

* Identifying the impact of COVID-19 pandemic on air travel: It can be analysed using data analytics on how it affected the air travel industry, how it impacted the delays and disruptions, and how can it be handled in the future.