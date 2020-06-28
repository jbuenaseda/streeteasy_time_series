# Median Rent Prediction for Studios, 1 Bedrooms and 3 Bedrooms+ in Astoria, Sunnyside and Greenpoint using Median Asking Rental Price from the Streeteasy Data Dashboard 

## Introduction:

Tons of people move to NYC everyday - and with a city so diverse with a lot of different neighborhoods and different standards of living, people tend to try out as much as they can while living in the city. The changes of one's environment is as fast paced as the city itself. You can go from having 8 roommates in a 5 bedroom apartment, get tired of them and move to a studio, meet a partner and then move to a 1 bedroom or get a new remote job that made you move to a 2 bedroom for a home office all within a short amount of time. This also applies to anyone out of the city planning to save money to finally chase their dreams in NYC while properly budgeting. So this project aims to help you plan your NYC life, which finding an apartment within your budget and preffered neighborhood is such an important factor.

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

## EDA 

![](/images/studios.png)
<br />
<br />
<br />
<br />
<br />
![](/images/1br.png)
<br />
<br />
<br />
<br />
<br />
![](/images/3br.png)
<br />
<br />
<br />
<br />
<br />
## Astoria Map:
![](/images/astoria.png)
<br />
<br />

### Visual Stationary Check Using Rolling Statistics
![](/images/rollingstudio.png)
<br />
<br />
<br />
## Models
### Base Model
![](/images/base.png)
<br />
The Persistence Model was used as the base model. It compares a lag-1 of the data to the present data as its prediction. This model had an RMSE of 54.9.
<br />
<br />
<br />
<br />
<br />
### ARIMA Model
![](/images/arima.png)
<br />
The ARIMA model (order = 1,0,1) had an RMSE score of 51.99 doing slightly better than the base model. 
<br />
<br />
<br />
<br />
<br />
### FB Prophet Model
![](/images/fb.png)
<br />
The FB Prophet model had an RMSE score of 85.64 doing worse than the base and ARIMA model.
<br />
<br />
<br />
<br />
<br />

## Conclusion
Moving into the city or within the city is a grueling task from the highly competitive apartment market to the consideration of the duration of your lease. We can always use all the guidance we can get when preparing for a move. Knowing how much we can expect a rental to be can put our minds at ease and have one less thing to worry about. With that said, the models used for this project given the different neighborhoods and apartment types differ in results. Sometimes an ARIMA model would have a lower error but sometimes even the base model beats both ARIMA and FB Prophet. It is important that all models are evaluated and compared to each other to get the best results. We get a pretty good idea on what rent could be and maybe that's enough to at least get the plan to move forward for now.  
## Future Improvement
Some future improvement and further analysis include adding in exogenous variables such as:
- cost of living of the neighborhood 
- amount of green space in the area 
- the number of restaurants/coffee shops 

Another improvement for this project I would like to add is a linear regression model with features of the apartments from:
- type of floor
- allowance of pets
- prewar/modern
- and of course, exposed brick

## Repository Navigation

## Reproduction Instructions

## Link to Presentation

## Sources
Persistence Model & Test/Train Split of TimeSeries Data was made possible with the help of Jason Brownlee, PhD of https://machinelearningmastery.com/
