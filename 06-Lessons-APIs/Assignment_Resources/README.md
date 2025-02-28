# Challenge Expanded Instructions

The objective of this challenge is for learners to  build on their Python API programming skills, writing input statements, decision statements, logical expressions, and use the Pandas `loc` method and `concat()` function to create marker layer and directions layer Google maps.

## Deliverable 1: Retrieve Weather Data

For the first deliverable, we are asking the learners to create a new set of 2,000 random latitudes and longitudes and get the nearest city using the `citypy` module. Using their  OpenWeatherMap API key, they'll retrieve all the weather data they retrieved in the module plus the weather description. They'll then add all the data to a DataFrame and export the DataFrame into the "Weather_Database" folder as `WeatherPy_Database.csv`.

The DataFrame should look similar to the following:

![WeatherPy Database DataFrame](WeatherPy_Database_df.png)

## Deliverable 2: Create a Customer Travel Destinations Map

For the second deliverable, the learners will need to filter the `WeatherPy_Database.csv` on the minimum and maximum temperature preferences to identify potential travel destinations. Then they'll need to find nearby hotels using the Google Maps and Places API. After they add the hotel to the DataFrame they'll export the DataFrame into the "Vacation_Search" folder as `WeatherPy_vacation.csv`, and then show those destinations on a marker layer map with pop-up markers.

For this part of the challenge we have provided [Vacation Search starter code](Vacation_Search_starter_code.ipynb) that has comments as to where the learners will need to add code to complete this part of the challenge.

The learners should be familiar with many of the steps for this part of the challenge since most of the steps have been covered in the module. After they add the hotel name to the `hotel_df` DataFrame they will need to drop the rows in the DataFrame where there is no hotel name retrieved from the Google Places API.

## Deliverable 3: Create a Travel Itinerary Map

For the third deliverable, we are asking the learners to create a travel route itinerary using the Google "Directions API". From the filtered cities in `WeatherPy_vacation.csv` file they will need to select four cities to travel to and then create a directions layer map. Then they'll to create a marker layer map with a pop-up marker for each city on the itinerary.

For this part of the challenge we have provided [Vacation Itinerary starter code](Vacation_Itinerary_starter_code.ipynb) that has comments as to where the learners will need to add code to complete this part of the challenge. Here is an overview of what they need to do:

1. The learners will need to enable the "Google Directions API" on their account before they get started.
2. In Steps 1-4, they'll need to read the `WeatherPy_vacation.csv` file into a DataFrame, then they'll create a marker layer map.
3. From the map, they'll need pick four cities, preferably in the same country, for the route.
4. In Step 5, using the variables we have provided they'll need to create four separate DataFrames using the `loc` method for each city on the travel route. The staring city will also be the ending city with three stops on the route.
5. In order to map the cities on a directions layer map, they'll have to retrieve the latitudes and longitudes from all four cities. In Step 6, they'll need to write code to retrieve the latitude-longitude pairs as tuples from each city DataFrame using the `to_numpy()` function and list indexing. We have provided a hint that shows documentation on how to use the `to_numpy()` function.
6. In Step 7, the learners will then have to use the [gmaps documentation](https://jupyter-gmaps.readthedocs.io/en/latest/tutorial.html#directions-layer) to create a directions layer map using the variables from Step 6, where the starting and ending city are the same city, the `waypoints` are the three other cities, and the `travel_mode` is either, `DRIVING`, `BICYCLING`, or `WALKING` to create the travel route.
7. In Step 8, they'll need to combine the four separate DataFrames for each city using the `concat()` function. We have provided a code snippet, `itinerary_df = pd.concat([], ignore_index=True)` and a hint that shows documentation on how to use the `concat()` function.
8. Finally, in Steps 9-11, we are asking them to create a marker layer map with a pop-up marker for each city they on the route.


