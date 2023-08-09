# python-api-challenge

### Dependencies Used:
- matplotlib.pyplot
- pandas
- numpy
- requests
- time
- json
- scipy.stats
- linregress
- hvplot.pandas
- citipy

### Description of WeatherPy

In this project I generated a list of 618 random cities. This was done by using random to generate 1500 pairs of numbers that were then used in a citipy.nearest_city to generate cities.

Open WeatherMap API was used to create a DataFrame with the location (lat, and long), Max Temp, Humidity, Cloudiness, and Wind Speed for each city, and removed any cities that didn't have that information available.

That DataFrame was used to generate graphs of Latidude compared to:
- Max Temp
- Humidity
- Cloudiness
- Wind Speed

A function ('lin_reg') was created to take two columns from the DataFrame to plot a scatter plot with a linear regression line.

Each of the graphs listed above were then plotted again for the northern and southern hemsipheres with linear regression plotted and labled.

### Discussion on findings of WeatherPy:
- It appeats that there is moderate to strong correlation between latitude of a city and the temperature
- These charts suggest that the correlation is stronger in the southern hemisphere (0.82) than in the northern (-0.58)
- In the northern hemisphere, as you go up 1 latitude you can expect there to be a .23 drop in temperature(C)
- In the southern hemishpere, as you move on latitude close to the equater, you can expect a .47 increase in temperature(C)
- There does not appear to be a correlation between a city's latitude and its humidity, Cloudiness, or Wind Speed.

### Description of VacationPy

Using the city_data_df generated in WeatherPy, a map was plotted using hvplot.points to show each city with a marker sized to the humidity of that city.

A new DataFrame was created that only included cities with ideal weather conditions:
- Temp higher that 16, lower than 30
- Humidity below 50%
- Wind Speed below 4 m/s
- Cloudiness below 50%

The Geoapify was used to find the nearest hotel to the latitude and longitude in the DataFrame. A map was plotted using hvplot.points to show each of the cities with a hover message that includes:
- Longitude
- Latitude
- Hotel Name
- City
- Country