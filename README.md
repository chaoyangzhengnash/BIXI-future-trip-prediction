# BIXI-future-trip-predictiond
The project is implemented by Chaoyang Zheng, Quan Hao and Gabriel Lainesse for master course: Data mining in HEC MONTREAL.
![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/1.PNG "Optional title")

## I. Introduction 
Currently, more than 1,000 cities around the world have established or plan to establish a bike sharing system, spreading from campus, subway stations and residential areas to commercial center, grand parks and organizations. As a great application of sharing economy and the first large-scale bike sharing system in North America, Bixi Montréal plays an essential role in promoting travel flexibility and transportation efficiency, while also positively impacting the environment and quality of life.   

The primary goal of this project is to establish accurate models that will predict the number of bikes required in different areas of the city at different points in time, as the way to anticipate demand. To do so, we take into consideration a number of features, including weather conditions, weekday daytime, statutory holiday, Montreal festival data, city of Montréal geographical feature data and fuel price, through which pertinent suggestions about the demand could be provided to Bixi service to help them increase the operational efficiency. We apply and compare results obtained from linear regression and random forest models. Our result shows that the random forest with staring neighborhood gave us the best result.  

To review the code, we show how we implemented data cleaning and feature engineering in "Bixi_Pre-Processing_Step1" and "Bixi_Pre-Processing_Step2", and "Bixi_Final_Modeling" explain the visualization and modeling process.

For more detaied information about report, please see "report" folder.
 
## II.Exploratory data analysis
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


![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/4.png "Optional title")

Graph: Line chart for the number of Bixi trips in Montreal under different weekly temperature
##### Intuition 
- Positive correlation between weekly temperature and trip counts   


![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/51.png "Optional title")

Graph: : Line chart for the number of Bixi trips under different Weekly Wind speed
##### Intuition 
- Negative correlation between weekly wind speed and trip counts   


![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/5.PNG "Optional title")

Graph: : Line chart for the number of Bixi trips in Montreal under different weekly humidity
##### Intuition 
- Negative correlation between weekly humidity and trip counts (Rainy)   
   

![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/6.png "Optional title")

Graph: : Line chart for the number of Bixi trips under different Weekly Wind speed
##### Intuition 
- Negative correlation between weekly wind speed and trip counts    

![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/7.png "Optional title")

Graph: : Line chart for the number of Bixi trips under different Weekly pressure
##### Intuition 
- No significant correlation between weekly wind speed and trip counts   


![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/12.PNG "Optional title")

Graph: : City of Montreal geographical features dataset 
##### Intuition 
-The information on the distribution of each neighborhood 
- Land use (affectation) based on the City’s urban planning 

## III.Models and results
To predict the Bixi future trip volume, two regression models, a multiple linear regression and a random forest regression were developed. For shorter route affectation, we record both the starting station and ending station. Before we started to build these models, we calculated the number of rows and the mean of the count of trips for each group of features, in order to get a sense of the quality of the grouping and to make sure our target variable had meaning on its own. The count of trips is 75,986 for the starting neighbourhood models, 135,384 for long route affectation models and 120,127 for the short route affectation models. The average trip count per group is 62.88 for the starting neighbourhood models, 35.014 for the long route affectation models and 39.46 for the short affectation models. 

Performance metrics are detailed in the table below. All performance metrics were calculated on the test dataset, using the train-test split methodology for a 70% train / 30% test split of the data. 

![Alt text](https://raw.githubusercontent.com/chaoyangzhengnash/BIXI-future-trip-prediction/master/graph/13.PNG "Optional title")

Table:  Performance metric

## Reference

[1] Bixi Open Data. URL: https://www.bixi.com/en/open-data

[2] Weatherstats.ca. URL : https://montreal.weatherstats.ca/download.html

[3] Kaggle - Historical Hourly Weather Data. URL : https://www.kaggle.com/selfishgene/historical-hourly-weather-data

[4] Montréal Données Ouvertes – Affectation du Sol. URL : http://donnees.ville.montreal.qc.ca/dataset/affectation-du-sol

[5] Montréal Données Ouvertes – Arrondissements. URL : http://donnees.ville.montreal.qc.ca/dataset/polygones-arrondissements

[6] Government of Ontario – Fuels price survey information. URL : https://www.ontario.ca/data/fuels-price-survey-information

[7] Aubert Sigouin, BIXI Montreal (public bicycle sharing system) https://www.kaggle.com/aubertsigouin/biximtl

[8] Borgnat, Pierre, et al. "Shared Bicycles in a City: A Signal Processing and Data Analysis Perspective." 26 2010. Scientific Commons. 1 February 2010 <http://www.scientificcommons.org/58104633>

[9]Pablo Jensen, Jean-Baptiste Rouquier, Nicolas Ovtracht, Céline Robardet. Characterizing the speed and paths of shared bicycles in Lyon. Transportation Research Part D: Transport and Environment, Elsevier, 2010, 15 (8), pp.522-524. <10.1016/j.trd.2010.07.002>. <hal-00541307>

[10]Froehlich, J., J. Neumann and N. Oliver. "Measuring the pulse of the city through shared bicycle programs." International Workshop on Urban, Community, and Social Applications of Networked Sensing Systems‐ UrbanSense08. 2008.

[11]Patrick Vogel, Torsten Greiser, Dirk Christian Mattfeld, Understanding Bike-Sharing Systems using Data Mining: Exploring Activity Patterns, Procedia - Social and Behavioral Sciences, Volume 20, 2011, Pages 514-523, ISSN 1877-0428.

[12]Nair, Rahul & Miller-Hooks, Elise & Hampshire, Robert & Busic, Ana. (2012). Large-Scale Vehicle Sharing Systems: Analysis of Vélib'. International Journal of Sustainable Transportation - INT J SUSTAIN TRANSP. 7. 10.1080/15568318.2012.660115.

[13]Rahul Nair, Elise Miller-Hooks, Robert C. Hampshire & Ana Bušić (2013) Large-Scale Vehicle Sharing Systems: Analysis of Vélib', International Journal of Sustainable Transportation, 7:1, 85-106, DOI: 10.1080/15568318.2012.660115

[14]F. Pedregosa, G. Varoquaux, A. Gramfort, V. Michel, B. Thirion, O. Grisel, M. Blondel, P. Prettenhofer, R. Weiss, V. Dubourg, J. Vanderplas, A. Passos, D. Cournapeau, M. Brucher, M. Perrot, and E. Duchesnay, “Scikit-learn: machine learning in Python,” Journal of Machine Learning Research, vol. 12, pp. 2825–2830, 2011.













