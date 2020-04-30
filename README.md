# BIXI-future-trip-predictiond
The project is implemented by Chaoyang Zheng, Quan Hao and Gabriel Lainesse for master course: Data mining in HEC MONTREAL.
![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/1.PNG "Optional title")

## I. Introduction 
Currently, more than 1,000 cities around the world have established or plan to establish a bike sharing system, spreading from campus, subway stations and residential areas to commercial center, grand parks and organizations. As a great application of sharing economy and the first large-scale bike sharing system in North America, Bixi Montréal plays an essential role in promoting travel flexibility and transportation efficiency, while also positively impacting the environment and quality of life.   

The primary goal of this project is to establish accurate models that will predict the number of bikes required in different areas of the city at different points in time, as the way to anticipate demand. To do so, we take into consideration a number of features, including weather conditions, weekday daytime, statutory holiday, Montreal festival data, city of Montréal geographical feature data and fuel price, through which pertinent suggestions about the demand could be provided to Bixi service to help them increase the operational efficiency. We apply and compare results obtained from linear regression and random forest models. Our result shows that the random forest with staring neighborhood gave us the best result.  
 
## II.exploratory data analysis
To learn insights towards our dataset, we generated following data visualization:

![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/2.png "Optional title")

Graph: Ridgeline Plot of Trip Count per Hour of the Day per Neighborhood

##### Intuition 
- Top 2 neighborhood in Bixi usage: Le Plateau-Mont-Royal and Ville-Marie
- 2 peak period: 7-9 and 16-18 (commuting time)

![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/3.png "Optional title")

Graph: Box plot for the number of Bixi trips in Montreal under each weather condition in a given day 

##### Intuition 
- Completed metrics for weather condition. e.g.: Temperature, Wind speed etc(Numerical data)
- Descriptions of observed weather.e.g.:  broken clouds, thunderstorm, light rain etc.











