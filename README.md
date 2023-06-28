Final-Project-Statistical-Modelling-with-Python

Project/Goals

(My project goals are to: 1. Connecting to CityBikes API, Step 2: Connecting to Foursquare and Yelp APIs, Part 3: Joining Data, Part 4: Building a Model + Results + Challenges + future goals.)

Process

Part 1: Connecting to CityBikes API

For this part, we will work with an API that you have not seen before: CityBikes

Citybikes is an API that provides bike sharing data for apps, research and projects. CityBikes supports more than 400 cities and the Citybikes API is an interesting dataset for building bike-sharing transportation projects.

Your tasks are as follows:

Explore the structure of the API, query the API and understand the data returned. Choose a city covered by the CityBikes API and retrieve all available bike stations in that city. For each bike station, use the API to call the latitude, longitude and number of bikes. Parse the JSON object into a Pandas dataframe. Complete the city_bikes.ipynb notebook to demonstrate how you executed the tasks above.

Part 2: Connecting to Foursquare and Yelp APIs

Your tasks are as follows:

Connect to the Foursquare API Connect to the Yelp API. This API offers similar services as Foursquare. For each of the bike stations in Part 1, query both APIs to retrieve information for the following in that location: Restaurants or bars Various POIs (points of interest) of your choice Create a DataFrame for the Yelp results and Foursquare results. Compare the quality of the Yelp and Foursquare API. For your location, which API gives you the most complete information/better coverage? NOTE: Your definition of 'coverage' is up to you. It could be simple 'number of POIs in the area', but it could also be something more specific like 'number of reviews per POI', or 'number of different attributes of each POI'. Complete the yelp_foursquare_EDA.ipynb notebook to demonstrate how you executed the tasks above.

Part 3: Joining Data

Join the data from Part 1 with the data from Part 2 to create a new dataframe. Use data visualization to explore the data. Create your own SQLite database and store the data you've collected on the POIs. Put some thought into the structure of your database. We've used and created sqlite3 databases before in the activity SQL in Python. Validate your data. Complete the joining_data.ipynb notebook to demonstrate how you executed the tasks above.

Part 4: Building a Model

Build a regression model using Python’s statsmodels module that demonstrates a relationship between the number of bikes in a particular location and the characteristics of the POIs in that location. Interpret results. Expand on the model output, and derive insights from your model. Stretch: can you think of a way to turn the above regression problem into a classification one? Without coding, can you sketch out how you would cast the problem specifically, and lay out your approaches? Complete the model_building.ipynb notebook to demonstrate how you executed the tasks above.

Results

(Fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model: The coverage that I found is that the people in NYC use citibikes quite often and for long periods at a time.)

Challenges

(Some challenges that I faced was that the Jupyter Notebook kept glitching and had to re-start kernel numerous times another issue is that creating an environment was glitching as well.)

Future Goals

(If I had more time I would spend more time on going more in-depth with cleaning data.)
