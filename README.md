# World_Weather_Analysis# World Weather Analysis
## Project Overview
In this project, we will practice analysis, visualization, and statistical skills by retrieving and analyzing weather data for a hypothetical travel company, PlanMyTrip. 

## Resources
- Data Source: [https://openweathermap.org/api](https://openweathermap.org/api), https://console.cloud.google.com/apis 
- Software: Jupyter Notebook, Pandas Library, CityPy, Python Request, APIs, JSON Traversals, csv exporting, 

## Summary
In this projects, using API's we generated 2000 random Latitude and Longitude coordinate pairs across the world. We then found the closest city to each of those coordinate pairs. We then retrieved, collected, and cleaned weather data from each city coordinate pair. The weather data was then used to help prospective vacationers find a city and hotel that meet their weather preferences. 
We then added weather description to the weather data. Weather presences were added to identify ideal travel destinations and hotels nearby. Four cities were chosen to create a travel itinerary. Using Google Maps Directions API, a travel route was created between those four cities and a marker layer was added to the map. 

### Retrieving Weather Data
We begin our process by importing our dependencies, starting the URL for Weather Map API to make a call to it. A set of 2000 random Latitude and Longitude coordinates was created. Then a list of cities were created by using the coordinate pairs and finding the nearest city to each pair. By doing this, we found 738 cities. 
 
An empty list was created to hold weather data and then a loop was created to iterate through all the cities on the list. An API request was run to obtain City, Country, and multiple weather conditions. 
This array of dictionaries was created into a Pandas DataFrame, and then the columns were reordered. Below is the DataFrame created. We finalize the process by saving the city_data_df to csv file WeatherPy_Database.csv
 
### Creating Travel Destinations Map
For clarity purposes we created another Jupyter notebook, which we called vacation search. With it, the intend is to get the min and max temperatures, creating a range of the ideal temperature for costumers to consider their vacation plans. Once temperatures are recorded we generate a new list of cities with the temperature ranges
 
The new data set needed to be check for any missing values or nulls. In our case our dataframe did needed to be cleaned. Once we cleaned our dataframe we rearrange our columns, for readability. That cleaned DataFrame was used to create another DataFrame used to hold hotel names, city name, country, max temp, or coordinates. Using gmap API, hotels were located within 5000 meters of each city. If no hotel was located within 5000 meters, that city was skipped.
 
All rows that did not have a Hotel name were dropped. This DataFrame was then saved as a CSV file. Info box was created using html and the data from each row of the above dataframe was added to the info boxes. This allowed us to render the follow map with markers, that once clicked it would pop the name of the city, country, hotels name, current description and the max temp.
This produced the map below: 
 
### Creating a Travel Itinerary Map
Using all the information gathered above, 4 cities were selected to create an Travel Itinerary route. The loc method was utilized to create DataFrames for each of the four cities. The latitude and longitude pairs from each city were found using the "to_numpy" function. These latitude-longitude pairs were used to create a direction layer map. 
 
Info box was created to display hotel, city, country, weather description and maximum temperature. And a marker layer was created to display this information.  The result is as follow:
 

### Findings	
The project can be used for finding the ideal hotels with the right temperatures, however it does fail to become more automated since choosing the route is not automated meaning the coder needs to change the cities start and stops. Overcoming that is outside the scope of this lesson, but being to give the user more input and allowing to filter more through the data could mean true atomization and the ability for the user to really find their ideal hotels not just based on temperature, but overall weather. 
