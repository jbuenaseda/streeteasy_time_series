# Median Rent Prediction for Studios, 1 Bedrooms and 3 Bedrooms+ in Astoria, Sunnyside and Greenpoint using Median Asking Rental Price from the Streeteasy Data Dashboard 

## Introduction:

Tons of people move to NYC everyday - and with a city so diverse with a lot of different neighborhoods and different standards of living, people tend to try out as much as they can while living in the city. The changes to one's life situation may be as fast paced as the city itself. You can go from having 8 roommates in a 5 bedroom apartment, get tired of them and move to a studio, meet a partner and then move to a 1 bedroom or get a new remote job that made you move to a 2 bedroom for a home office all within a short amount of time. This also applies to anyone out of the city planning to save money to finally chase their dreams in NYC while properly budgeting. So this project aims to help you plan your NYC life, which finding an apartment within your budget and preferred neighborhood is such an important factor. This project also only specifically covers the three aforementioned neighborhoods, but could easily be extended to provide a comprehensive view of rent prices for all of the city.

## Data:

- The data used for this project will be the median asking price rental data extracted from the Streeteasy Data Dashboard for Studios, One Bedrooms and Three Bedrooms +
- This data contains median asking price that dates back to 2015 up to May of 2020
- The frequency of the data will be monthly

## Data Science Process:

- Obtain (download all neccessary data from the streeteasy data dashboard)
- Scrub (clean/filter data and transform it to a time series dataset)
- Explore (perform EDA to get a basic understanding of the data)
- Model (model and fit data for prediction)
- iNterpret (check accuracy of results and apply in the real world)

# Preview for Astoria:
## Astoria Map:
![](/images/astoria.png)
<br />
<br />
## EDA 

![](/images/studios.png)
<br />
<br />


![](/images/1br.png)
<br />
<br />


![](/images/3br.png)
<br />
<br />


### ACF & PACF
![](/images/acf.png)
![](/images/pacf.png)
<br />
The ACF and PACF plots helps us determine the order numbers for our ARIMA model when fitting our data
<br />
<br />


### Visual Stationary Check Using Rolling Statistics
![](/images/rollingstudio.png)
<br />
Mean and Standard Deviation of the data remains constant passing the test for stationarity
<br />
<br />

## Models
### Base Model
![](/images/base.png)
<br />
The Persistence Model was used as the base model. It compares a lag-1 of the data to the present data as its prediction. This model had an RMSE of 54.9.
<br />
<br />


### ARIMA Model
![](/images/arima.png)
<br />
The ARIMA model combines the auto-correlation function and the partial auto-correlation funciton with the number of times the data is differenced. This particular ARIMA model (order = 1,0,1) had an RMSE score of 51.99 doing slightly better than the base model. 
<br />
<br />


### FB Prophet Model
![](/images/fb.png)
<br />
FB Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. This FB Prophet model had an RMSE score of 85.64 doing worse than the base and ARIMA model. The lack of trend and seasonality seem to have affected its performance which explains the higher RMSE. 
<br />
<br />



## Conclusion
Selecting a place to rent in the city can be a grueling task, as a renter strives to get the most value out of their rent cost but must also be realistic given a highly competitive apartment market. Not to mention other constraining factors such as duration of lease. We can always use all the guidance we can get when preparing for a move. Knowing how much we can expect a rental to be can put our minds at ease and have one less thing to worry about. With that said, the models used for this project given the different neighborhoods and apartment types differ in results. Sometimes an ARIMA model would have a lower error but sometimes even the base model beats both ARIMA and FB Prophet. It is important that all models are evaluated and compared to each other to get the best results. We get a pretty good idea on what rent could be and maybe that's enough to at least get the plan to move forward for now.  
## Future Improvement
Some future improvement and further analysis include adding in exogenous variables such as:
- cost of living of the neighborhood 
- amount of green space in the area 
- the number of restaurants/coffee shops 

Another improvement for this project I would like to add is a linear regression model with features of the apartments from:
- type of floor
- allowance of pets
- prewar/modern
- walkscore
- and of course, exposed brick

## Repository Navigation
Contents:
1. csvs
2. images
3. README
4. Data Cleaning/Filtering & Exploratory Data Analysis (eda.ipynb)
5. Astoria Rent Prediction Models (astoria_rent.ipynb)
6. Greenpoint Rent Prediction Models (greenpt_rent.ipynb)
7. Sunnyside Rent Prediction Models (sunnyside_rent.ipynb)

## Reproduction Instructions

To get started:
 - Data Cleaning/Filtering & Exploratory Data Analysis (eda.ipynb) contains all data to start your own prediction model. To choose a neighborhood, simply pick from the three rental type variables (studio, 1br, 3br+) and filter columns with the neighborhood name.

## Link to Presentation

https://docs.google.com/presentation/d/1FQYufuqmlkO-GwBV9uYUDLOX8BFssuqNjYpZymGtatE/edit?usp=sharing

## Sources
Persistence Model & Test/Train Split of TimeSeries Data was made possible with the help of Jason Brownlee, PhD of https://machinelearningmastery.com/
<br />
## Appendix

Street Easy Dashboard: https://streeteasy.com/blog/data-dashboard/
<br />
Persistence Model: https://machinelearningmastery.com/persistence-time-series-forecasting-with-python/
<br />
Statsmodel ARIMA: https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima_model.ARIMA.html
<br />
FB Prophet: https://facebook.github.io/prophet/
