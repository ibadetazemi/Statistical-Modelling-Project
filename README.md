Final-Project-Statistical-Modelling-with-Python

Project/Goals

(My project goals are to: 1. Connecting to CityBikes API Step 2: Connecting to Foursquare and Yelp APIs, Part 3: Joining Data, Part 4: Building a Model + Results + Challenges + future goals.)

Process

Part 1: Connecting to CityBikes API

Tasks:

1.) Choose a city covered by the CityBikes API and retrieve all available bike stations in that city. 
2.) For each bike station, use the API to call the latitude, longitude and number of bikes. Parse the JSON object into a Pandas dataframe. 
3.) Complete the city_bikes.ipynb notebook to demonstrate how you executed the tasks above.

{'company': ['NYC Bike Share, LLC',
    'Motivate International, Inc.',
    'PBSC Urban Solutions'],
   'ebikes': True,
   'gbfs_href': 'https://gbfs.citibikenyc.com/gbfs/gbfs.json',
   'href': '/v2/networks/citi-bike-nyc',
   'id': 'citi-bike-nyc',
   'location': {'city': 'New York, NY',
    'country': 'US',
    'latitude': 40.7143528,
    'longitude': -74.00597309999999},
   'name': 'Citi Bike'}

Part 2: Connecting to Foursquare and Yelp APIs

Tasks:

1.) Connect to the Foursquare API Connect to the Yelp API. 
2.) For each of the bike stations in Part 1, query both APIs to retrieve information for the following in that location: Restaurants or bars Various POIs (points of interest) of your choice 
3.) Create a DataFrame for the Yelp results and Foursquare results. 
4.) Compare the quality of the Yelp and Foursquare API. For your location, which API gives you the most complete information/better coverage? 
5.) Complete the yelp_foursquare_EDA.ipynb notebook to demonstrate how you executed the tasks above.

Part 3: Joining Data

Tasks:

1.) Join the data from Part 1 with the data from Part 2 to create a new dataframe. 
2.) Use data visualization to explore the data.
3.) Create your own SQLite database and store the data you've collected on the POIs. 
4.) Validate your data. 
5.) Complete the joining_data.ipynb notebook to demonstrate how you executed the tasks above.

Part 4: Building a Model

Tasks:

1.) Build a regression model using Python’s statsmodels module that demonstrates a relationship between the number of bikes in a particular location and the characteristics of the POIs in that location.
2.) Interpret results. Expand on the model output, and derive insights from your model. 
3.) Can you think of a way to turn the above regression problem into a classification one?
4.) Complete the model_building.ipynb notebook to demonstrate how you executed the tasks above.

Results

(Fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model: The coverage that I found is that the people in NYC use citibikes quite often and for long periods at a time.)

Challenges

(Some challenges that I faced was that the Jupyter Notebook kept glitching and had to re-start kernel numerous times another issue is that creating an environment was glitching as well.)

Future Goals

(If I had more time I would spend more time on going more in-depth with cleaning data and finding more POI and just adding more POI's.)
