Final-Project-Statistical-Modelling-with-Python
#Project/Goals

My project goals is to determine the strength of the relationship between number of bikes + POI(characteristics)

Process
Part 1: Connecting to CityBikes API

Tasks:

1.) I had chose New York City as my city of choice and had retrieved all available bike stations in that city 2.) I had used the API to call the latitude, longitude and number of bikes for each bike station. Then I had parsed my JSON response into a Pandas dataframe which I had also converted to CSV

Part 2: Connecting to Foursquare and Yelp APIs

Tasks:

1.) I had connected to the Foursquare API + Yelp API. 2.) For each of the bike stations in Part 1, I had queried both APIs to retrieve information for Restaurants 3.) Next I had created a DataFrame for the Yelp results and Foursquare results. 4.) I prefered Yelp API as it allows customization and was easy to use

Part 3: Joining Data

Tasks:

1.) I had joined the data from Part 1 with the data from Part 2 to create a new dataframe and had also converted to csv 2.) I had then started cleaning data + EDA visualizations 3.) I had created my own SQLite database and stored the data I had collected 4.) I had also validated my data.

Part 4: Building a Model

Tasks:

1.) I had build a regression model that resembles a relationship with the number of bikes and POI(restaurants) characteristics

EDA Visualisations:
#Citybikes_heatmap sns.heatmap(data= numeric, annot=True)

#Citybikes_whiskers sns.boxplot(x=citybikes['Distance'], whis=4)

#Citybikes_violin sns.violinplot(data=citybikes, y="Number of Bikes") plt.show()

#Citybikes_boxplot plt.figure(figsize=(6.4,4.8)) #default size sns.barplot(data=citybikes, x='Ratings', y='Number of Bikes') #averages with error bars

plt.show()

#Citybikes_scatterplot plt.figure(figsize=(15,8)) sns.scatterplot(data=citybikes, x='Ratings', y='Number of Bikes', hue='Distance', size='Number of Bikes')

plt.show()

#Citybikes_pairplot fig_5=sns.pairplot(data=citybikes, kind='reg', diag_kind='kde', plot_kws={'line_kws':{'color':'green'}}) plt.show()

#Citybikes_histogram axes[0,0].hist(citybikes['Number of Bikes']) axes[0,0].set_title('[Matplotlib] Histogram of Number of Bikes')

axes[0,1].boxplot(citybikes['Ratings']) axes[0,1].set_title('[Matplotlib] Box-Plot of Ratings')

sns.histplot(ax=axes[1,0], data=citybikes, x="Distance") axes[1,0].set_title('[Seaborn] Histogram of Distance')

sns.boxplot(ax=axes[1,1], data=citybikes, y="Bike Stations") axes[1,1].set_title('[Seaborn] Box-Plot of Bike Stations')

plt.show()

#Citybikes_plotgraph2 fig_2=sns.scatterplot(data=citybikes, y ='Latitude', x ='Longitude', hue='Ratings', size='Ratings', sizes=(0, 200)) fig_2.set(title='Restaurants in New York City')

#Citybikes_plotgraph fig_1=sns.scatterplot(data=citybikes, y ='Latitude', x ='Longitude', hue='Number of Bikes', size='Number of Bikes', sizes=(0, 200)) fig_1.set(title='Available bikes in New York City')

#Citybikes_scatterplot graph sns.jointplot(data=citybikes, x="Ratings", y="Number of Bikes", height = 8 # a jointplot is a square by default ) plt.suptitle("JoinPlot Comparing Number of Bikes to Ratings", y=1)

plt.show()

#Citybikes_predictions sns.lmplot(x='POI_Count', y='Number of Bikes', data=citybikess, line_kws={'color': 'black'});

#Results

(The coverage that I found is that the people in NYC use citibikes quite often and for long periods at a time. The regression model that was built to predict number of bikes, ratings and distance is performing very well.

The low R-squared value appears to reflect that there is a weak correlation <> Coefficient: Is positive and has a positive affect on Y <> T-Statistic: Strong coefficient <> P-Value: Significance of each and is a strong coefficient)

#Challenges

(Some challenges that I faced was learning how to use API's, building a regression model as well as time was a challenge.)

#Future Goals

(If I had more time I would spend more time on going more in-depth with cleaning data and finding more POI and just adding more POI's.)
