
# Observable Trends:
1) The strongest correlation is between latitude and temperature, as expected

2) The data from cloudiness from openweather appear to be often rounded to the nearest 5 or 10%

3) There is loose correlation between humidity and latitude, with higher humidity tending to be near the equator


```python
import matplotlib.pyplot as plt
from citipy import citipy
import numpy as np
import pandas as pd
import requests
from configapikey import gkey
import json
import random
import seaborn as sbn
```

# Generate 1,600 random latitudes and longitudes in attempt to disperse around globe.  1,600 is >> 500 because of duplicate nearby cities from citipy and failed api calls to openweather.


```python

LatList=random.sample(range(0, 1600), 1600)
LatList=pd.DataFrame(LatList)
for i in LatList:
    float(i)
    LatList[0]=LatList[0]*180/1600-90
LatList.rename(columns={0:'Lat'}, inplace=True)
    

LonList=random.sample(range(0, 1600), 1600)
LonList=pd.DataFrame(LonList)
for i in LonList:
    float(i)
    LonList[0]=LonList[0]*360/1600-180
LonList.rename(columns={0:'Lon'}, inplace=True)

#LatList=LatList/180
LatLon = pd.concat([LatList, LonList], axis=1)
#LatLon["City"]=""
LatLon.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-65.9250</td>
      <td>58.725</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
    </tr>
  </tbody>
</table>
</div>



# For each random lat/lon pair, find nearest city using citipy


```python
City=pd.DataFrame(index=range(0,1600),columns=['City'])

for x in range(0,1600):
    City["City"][x]= citipy.nearest_city(LatLon['Lat'][x], LatLon['Lon'][x]).city_name
LatLon = pd.concat([LatLon, City], axis=1)
LatLon.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
      <td>klaksvik</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
      <td>faanui</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-65.9250</td>
      <td>58.725</td>
      <td>taolanaro</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
      <td>hithadhoo</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
      <td>nikolskoye</td>
    </tr>
  </tbody>
</table>
</div>




```python
#  Eliminate duplicate cities

LatLon.set_index("City")
UniqueCities = LatLon.drop_duplicates(subset='City')
UniqueCities=UniqueCities.reset_index(drop=True)
UniqueCities.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
      <td>klaksvik</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
      <td>faanui</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-65.9250</td>
      <td>58.725</td>
      <td>taolanaro</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
      <td>hithadhoo</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
      <td>nikolskoye</td>
    </tr>
  </tbody>
</table>
</div>




```python
weather_json
```




    {'base': 'stations',
     'clouds': {'all': 0},
     'cod': 200,
     'coord': {'lat': 11.14, 'lon': 123.72},
     'dt': 1521526883,
     'id': 1685422,
     'main': {'grnd_level': 1022.64,
      'humidity': 100,
      'pressure': 1022.64,
      'sea_level': 1022.68,
      'temp': 82.82,
      'temp_max': 82.82,
      'temp_min': 82.82},
     'name': 'Sulangan',
     'sys': {'country': 'PH',
      'message': 0.0028,
      'sunrise': 1521496166,
      'sunset': 1521539755},
     'weather': [{'description': 'clear sky',
       'icon': '01d',
       'id': 800,
       'main': 'Clear'}],
     'wind': {'deg': 34.5016, 'speed': 7.43}}




```python
UniqueCities.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
      <td>klaksvik</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
      <td>faanui</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-65.9250</td>
      <td>58.725</td>
      <td>taolanaro</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
      <td>hithadhoo</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
      <td>nikolskoye</td>
    </tr>
  </tbody>
</table>
</div>



# Pull Data from OpenWeather, 1 City at a Time


```python
# Save config information
url = "http://api.openweathermap.org/data/2.5/weather?"




# Replace nearby Latitude with actual Latitude and get weather data
UniqueCities["LatReal"]=""
UniqueCities["Temperature"]=""
UniqueCities["Humidity"]=""
UniqueCities["Cloudiness"]=""
UniqueCities["Wind_Speed"]=""

for x in range(0,len(UniqueCities)):
    
    ThisCity=UniqueCities['City'][x]
    query_url = url + "appid=" + gkey + "&q=" + ThisCity + "&units=imperial"
    
    weather_response = requests.get(query_url)
    weather_json = weather_response.json()

   #  Bypass "city not found"    
    if weather_response.status_code==404:
        UniqueCities.loc[x,('LatReal')] = "NA"
    else: 
        UniqueCities.loc[x,('LatReal')] = weather_json['coord']['lat']
        UniqueCities.loc[x,('Temperature')] = weather_json['main']['temp']
        UniqueCities.loc[x,('Humidity')] = weather_json['main']['humidity']
        UniqueCities.loc[x,('Cloudiness')] = weather_json['clouds']['all']
        UniqueCities.loc[x,('Wind_Speed')] = weather_json['wind']['speed']
UniqueCities.head()







```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
      <th>City</th>
      <th>LatReal</th>
      <th>Temperature</th>
      <th>Humidity</th>
      <th>Cloudiness</th>
      <th>Wind_Speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
      <td>klaksvik</td>
      <td>62.23</td>
      <td>39.2</td>
      <td>98</td>
      <td>36</td>
      <td>16.11</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
      <td>faanui</td>
      <td>-16.48</td>
      <td>80.21</td>
      <td>100</td>
      <td>44</td>
      <td>17.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-65.9250</td>
      <td>58.725</td>
      <td>taolanaro</td>
      <td>NA</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
      <td>hithadhoo</td>
      <td>-0.6</td>
      <td>85.25</td>
      <td>99</td>
      <td>0</td>
      <td>13.24</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
      <td>nikolskoye</td>
      <td>59.7</td>
      <td>26.6</td>
      <td>92</td>
      <td>90</td>
      <td>8.95</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Eliminate "bad" data
UniqueCities['Humidity'].replace('', np.nan, inplace=True)
UniqueCities.dropna(subset=['Humidity'], inplace=True)
print(len(UniqueCities))

# Confirm > 500 Cities

UniqueCities.head()
```

    584
    




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lat</th>
      <th>Lon</th>
      <th>City</th>
      <th>LatReal</th>
      <th>Temperature</th>
      <th>Humidity</th>
      <th>Cloudiness</th>
      <th>Wind_Speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>69.4125</td>
      <td>-2.925</td>
      <td>klaksvik</td>
      <td>62.23</td>
      <td>39.2</td>
      <td>98.0</td>
      <td>36</td>
      <td>16.11</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-5.9625</td>
      <td>-156.825</td>
      <td>faanui</td>
      <td>-16.48</td>
      <td>80.21</td>
      <td>100.0</td>
      <td>44</td>
      <td>17.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-4.5000</td>
      <td>78.300</td>
      <td>hithadhoo</td>
      <td>-0.6</td>
      <td>85.25</td>
      <td>99.0</td>
      <td>0</td>
      <td>13.24</td>
    </tr>
    <tr>
      <th>4</th>
      <td>51.3000</td>
      <td>164.925</td>
      <td>nikolskoye</td>
      <td>59.7</td>
      <td>26.6</td>
      <td>92.0</td>
      <td>90</td>
      <td>8.95</td>
    </tr>
    <tr>
      <th>5</th>
      <td>86.4000</td>
      <td>174.825</td>
      <td>pevek</td>
      <td>69.7</td>
      <td>-16.1</td>
      <td>48.0</td>
      <td>12</td>
      <td>7.2</td>
    </tr>
  </tbody>
</table>
</div>



# Plot Temp vs. Latitude


```python
plt.title("City Latitude vs. Temperature")
plt.xlabel("City Latitude")
plt.ylabel("Temperature (Fahrenheit)")
sbn.set_style()
plt.scatter(UniqueCities['Lat'], UniqueCities['Temperature'], marker="o",facecolors="blue", edgecolors="black",)
plt.show()
plt.savefig('temperature.png')

```


![png](output_13_0.png)


# Plot Humidity vs. Latitude


```python
plt.title("City Latitude vs. Humidity")
plt.xlabel("City Latitude")
plt.ylabel("Humidity (%)")
sbn.set_style()
plt.scatter(UniqueCities['Lat'], UniqueCities['Humidity'], marker="o",facecolors="blue", edgecolors="black",)
plt.show()
plt.savefig('humidity.png')
```


![png](output_15_0.png)


# Plot Cloudiness vs. Latitude


```python
plt.title("City Latitude vs. Cloudiness")
plt.xlabel("City Latitude")
plt.ylabel("Cloudiness (%)")
sbn.set_style()
plt.scatter(UniqueCities['Lat'], UniqueCities['Cloudiness'], marker="o",facecolors="blue", edgecolors="black",)
plt.show()
plt.savefig('cloudiness.png')
```


![png](output_17_0.png)


# Plot Wind Speed vs. Latitude


```python
plt.title("City Latitude vs. Wind Speed")
plt.xlabel("City Latitude")
plt.ylabel("Wind Speed (mph)")
sbn.set_style()
plt.scatter(UniqueCities['Lat'], UniqueCities['Wind_Speed'], marker="o",facecolors="blue", edgecolors="black",)
plt.show()
plt.savefig('windspeed.png')
```


![png](output_19_0.png)



```python
UniqueCities.to_csv('CitiesData.csv')
```
