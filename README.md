# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
(My project goals are to: 1. Connecting to CityBikes API, Step 2: Connecting to Foursquare and Yelp APIs, Part 3: Joining Data, Part 4: Building a Model)

## Process

Part 1: Connecting to CityBikes API

For this part, we will work with an API that you have not seen before: CityBikes

Citybikes is an API that provides bike sharing data for apps, research and projects. CityBikes supports more than 400 cities and the Citybikes API is an interesting dataset for building bike-sharing transportation projects.

Querries:

# Python City Bikes Scraper
#
# Simple functions to use the citybik.es API to record bike availability in a specific city.
# Settings for scrapers can be changed in lines 18-22
# 
# Built using Python 2.7
#
# Shane Lynn 24/03/2014
# @shane_a_lynn
# http://104.236.88.249
import requests
import pandas as pd
import pandas.io.sql as pdsql
from time import sleep, strftime, gmtime
import json
import sqlite3
# define the city you would like to get information from here:
# for full list see http://api.citybik.es
API_URL = "http://api.citybik.es/dublinbikes.json"
#Settings:
SAMPLE_TIME = 120                   # number of seconds between samples
SQLITE = False                      # If true - data is stored in SQLite file, if false - csv.
SQLITE_FILE = "bikedb.db"           # SQLite file to save data in
CSV_FILE = "output.csv"             # CSV file to save data in
def getAllStationDetails():
    print "\n\nScraping at " + strftime("%Y%m%d%H%M%S", gmtime())
    try:
        # this url has all the details
        decoder = json.JSONDecoder()
        station_json = requests.get(API_URL, proxies='')
        station_data = decoder.decode(station_json.content)
    except:
        print "---- FAIL ----"
        return None
    #remove unnecessary data - space saving
    # we dont need latitude and longitude
    for ii in range(0, len(station_data)):
        del station_data[ii]['lat']
        del station_data[ii]['lng']
        #del station_data[ii]['station_url']
        #del station_data[ii]['coordinates']
    print " --- SUCCESS --- "
    return station_data
def writeToCsv(data, filename="output.csv"):
    """
    Take the list of results and write as csv to filename.
    """
    data_frame = pd.DataFrame(data)
    data_frame['time'] = strftime("%Y%m%d%H%M%S", gmtime())
    data_frame.to_csv(filename, header=False, mode="a")
def writeToDb(data, db_conn):
    """
    Take the list of results and write to sqlite database
    """
    data_frame = pd.DataFrame(data)
    data_frame['scrape_time'] = strftime("%Y%m%d%H%M%S", gmtime())
    pdsql.write_frame(data_frame, "bikedata", db_conn, flavor="sqlite", if_exists="append", )
    db_conn.commit()
if __name__ == "__main__":
    # Create / connect to Sqlite3 database
    conn = sqlite3.connect(SQLITE_FILE) # or use :memory: to put it in RAM
    cursor = conn.cursor()
    # create a table to store the data
    cursor.execute("""CREATE TABLE IF NOT EXISTS bikedata
                      (name text, idx integer, timestamp text, number integer,
                       free integer, bikes integer, id integer, scrape_time text)
                   """)
    conn.commit()
    #run main function
    # we need to run the full collection, parsing, and writing every minute.
    while True:
        station_data = getAllStationDetails()
        if station_data:
            if SQLITE:
                writeToDb(station_data, conn)
            else:                
                writeToCsv(station_data, filename=CSV_FILE)
        print "Sleeping for 120 seconds."
        sleep(120)


Your tasks are as follows:

Explore the structure of the API, query the API and understand the data returned.
Choose a city covered by the CityBikes API and retrieve all available bike stations in that city.
For each bike station, use the API to call the latitude, longitude and number of bikes.
Parse the JSON object into a Pandas dataframe.
Complete the city_bikes.ipynb notebook to demonstrate how you executed the tasks above.

Part 2: Connecting to Foursquare and Yelp APIs

Your tasks are as follows:

Connect to the Foursquare API
Connect to the Yelp API. This API offers similar services as Foursquare.
For each of the bike stations in Part 1, query both APIs to retrieve information for the following in that location:
Restaurants or bars
Various POIs (points of interest) of your choice
Create a DataFrame for the Yelp results and Foursquare results.
Compare the quality of the Yelp and Foursquare API. For your location, which API gives you the most complete information/better coverage? NOTE: Your definition of 'coverage' is up to you. It could be simple 'number of POIs in the area', but it could also be something more specific like 'number of reviews per POI', or 'number of different attributes of each POI'.
Complete the yelp_foursquare_EDA.ipynb notebook to demonstrate how you executed the tasks above.

Part 3: Joining Data

Join the data from Part 1 with the data from Part 2 to create a new dataframe.
Use data visualization to explore the data.
Create your own SQLite database and store the data you've collected on the POIs. Put some thought into the structure of your database. We've used and created sqlite3 databases before in the activity SQL in Python. Validate your data.
Complete the joining_data.ipynb notebook to demonstrate how you executed the tasks above.

Part 4: Building a Model

Build a regression model using Python’s statsmodels module that demonstrates a relationship between the number of bikes in a particular location and the characteristics of the POIs in that location.
Interpret results. Expand on the model output, and derive insights from your model.
Stretch: can you think of a way to turn the above regression problem into a classification one? Without coding, can you sketch out how you would cast the problem specifically, and lay out your approaches?
Complete the model_building.ipynb notebook to demonstrate how you executed the tasks above.

## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

## Challenges 
(discuss challenges you faced in the project)

## Future Goals
(If I had more time I would spend more time on going more in-depth with cleaning data.)
