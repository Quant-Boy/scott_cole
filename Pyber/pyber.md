

```python
#Dependencies
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import seaborn as sbn


```

# Read Data Files and Change Indexes to City


```python
df_city=pd.read_csv("raw_data/city_data.csv")
df_city=df_city.set_index('city')
display(df_city)

df_ride=pd.read_csv("raw_data/ride_data.csv")
df_ride=df_ride.set_index('city')
display(df_ride)

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
      <th>driver_count</th>
      <th>type</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Kelseyland</th>
      <td>63</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>8</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>12</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>34</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>52</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>South Josephville</th>
      <td>4</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>70</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>37</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>70</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>66</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Mooreview</th>
      <td>34</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>67</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>55</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>28</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>15</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>12</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>61</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Kimberlychester</th>
      <td>13</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>67</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>46</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>7</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>11</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>42</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>31</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>41</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>70</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>47</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>60</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>64</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>69</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>58</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>9</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>55</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>26</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lake Stevenbury</th>
      <td>63</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>22</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>68</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>9</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Maryside</th>
      <td>20</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>47</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>55</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>15</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>30</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Aprilchester</th>
      <td>49</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>35</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>43</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>11</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>43</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>22</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>13</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>52</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>73</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>11</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Antoniomouth</th>
      <td>21</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>49</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>12</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>73</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>51</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>45</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>44</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>8</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>43</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>25</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>65</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>65</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Alvarezhaven</th>
      <td>21</td>
      <td>Urban</td>
    </tr>
    <tr>
      <th>Carrollbury</th>
      <td>4</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>26</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Michelleberg</th>
      <td>9</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>4</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>19</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>22</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>5</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Brandonborough</th>
      <td>9</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Floresberg</th>
      <td>7</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>24</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Kyleton</th>
      <td>12</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>1</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>9</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>8</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>16</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>27</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>18</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>20</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>15</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>16</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>13</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>25</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>14</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>9</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>10</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>21</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port Alexandria</th>
      <td>27</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>6</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>16</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>18</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Lynn</th>
      <td>20</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>11</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>13</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>17</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>3</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>26</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>26</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>26</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>21</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>North Tracyfort</th>
      <td>18</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>5</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>22</td>
      <td>Suburban</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>6</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>6</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>9</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>4</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>3</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Manuelchester</th>
      <td>7</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>6</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>10</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>6</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>9</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>10</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>8</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>5</td>
      <td>Rural</td>
    </tr>
  </tbody>
</table>
</div>



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
      <th>date</th>
      <th>fare</th>
      <th>ride_id</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Sarabury</th>
      <td>2016-01-16 13:49:27</td>
      <td>38.35</td>
      <td>5403689035038</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>2016-01-02 18:42:34</td>
      <td>17.49</td>
      <td>4036272335942</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-01-21 17:35:29</td>
      <td>44.18</td>
      <td>3645042422587</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-07-31 14:53:22</td>
      <td>6.87</td>
      <td>2242596575892</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>2016-07-09 04:42:44</td>
      <td>6.28</td>
      <td>1543057793673</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>2016-02-22 18:36:25</td>
      <td>36.01</td>
      <td>9757888452346</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-06-07 02:39:58</td>
      <td>17.15</td>
      <td>4352278259335</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-09-20 20:58:37</td>
      <td>22.98</td>
      <td>1500221409082</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>2016-01-15 17:32:02</td>
      <td>27.39</td>
      <td>850152768361</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>2016-11-16 07:27:00</td>
      <td>21.61</td>
      <td>2389035050524</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-04-11 07:20:48</td>
      <td>7.72</td>
      <td>9992929847990</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>2016-09-13 15:06:42</td>
      <td>24.89</td>
      <td>7918411468537</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-03-29 05:15:56</td>
      <td>23.88</td>
      <td>6778235889588</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>2016-09-05 05:20:39</td>
      <td>4.54</td>
      <td>9650770953139</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>2016-08-02 21:18:44</td>
      <td>12.87</td>
      <td>7994760397230</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-07-11 18:42:11</td>
      <td>39.30</td>
      <td>744481862626</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>2016-07-05 18:09:14</td>
      <td>5.82</td>
      <td>6370359473201</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>2016-11-03 01:03:05</td>
      <td>7.51</td>
      <td>4744239092530</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>2016-01-06 17:11:30</td>
      <td>8.66</td>
      <td>7298562820881</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-09-12 18:43:41</td>
      <td>26.83</td>
      <td>9304728540000</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>2016-02-27 03:55:54</td>
      <td>20.17</td>
      <td>8514523868075</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-06-12 17:01:29</td>
      <td>34.47</td>
      <td>4135673527977</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>2016-03-26 12:56:57</td>
      <td>36.43</td>
      <td>3015329826849</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>2016-08-12 11:52:41</td>
      <td>28.08</td>
      <td>133077693483</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-09-17 12:38:58</td>
      <td>38.25</td>
      <td>2182376146051</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>2016-08-23 14:49:59</td>
      <td>36.12</td>
      <td>5885997568611</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>2016-01-16 00:33:02</td>
      <td>26.62</td>
      <td>1574788996743</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>2016-06-24 20:11:11</td>
      <td>6.45</td>
      <td>1092683495142</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-01-12 20:48:43</td>
      <td>38.68</td>
      <td>5229089333754</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-10-15 05:26:40</td>
      <td>11.74</td>
      <td>8402784599831</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>2016-06-22 07:53:44</td>
      <td>39.81</td>
      <td>5322918326146</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-07-12 02:52:31</td>
      <td>31.39</td>
      <td>754749022068</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>2016-10-29 12:28:18</td>
      <td>23.50</td>
      <td>6168304478087</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>2016-08-12 17:14:50</td>
      <td>34.63</td>
      <td>6249037081192</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>2016-08-19 04:27:52</td>
      <td>5.51</td>
      <td>6246006544795</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-06-13 03:01:05</td>
      <td>25.91</td>
      <td>7414420703015</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>2016-03-22 06:49:22</td>
      <td>5.78</td>
      <td>4026457009379</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>2016-07-16 02:33:56</td>
      <td>34.69</td>
      <td>7536776262746</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-09-17 15:52:03</td>
      <td>29.95</td>
      <td>5575845447570</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>2016-12-03 08:39:02</td>
      <td>32.88</td>
      <td>7098916182845</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>2016-03-27 03:46:41</td>
      <td>6.72</td>
      <td>927702182035</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-10-01 09:57:27</td>
      <td>37.84</td>
      <td>1617736281758</td>
    </tr>
    <tr>
      <th>Aprilchester</th>
      <td>2016-05-11 07:04:30</td>
      <td>20.29</td>
      <td>1081687614611</td>
    </tr>
    <tr>
      <th>South Josephville</th>
      <td>2016-06-01 05:15:38</td>
      <td>28.33</td>
      <td>7956832876432</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-07-23 07:42:44</td>
      <td>21.76</td>
      <td>7546681945283</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>2016-10-14 00:03:21</td>
      <td>11.62</td>
      <td>8416915635572</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-08-31 20:43:30</td>
      <td>34.77</td>
      <td>2560957341604</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-10-22 13:25:30</td>
      <td>26.82</td>
      <td>3277092464967</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>2016-01-06 20:50:19</td>
      <td>34.72</td>
      <td>5731438242537</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-03-23 11:06:08</td>
      <td>9.17</td>
      <td>7823456852992</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>2016-07-08 05:37:54</td>
      <td>28.75</td>
      <td>710013110978</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-06-23 10:30:26</td>
      <td>16.24</td>
      <td>1221562985836</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>2016-06-29 21:29:33</td>
      <td>17.12</td>
      <td>1214603530980</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>2016-07-26 10:58:14</td>
      <td>19.81</td>
      <td>6337630525080</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>2016-01-03 10:46:24</td>
      <td>22.90</td>
      <td>5882538144686</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>2016-05-05 08:07:56</td>
      <td>26.50</td>
      <td>6984237224818</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>2016-08-29 18:17:56</td>
      <td>6.16</td>
      <td>209062359877</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-05-28 09:20:29</td>
      <td>35.61</td>
      <td>7474701747862</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>2016-06-05 12:00:48</td>
      <td>25.56</td>
      <td>9576410708436</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>2016-04-12 00:51:21</td>
      <td>34.59</td>
      <td>9597060126975</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>2016-04-04 10:57:33</td>
      <td>33.91</td>
      <td>7428625925530</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>2016-10-30 22:19:10</td>
      <td>8.44</td>
      <td>1130740557911</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-04-02 04:32:25</td>
      <td>38.03</td>
      <td>4932495851866</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>2016-10-05 22:23:02</td>
      <td>32.64</td>
      <td>7916984508100</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>2016-01-28 23:28:57</td>
      <td>26.61</td>
      <td>6097852530810</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-03-24 05:50:15</td>
      <td>38.73</td>
      <td>9909352484494</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-01-04 20:54:04</td>
      <td>17.10</td>
      <td>7449364616114</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-11-19 02:08:55</td>
      <td>34.47</td>
      <td>3218497808314</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>2016-06-19 05:30:03</td>
      <td>35.29</td>
      <td>319785584804</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>2016-01-06 03:50:10</td>
      <td>19.60</td>
      <td>239487697551</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>2016-02-10 05:36:14</td>
      <td>23.41</td>
      <td>397475291942</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>2016-07-24 15:18:57</td>
      <td>30.80</td>
      <td>3839329929610</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>2016-10-12 17:56:31</td>
      <td>24.65</td>
      <td>9382980155712</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>2016-08-16 23:26:16</td>
      <td>7.25</td>
      <td>1040904625038</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-01-16 18:28:03</td>
      <td>35.59</td>
      <td>7002933670322</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>2016-11-21 10:41:56</td>
      <td>26.13</td>
      <td>6513545702246</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>2016-09-08 17:46:03</td>
      <td>13.81</td>
      <td>1034339681561</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>2016-05-22 21:34:07</td>
      <td>8.83</td>
      <td>5135321621391</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>2016-08-19 03:53:38</td>
      <td>17.72</td>
      <td>1904212005602</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>2016-11-20 02:09:58</td>
      <td>6.81</td>
      <td>6512612750531</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>2016-02-02 20:46:31</td>
      <td>18.96</td>
      <td>7234982138755</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>2016-08-11 11:17:38</td>
      <td>5.97</td>
      <td>7276044030126</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-06-23 05:03:41</td>
      <td>26.82</td>
      <td>6711035373406</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>2016-10-01 19:07:00</td>
      <td>16.36</td>
      <td>8450340983211</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>2016-11-02 16:34:41</td>
      <td>15.29</td>
      <td>7136970429336</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-02-29 22:39:26</td>
      <td>15.58</td>
      <td>2605125055829</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-05-26 20:42:36</td>
      <td>12.96</td>
      <td>3749975593991</td>
    </tr>
    <tr>
      <th>Mooreview</th>
      <td>2016-05-31 13:20:24</td>
      <td>24.82</td>
      <td>9881448402158</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>2016-08-01 20:38:52</td>
      <td>34.95</td>
      <td>2258161061820</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-08-21 08:03:31</td>
      <td>15.92</td>
      <td>4308926263704</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>2016-09-20 19:27:35</td>
      <td>14.00</td>
      <td>2465241563666</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>2016-07-19 07:42:04</td>
      <td>11.24</td>
      <td>8566233760392</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>2016-09-20 02:40:41</td>
      <td>23.26</td>
      <td>825335145222</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>2016-05-24 15:47:08</td>
      <td>29.25</td>
      <td>9781946552709</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>2016-10-04 21:18:38</td>
      <td>20.62</td>
      <td>1064604032088</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>2016-01-26 13:18:17</td>
      <td>23.52</td>
      <td>1415478418209</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-11-18 15:01:25</td>
      <td>17.64</td>
      <td>8669842502879</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>2016-10-14 09:22:04</td>
      <td>33.40</td>
      <td>9894794967721</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-08-27 18:09:13</td>
      <td>22.48</td>
      <td>9410972024170</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-09-12 00:38:50</td>
      <td>20.62</td>
      <td>8634932507263</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>2016-08-12 12:15:35</td>
      <td>21.78</td>
      <td>7006435894279</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>2016-02-26 22:31:15</td>
      <td>19.52</td>
      <td>392575904754</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>2016-02-18 04:54:07</td>
      <td>7.71</td>
      <td>5375229465585</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-07-08 23:48:54</td>
      <td>31.51</td>
      <td>4504825560306</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>2016-11-08 19:22:04</td>
      <td>19.49</td>
      <td>1702803950740</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-11-26 12:07:06</td>
      <td>43.98</td>
      <td>4622629065145</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>2016-05-13 22:09:10</td>
      <td>11.30</td>
      <td>5490281721377</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>2016-10-04 21:47:13</td>
      <td>42.87</td>
      <td>3212713367333</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-06-07 18:54:40</td>
      <td>22.35</td>
      <td>7312472946247</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-06-30 23:03:42</td>
      <td>15.58</td>
      <td>2449180773119</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>2016-06-15 22:30:43</td>
      <td>20.25</td>
      <td>2462322760709</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>2016-06-17 04:23:36</td>
      <td>40.88</td>
      <td>2616108795939</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>2016-09-08 02:07:21</td>
      <td>38.81</td>
      <td>9677721784086</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-09-11 05:05:48</td>
      <td>10.05</td>
      <td>1690993450433</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>2016-03-06 18:21:13</td>
      <td>28.26</td>
      <td>3899054595030</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-01-14 06:15:56</td>
      <td>7.61</td>
      <td>9210055628598</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>2016-07-01 23:19:21</td>
      <td>5.60</td>
      <td>3234929453440</td>
    </tr>
    <tr>
      <th>Alvarezhaven</th>
      <td>2016-04-18 20:51:29</td>
      <td>31.93</td>
      <td>4267015736324</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>2016-02-04 05:21:21</td>
      <td>32.23</td>
      <td>5464913219631</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-08-22 06:59:40</td>
      <td>43.14</td>
      <td>5027353344310</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-10-29 19:14:58</td>
      <td>13.85</td>
      <td>8841221112569</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>2016-04-02 13:49:14</td>
      <td>28.17</td>
      <td>3800595642657</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>2016-04-17 06:59:50</td>
      <td>5.54</td>
      <td>7466473222333</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-04-26 16:06:26</td>
      <td>30.35</td>
      <td>8277767411680</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>2016-06-08 06:50:52</td>
      <td>22.13</td>
      <td>8737367087802</td>
    </tr>
    <tr>
      <th>Alvarezhaven</th>
      <td>2016-08-01 00:39:48</td>
      <td>6.42</td>
      <td>8394540350728</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>2016-01-11 14:29:59</td>
      <td>10.13</td>
      <td>60400779470</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-09-30 12:48:34</td>
      <td>30.30</td>
      <td>6388737278232</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>2016-07-03 17:13:53</td>
      <td>32.91</td>
      <td>1045867165508</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>2016-06-12 21:55:26</td>
      <td>15.68</td>
      <td>6360386076803</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-12-04 12:34:11</td>
      <td>17.25</td>
      <td>3972159758798</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-08-11 12:33:41</td>
      <td>12.76</td>
      <td>452574991633</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>2016-03-19 13:08:09</td>
      <td>35.07</td>
      <td>9198401002936</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-04-29 20:53:30</td>
      <td>19.77</td>
      <td>44295036528</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>2016-06-01 01:49:06</td>
      <td>31.05</td>
      <td>308132266739</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>2016-08-07 11:22:14</td>
      <td>35.99</td>
      <td>8759291063608</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-04-26 03:20:31</td>
      <td>17.22</td>
      <td>7893586299172</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>2016-04-01 04:46:39</td>
      <td>13.17</td>
      <td>2912135299250</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>2016-01-25 13:57:53</td>
      <td>27.53</td>
      <td>5400221539672</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>2016-06-07 07:40:57</td>
      <td>16.54</td>
      <td>9656275609373</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>2016-06-12 10:31:30</td>
      <td>38.40</td>
      <td>2185801400452</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>2016-03-01 19:20:31</td>
      <td>33.99</td>
      <td>3329473853492</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>2016-10-16 09:38:42</td>
      <td>5.07</td>
      <td>3086950951569</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>2016-11-26 13:24:34</td>
      <td>44.48</td>
      <td>8256626498055</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>2016-10-03 05:05:10</td>
      <td>20.30</td>
      <td>9267605063828</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-06-14 16:52:30</td>
      <td>8.58</td>
      <td>8124141597846</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>2016-01-02 18:46:46</td>
      <td>40.84</td>
      <td>3714119486484</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>2016-07-12 02:19:07</td>
      <td>44.39</td>
      <td>8861487145996</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>2016-07-26 16:34:27</td>
      <td>33.19</td>
      <td>6568406414554</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>2016-06-07 02:32:33</td>
      <td>27.05</td>
      <td>1007050766497</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>2016-02-05 02:25:34</td>
      <td>37.01</td>
      <td>4010739308021</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>2016-10-18 23:07:01</td>
      <td>27.41</td>
      <td>4273352984502</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>2016-10-16 19:55:33</td>
      <td>25.52</td>
      <td>2615527029618</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-08-29 05:21:28</td>
      <td>7.69</td>
      <td>7920890699425</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-05-29 22:39:17</td>
      <td>39.36</td>
      <td>4912899618265</td>
    </tr>
    <tr>
      <th>Alvarezhaven</th>
      <td>2016-09-01 22:57:12</td>
      <td>18.09</td>
      <td>1197329964911</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>2016-02-03 14:17:58</td>
      <td>13.15</td>
      <td>3249005020508</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-03-29 20:04:52</td>
      <td>32.63</td>
      <td>8172040679569</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>2016-10-04 10:31:59</td>
      <td>32.35</td>
      <td>3963883373388</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>2016-10-07 11:09:50</td>
      <td>25.19</td>
      <td>7709877217148</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-08-04 00:25:52</td>
      <td>27.20</td>
      <td>2429366407526</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-01-17 07:11:21</td>
      <td>21.03</td>
      <td>3138020890244</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-02-14 02:12:58</td>
      <td>34.20</td>
      <td>5949268564952</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>2016-05-04 15:06:07</td>
      <td>30.54</td>
      <td>2140501382736</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>2016-07-20 23:09:53</td>
      <td>13.62</td>
      <td>3418054971844</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>2016-06-11 21:01:35</td>
      <td>27.66</td>
      <td>6959463827218</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-04-10 15:48:48</td>
      <td>38.54</td>
      <td>7589586454429</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>2016-05-21 13:23:13</td>
      <td>35.10</td>
      <td>2651836106343</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-03-13 23:58:48</td>
      <td>13.72</td>
      <td>3114245954411</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-10-20 08:38:04</td>
      <td>9.85</td>
      <td>956191227071</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>2016-01-19 01:06:19</td>
      <td>10.11</td>
      <td>7226694900591</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>2016-01-25 20:44:56</td>
      <td>12.08</td>
      <td>1896987891309</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-10-27 13:17:27</td>
      <td>37.12</td>
      <td>3869246419390</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>2016-08-05 05:51:10</td>
      <td>43.57</td>
      <td>1405839416890</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>2016-01-30 07:31:03</td>
      <td>34.93</td>
      <td>6848867019018</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>2016-02-08 03:40:56</td>
      <td>23.20</td>
      <td>2168468041107</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>2016-09-18 18:24:17</td>
      <td>19.67</td>
      <td>2851656538564</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>2016-09-16 03:21:55</td>
      <td>40.56</td>
      <td>2942923988585</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>2016-08-05 08:01:53</td>
      <td>17.80</td>
      <td>6636226910096</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-10-01 19:56:45</td>
      <td>11.43</td>
      <td>6593096228570</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>2016-08-25 21:23:25</td>
      <td>15.40</td>
      <td>4382199002444</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-03-29 09:41:20</td>
      <td>24.47</td>
      <td>8594133966682</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>2016-05-10 04:55:12</td>
      <td>5.13</td>
      <td>3220127429066</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>2016-08-06 19:00:42</td>
      <td>16.35</td>
      <td>2843507224931</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>2016-01-18 17:58:19</td>
      <td>23.56</td>
      <td>7950685654605</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>2016-06-16 10:11:35</td>
      <td>13.25</td>
      <td>1348406500045</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>2016-10-06 18:54:55</td>
      <td>36.97</td>
      <td>9199037124955</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-08-23 23:45:29</td>
      <td>23.05</td>
      <td>4340058285247</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>2016-03-07 22:54:10</td>
      <td>16.40</td>
      <td>2234985643749</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-07-19 12:38:21</td>
      <td>43.64</td>
      <td>9414931729816</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-05-29 13:39:18</td>
      <td>16.00</td>
      <td>9147017027284</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>2016-01-03 11:35:45</td>
      <td>6.69</td>
      <td>7455207171412</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-05-09 01:35:14</td>
      <td>17.56</td>
      <td>2796711976151</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>2016-02-27 23:17:20</td>
      <td>20.30</td>
      <td>154182897351</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>2016-11-22 21:50:07</td>
      <td>11.74</td>
      <td>3338056080828</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>2016-04-20 15:42:03</td>
      <td>27.26</td>
      <td>7924974337784</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>2016-10-19 20:25:16</td>
      <td>28.18</td>
      <td>6204409645686</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>2016-05-22 05:49:44</td>
      <td>25.10</td>
      <td>9598588567912</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-03-27 09:25:01</td>
      <td>21.18</td>
      <td>105529334350</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>2016-10-26 09:01:30</td>
      <td>9.48</td>
      <td>8359941011708</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>2016-07-15 15:36:30</td>
      <td>12.65</td>
      <td>3065372869423</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>2016-07-14 14:58:39</td>
      <td>7.22</td>
      <td>3428800534766</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-05-26 05:12:55</td>
      <td>40.24</td>
      <td>2895967596189</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>2016-07-27 16:58:49</td>
      <td>38.30</td>
      <td>257500253836</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-07-12 04:33:22</td>
      <td>30.88</td>
      <td>564769023118</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-01-02 02:30:39</td>
      <td>18.51</td>
      <td>4484116538552</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-01-12 01:10:56</td>
      <td>35.07</td>
      <td>9029197394649</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>2016-09-25 16:35:54</td>
      <td>22.28</td>
      <td>9242784905015</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>2016-07-05 13:53:10</td>
      <td>35.82</td>
      <td>5594924751117</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-09-26 10:18:39</td>
      <td>33.45</td>
      <td>8539342573320</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>2016-03-12 13:26:42</td>
      <td>10.61</td>
      <td>6544353421920</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>2016-03-08 05:38:56</td>
      <td>16.34</td>
      <td>4824338773568</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>2016-11-28 01:14:54</td>
      <td>33.11</td>
      <td>231866596752</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>2016-09-03 02:23:56</td>
      <td>22.86</td>
      <td>8393534675892</td>
    </tr>
    <tr>
      <th>Maryside</th>
      <td>2016-07-20 01:03:51</td>
      <td>14.07</td>
      <td>987385552129</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>2016-06-28 16:34:41</td>
      <td>12.92</td>
      <td>5992374822461</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-07-25 10:44:01</td>
      <td>17.73</td>
      <td>4467299640441</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>2016-05-05 21:32:36</td>
      <td>4.54</td>
      <td>2443254047182</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-02-07 05:19:26</td>
      <td>23.44</td>
      <td>2983583783981</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-03-31 01:06:39</td>
      <td>32.58</td>
      <td>7973806871682</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>2016-02-22 12:18:36</td>
      <td>25.21</td>
      <td>9932058462800</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>2016-09-22 23:20:26</td>
      <td>23.34</td>
      <td>9218804614069</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>2016-07-20 22:47:27</td>
      <td>8.73</td>
      <td>2796624267728</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>2016-04-10 11:11:22</td>
      <td>4.36</td>
      <td>74296958741</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>2016-11-18 17:37:57</td>
      <td>5.10</td>
      <td>9084182452384</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>2016-03-20 00:51:56</td>
      <td>38.49</td>
      <td>1577200130190</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-10-20 18:30:59</td>
      <td>5.48</td>
      <td>5201786146257</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>2016-05-16 15:36:19</td>
      <td>9.15</td>
      <td>5125461669650</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>2016-04-14 03:24:49</td>
      <td>9.77</td>
      <td>664212477922</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>2016-07-20 15:44:50</td>
      <td>21.57</td>
      <td>8210929698932</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-01-30 04:01:09</td>
      <td>6.28</td>
      <td>1190676544959</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>2016-05-17 08:07:38</td>
      <td>21.40</td>
      <td>644161168324</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>2016-10-13 23:41:18</td>
      <td>10.56</td>
      <td>2833681147171</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>2016-11-18 12:47:21</td>
      <td>4.92</td>
      <td>8534735733800</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>2016-10-14 12:46:35</td>
      <td>30.17</td>
      <td>8693419258883</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>2016-09-11 15:12:15</td>
      <td>22.16</td>
      <td>2625948382445</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>2016-03-03 08:04:55</td>
      <td>11.95</td>
      <td>9675758344587</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>2016-09-29 11:48:24</td>
      <td>35.67</td>
      <td>9849036104754</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>2016-05-12 15:57:15</td>
      <td>41.63</td>
      <td>224683791660</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>2016-06-22 16:24:01</td>
      <td>23.94</td>
      <td>6153395712431</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>2016-11-27 18:13:47</td>
      <td>16.04</td>
      <td>7446936449859</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>2016-02-29 19:08:06</td>
      <td>41.18</td>
      <td>592689263451</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>2016-02-03 07:47:55</td>
      <td>14.78</td>
      <td>8863628427671</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>2016-09-18 11:54:02</td>
      <td>23.41</td>
      <td>3915848678847</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>2016-04-16 11:09:22</td>
      <td>7.43</td>
      <td>5771727115432</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>2016-08-25 04:25:38</td>
      <td>4.27</td>
      <td>6739162487056</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>2016-02-23 02:21:54</td>
      <td>4.06</td>
      <td>5772409201337</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>2016-07-28 11:27:00</td>
      <td>40.77</td>
      <td>489025361264</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>2016-07-01 22:39:48</td>
      <td>34.02</td>
      <td>3643931487976</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>2016-03-14 19:58:33</td>
      <td>36.95</td>
      <td>6369117726062</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>2016-08-10 00:56:27</td>
      <td>43.17</td>
      <td>3214638737567</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>2016-07-17 16:27:49</td>
      <td>46.96</td>
      <td>7239195028961</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>2016-06-07 02:40:22</td>
      <td>35.32</td>
      <td>3720394047456</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-10-29 14:09:31</td>
      <td>19.01</td>
      <td>8482529942368</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>2016-11-30 20:07:05</td>
      <td>48.45</td>
      <td>8995803338738</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>2016-07-12 23:20:30</td>
      <td>28.71</td>
      <td>4681889328162</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>2016-11-02 22:40:30</td>
      <td>13.68</td>
      <td>7462937892494</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>2016-10-26 02:21:34</td>
      <td>29.03</td>
      <td>568812204547</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>2016-04-03 12:43:43</td>
      <td>41.87</td>
      <td>6921665148781</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>2016-05-05 11:25:25</td>
      <td>45.93</td>
      <td>7681604268404</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-06-27 15:54:38</td>
      <td>30.90</td>
      <td>9364933227561</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>2016-02-03 15:50:57</td>
      <td>17.57</td>
      <td>2238752751</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>2016-02-15 12:08:12</td>
      <td>47.04</td>
      <td>7838669752717</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>2016-11-09 19:10:25</td>
      <td>17.75</td>
      <td>172157590687</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-03-19 01:56:46</td>
      <td>21.92</td>
      <td>1982991238954</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>2016-07-02 03:44:09</td>
      <td>14.90</td>
      <td>8469790600203</td>
    </tr>
    <tr>
      <th>New Lynn</th>
      <td>2016-10-31 10:33:55</td>
      <td>17.89</td>
      <td>7106182911035</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>2016-02-06 01:24:57</td>
      <td>15.67</td>
      <td>3449564026717</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-10-07 21:10:22</td>
      <td>35.70</td>
      <td>3440594061846</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-09-30 00:18:46</td>
      <td>38.76</td>
      <td>2948110877038</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>2016-10-13 06:40:10</td>
      <td>37.05</td>
      <td>2718293829861</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>2016-01-26 07:27:21</td>
      <td>36.73</td>
      <td>6513765504538</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-06-24 20:00:42</td>
      <td>36.29</td>
      <td>7629110609205</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>2016-07-14 16:11:11</td>
      <td>48.93</td>
      <td>7745514475878</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>2016-05-31 09:14:14</td>
      <td>20.15</td>
      <td>3046318756120</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-05-18 16:18:03</td>
      <td>39.17</td>
      <td>820574534622</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>2016-10-19 22:48:45</td>
      <td>19.45</td>
      <td>9696914665100</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>2016-08-31 17:17:43</td>
      <td>16.34</td>
      <td>3262136578014</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>2016-05-28 07:21:44</td>
      <td>15.49</td>
      <td>2838087595946</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>2016-09-28 05:16:26</td>
      <td>42.58</td>
      <td>5687344816686</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>2016-11-03 20:05:04</td>
      <td>26.06</td>
      <td>4691824954233</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>2016-06-26 16:45:40</td>
      <td>35.04</td>
      <td>4101286981895</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>2016-04-18 07:32:21</td>
      <td>46.26</td>
      <td>4170471527972</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-05-30 17:10:29</td>
      <td>16.57</td>
      <td>4365273051347</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>2016-04-11 14:22:29</td>
      <td>34.31</td>
      <td>5735333103412</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-05-09 20:44:30</td>
      <td>25.02</td>
      <td>5180084863014</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>2016-07-19 11:48:25</td>
      <td>25.28</td>
      <td>5545096368412</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>2016-02-25 20:39:21</td>
      <td>20.55</td>
      <td>1952715136422</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>2016-09-23 16:13:17</td>
      <td>25.78</td>
      <td>7225493243908</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-02-13 08:59:15</td>
      <td>17.95</td>
      <td>7707934263299</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>2016-05-20 07:48:29</td>
      <td>19.43</td>
      <td>4247411080238</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-02-05 10:51:18</td>
      <td>29.74</td>
      <td>9506460250524</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>2016-05-23 15:09:27</td>
      <td>21.70</td>
      <td>7362542792786</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-07-02 00:26:53</td>
      <td>49.95</td>
      <td>7153762992366</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-08-31 21:49:33</td>
      <td>18.46</td>
      <td>5678403186406</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>2016-08-15 22:27:38</td>
      <td>22.95</td>
      <td>7917780105807</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>2016-07-26 14:43:53</td>
      <td>14.98</td>
      <td>9736030276740</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>2016-04-30 08:52:01</td>
      <td>45.36</td>
      <td>4625917076816</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>2016-01-23 18:52:27</td>
      <td>38.30</td>
      <td>8533541191606</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>2016-01-06 08:35:46</td>
      <td>48.39</td>
      <td>9067527240907</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>2016-11-17 04:32:08</td>
      <td>14.08</td>
      <td>7746790862079</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-01-12 14:36:00</td>
      <td>30.04</td>
      <td>2292425164476</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>2016-02-10 08:01:22</td>
      <td>42.62</td>
      <td>520744463270</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-07-07 11:44:06</td>
      <td>29.38</td>
      <td>4313739296320</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>2016-11-09 15:45:56</td>
      <td>43.72</td>
      <td>8103943152521</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>2016-06-02 06:42:46</td>
      <td>23.58</td>
      <td>5550577665799</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>2016-04-29 21:46:58</td>
      <td>33.34</td>
      <td>2084175895874</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>2016-04-15 13:57:39</td>
      <td>49.20</td>
      <td>5356741485558</td>
    </tr>
    <tr>
      <th>Floresberg</th>
      <td>2016-11-06 05:10:52</td>
      <td>41.50</td>
      <td>502047327282</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>2016-07-09 09:05:03</td>
      <td>23.35</td>
      <td>8198565947587</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>2016-11-20 11:01:27</td>
      <td>15.54</td>
      <td>6377267655644</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>2016-10-23 19:21:00</td>
      <td>32.76</td>
      <td>1154850634331</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>2016-06-07 10:59:44</td>
      <td>44.39</td>
      <td>6958569707509</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-10-16 03:24:03</td>
      <td>30.95</td>
      <td>8903442044811</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>2016-06-25 20:08:16</td>
      <td>37.10</td>
      <td>1275710680951</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>2016-07-26 15:41:29</td>
      <td>21.10</td>
      <td>1859961459728</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>2016-09-02 20:49:53</td>
      <td>29.91</td>
      <td>4571645215747</td>
    </tr>
    <tr>
      <th>New Michelleberg</th>
      <td>2016-08-01 12:29:19</td>
      <td>38.77</td>
      <td>8188679960565</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>2016-03-12 05:45:40</td>
      <td>44.37</td>
      <td>4341000080149</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-10-30 20:31:41</td>
      <td>24.27</td>
      <td>2755333176738</td>
    </tr>
    <tr>
      <th>North Tracyfort</th>
      <td>2016-01-21 22:58:39</td>
      <td>49.20</td>
      <td>8858130821345</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>2016-04-12 15:15:17</td>
      <td>18.26</td>
      <td>9193824203632</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>2016-04-21 13:16:48</td>
      <td>17.43</td>
      <td>1036264344283</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-01-07 04:23:50</td>
      <td>12.82</td>
      <td>6638603885492</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-05-09 23:34:49</td>
      <td>36.82</td>
      <td>4134621753765</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-06-24 00:33:52</td>
      <td>38.59</td>
      <td>5542622996828</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>2016-07-01 12:54:56</td>
      <td>21.83</td>
      <td>715134404609</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>2016-08-12 13:46:10</td>
      <td>36.19</td>
      <td>503643402298</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>2016-10-05 10:21:54</td>
      <td>45.47</td>
      <td>7308711145137</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-02-27 07:42:17</td>
      <td>30.47</td>
      <td>421686911259</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>2016-09-29 18:39:16</td>
      <td>32.93</td>
      <td>8560812007694</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>2016-11-13 12:08:17</td>
      <td>23.24</td>
      <td>4348021999986</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>2016-08-29 19:51:11</td>
      <td>26.36</td>
      <td>641341897487</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-07-19 14:20:26</td>
      <td>30.24</td>
      <td>6872721534416</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>2016-10-26 13:51:36</td>
      <td>46.16</td>
      <td>1378647556556</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>2016-01-25 17:39:01</td>
      <td>21.10</td>
      <td>6426838853122</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>2016-03-07 08:51:17</td>
      <td>24.26</td>
      <td>623481159694</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>2016-05-30 02:40:38</td>
      <td>28.00</td>
      <td>9142221889864</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>2016-01-19 12:40:19</td>
      <td>29.08</td>
      <td>3261020829294</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-03-16 10:58:26</td>
      <td>14.90</td>
      <td>8175931855295</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>2016-03-09 20:08:51</td>
      <td>44.62</td>
      <td>1689521191238</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>2016-04-02 18:40:05</td>
      <td>25.67</td>
      <td>9947857222852</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>2016-03-06 06:47:59</td>
      <td>39.15</td>
      <td>6580337521064</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>2016-01-02 16:24:54</td>
      <td>22.59</td>
      <td>3598172235339</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>2016-09-12 04:03:15</td>
      <td>24.15</td>
      <td>7088674842808</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>2016-03-17 08:21:55</td>
      <td>21.95</td>
      <td>3863083046542</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>2016-07-26 22:43:47</td>
      <td>21.61</td>
      <td>906508038494</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>2016-03-25 00:12:36</td>
      <td>21.08</td>
      <td>8297446071998</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-10-23 20:30:26</td>
      <td>19.91</td>
      <td>3559113387760</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>2016-07-26 01:44:46</td>
      <td>46.71</td>
      <td>9936536228476</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>2016-06-23 03:43:13</td>
      <td>49.24</td>
      <td>9932335592589</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>2016-07-04 13:31:18</td>
      <td>23.50</td>
      <td>3602696796266</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>2016-04-11 09:46:48</td>
      <td>28.66</td>
      <td>8222557011922</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>2016-04-14 19:45:45</td>
      <td>38.26</td>
      <td>4124017812046</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>2016-05-15 09:40:27</td>
      <td>40.02</td>
      <td>6407619626296</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>2016-10-02 08:26:34</td>
      <td>19.26</td>
      <td>4159099493050</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>2016-03-22 22:20:01</td>
      <td>33.36</td>
      <td>9782668221379</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>2016-01-06 07:02:48</td>
      <td>12.22</td>
      <td>5607242791342</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>2016-10-23 19:06:23</td>
      <td>23.06</td>
      <td>3922898108538</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>2016-01-28 21:29:29</td>
      <td>25.43</td>
      <td>5273736332355</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>2016-08-29 19:22:52</td>
      <td>18.75</td>
      <td>9976923455740</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>2016-11-10 20:28:12</td>
      <td>23.25</td>
      <td>8032749449163</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>2016-08-31 16:49:37</td>
      <td>19.95</td>
      <td>3362713962981</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-09-14 06:44:17</td>
      <td>44.15</td>
      <td>243886776311</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>2016-11-05 00:11:09</td>
      <td>20.57</td>
      <td>6852219007554</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>2016-05-17 08:21:05</td>
      <td>37.59</td>
      <td>5545308851404</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>2016-10-18 19:48:10</td>
      <td>26.75</td>
      <td>7553206322344</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>2016-01-03 16:21:55</td>
      <td>35.59</td>
      <td>1509231568529</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>2016-09-25 21:33:40</td>
      <td>18.89</td>
      <td>3474570518178</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>2016-06-11 19:21:00</td>
      <td>32.78</td>
      <td>8947216476408</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>2016-11-27 07:42:07</td>
      <td>12.83</td>
      <td>1139750594022</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>2016-11-26 10:45:05</td>
      <td>49.36</td>
      <td>1790101950968</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>2016-06-17 11:20:35</td>
      <td>14.84</td>
      <td>6611757009662</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>2016-05-12 21:57:46</td>
      <td>24.89</td>
      <td>3648265749196</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>2016-08-19 09:15:43</td>
      <td>17.22</td>
      <td>9307594888276</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>2016-07-19 10:07:33</td>
      <td>12.63</td>
      <td>8214498891817</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-05-18 23:28:12</td>
      <td>20.53</td>
      <td>6432117120069</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>2016-04-21 08:30:25</td>
      <td>56.60</td>
      <td>9002881309143</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-02-17 01:41:29</td>
      <td>57.52</td>
      <td>7365786843443</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-10-19 13:13:17</td>
      <td>24.43</td>
      <td>2728236352387</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-02-16 11:58:06</td>
      <td>22.43</td>
      <td>8118042484039</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>2016-02-14 15:52:14</td>
      <td>22.20</td>
      <td>341262393081</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-11-27 20:12:58</td>
      <td>12.92</td>
      <td>6460741616450</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-02-21 06:07:18</td>
      <td>45.12</td>
      <td>1607319707836</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-01-01 18:05:56</td>
      <td>11.76</td>
      <td>3568184448232</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-02-20 08:17:32</td>
      <td>58.95</td>
      <td>3176534714830</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-10-09 02:18:33</td>
      <td>10.33</td>
      <td>1819118738960</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-04-21 18:44:59</td>
      <td>19.26</td>
      <td>5836114186294</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>2016-03-22 21:22:20</td>
      <td>31.53</td>
      <td>1797785685674</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>2016-07-25 19:05:05</td>
      <td>24.03</td>
      <td>8781417245667</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-07-27 09:55:18</td>
      <td>41.64</td>
      <td>3154261826545</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-04-01 21:21:37</td>
      <td>51.01</td>
      <td>612689673941</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-04-13 04:30:56</td>
      <td>40.47</td>
      <td>7075058703398</td>
    </tr>
    <tr>
      <th>Manuelchester</th>
      <td>2016-03-21 22:15:25</td>
      <td>49.62</td>
      <td>6045427401799</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-04-12 00:21:43</td>
      <td>56.07</td>
      <td>7011959069461</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-04-26 09:35:48</td>
      <td>42.09</td>
      <td>9465134041656</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-08-15 14:54:05</td>
      <td>54.73</td>
      <td>9861677486822</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-04-26 02:34:30</td>
      <td>45.80</td>
      <td>9402873395510</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-06-26 20:11:50</td>
      <td>28.78</td>
      <td>6382848462030</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-07-11 01:21:31</td>
      <td>41.86</td>
      <td>1023430862078</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-03-04 10:49:25</td>
      <td>35.77</td>
      <td>9725377510815</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-10-01 06:32:37</td>
      <td>25.18</td>
      <td>5044558212428</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-04-05 18:53:16</td>
      <td>44.78</td>
      <td>6113138249150</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-02-19 01:42:58</td>
      <td>11.15</td>
      <td>8622534016726</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-05-24 15:29:59</td>
      <td>18.11</td>
      <td>1144791937271</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-02-10 11:22:03</td>
      <td>44.02</td>
      <td>225335802727</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-11-19 04:47:01</td>
      <td>43.84</td>
      <td>7366535419230</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-03-11 09:03:43</td>
      <td>42.13</td>
      <td>4568909568268</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-06-01 19:02:55</td>
      <td>29.88</td>
      <td>9429195617069</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-06-24 21:09:09</td>
      <td>50.03</td>
      <td>9224879345166</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-10-17 14:47:38</td>
      <td>53.42</td>
      <td>8515375903761</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-02-10 04:40:32</td>
      <td>38.98</td>
      <td>4404175884957</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-10-24 13:55:09</td>
      <td>29.51</td>
      <td>7225032916195</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-01-24 00:21:35</td>
      <td>30.32</td>
      <td>7342649945759</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>2016-01-26 09:38:17</td>
      <td>21.73</td>
      <td>5665544449606</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-11-13 10:21:10</td>
      <td>15.71</td>
      <td>7275986542384</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-06-10 18:27:03</td>
      <td>29.25</td>
      <td>4071225680519</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-01-09 01:11:17</td>
      <td>50.43</td>
      <td>9888063516963</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-11-21 05:16:26</td>
      <td>56.41</td>
      <td>1763715882352</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-05-23 12:55:48</td>
      <td>48.49</td>
      <td>9985496304508</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>2016-04-03 11:13:07</td>
      <td>22.79</td>
      <td>8193837300497</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-03-05 10:40:16</td>
      <td>23.35</td>
      <td>7443355895137</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-03-06 06:10:40</td>
      <td>51.32</td>
      <td>6841691147797</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-01-06 13:25:48</td>
      <td>59.53</td>
      <td>5277708038641</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-04-19 06:56:29</td>
      <td>26.40</td>
      <td>8819643364798</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-09-30 12:57:33</td>
      <td>58.45</td>
      <td>2786024888524</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-02-03 21:31:31</td>
      <td>46.32</td>
      <td>2945397874811</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-03-04 10:18:03</td>
      <td>13.43</td>
      <td>8814831098684</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-11-15 18:10:42</td>
      <td>34.73</td>
      <td>2872259802463</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-02-26 06:13:28</td>
      <td>29.15</td>
      <td>7556363986770</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>2016-03-11 12:27:01</td>
      <td>26.72</td>
      <td>4943246873754</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-02-15 02:35:41</td>
      <td>39.18</td>
      <td>2125908491083</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-03-23 17:37:13</td>
      <td>28.13</td>
      <td>5544477192400</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-06-25 08:04:12</td>
      <td>24.53</td>
      <td>8188407925972</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-08-24 01:16:18</td>
      <td>39.71</td>
      <td>4855991750139</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-04-11 04:44:50</td>
      <td>10.41</td>
      <td>9823290002445</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-11-28 09:09:15</td>
      <td>37.76</td>
      <td>804829686137</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-02-29 07:26:19</td>
      <td>14.01</td>
      <td>6867080292206</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-02-29 21:50:59</td>
      <td>47.48</td>
      <td>12105457917</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-04-21 19:22:03</td>
      <td>37.19</td>
      <td>5142074323359</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-02-21 18:20:14</td>
      <td>42.01</td>
      <td>3306522110065</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-06-26 11:16:28</td>
      <td>26.29</td>
      <td>304182959218</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-02-24 07:17:34</td>
      <td>43.15</td>
      <td>1177421944004</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-09-08 19:19:38</td>
      <td>30.59</td>
      <td>8211833105097</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-06-09 23:01:40</td>
      <td>24.63</td>
      <td>978305304720</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-11-14 10:46:11</td>
      <td>55.07</td>
      <td>8000095653619</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-08-24 23:19:15</td>
      <td>40.57</td>
      <td>4362092657873</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>2016-10-30 16:24:21</td>
      <td>22.81</td>
      <td>3116198466324</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-07-01 12:48:05</td>
      <td>12.88</td>
      <td>5989452220219</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>2016-02-23 17:46:29</td>
      <td>59.65</td>
      <td>241191157535</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-04-16 01:37:27</td>
      <td>26.60</td>
      <td>2964889579584</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-11-25 20:34:14</td>
      <td>38.45</td>
      <td>2898512024847</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-07-24 13:41:23</td>
      <td>11.78</td>
      <td>2001192693573</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-01-18 07:11:45</td>
      <td>10.66</td>
      <td>9287766069118</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-11-20 17:32:37</td>
      <td>26.79</td>
      <td>3095402154397</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-03-02 22:09:34</td>
      <td>36.61</td>
      <td>5500269118478</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-11-28 05:51:38</td>
      <td>23.38</td>
      <td>6392257942917</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-01-24 09:14:51</td>
      <td>24.37</td>
      <td>7069044920500</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-03-22 18:04:29</td>
      <td>25.67</td>
      <td>1480709392474</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-03-22 12:38:48</td>
      <td>36.54</td>
      <td>7210244842844</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-06-28 07:08:14</td>
      <td>51.09</td>
      <td>3151357214095</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>2016-05-11 12:08:25</td>
      <td>41.83</td>
      <td>1591306474620</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-03-14 01:46:10</td>
      <td>30.59</td>
      <td>9121141930245</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>2016-05-03 04:52:29</td>
      <td>40.71</td>
      <td>2918447130656</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-10-08 02:37:31</td>
      <td>19.21</td>
      <td>7539237840408</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>2016-10-13 03:36:59</td>
      <td>52.99</td>
      <td>9771737428375</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-03-24 10:27:00</td>
      <td>29.72</td>
      <td>3818227780479</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-06-12 16:57:25</td>
      <td>30.18</td>
      <td>2015025942653</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-07-13 18:13:46</td>
      <td>59.64</td>
      <td>1666847044707</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-07-22 05:59:01</td>
      <td>10.64</td>
      <td>1406024986969</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-06-15 19:53:16</td>
      <td>13.50</td>
      <td>9577921579881</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>2016-02-23 00:43:51</td>
      <td>40.84</td>
      <td>8665248512368</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-11-26 04:39:52</td>
      <td>44.21</td>
      <td>9598643212986</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>2016-07-23 08:23:50</td>
      <td>46.08</td>
      <td>8440329717166</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>2016-02-24 17:30:44</td>
      <td>44.68</td>
      <td>6389115653382</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-01-01 04:31:43</td>
      <td>33.53</td>
      <td>5149088250183</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>2016-02-22 02:45:07</td>
      <td>19.91</td>
      <td>808097865942</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>2016-11-23 07:47:18</td>
      <td>46.39</td>
      <td>1939838068038</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>2016-07-30 21:25:01</td>
      <td>35.39</td>
      <td>1107870956099</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-10-01 13:41:00</td>
      <td>34.17</td>
      <td>7750597960630</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-04-30 20:44:27</td>
      <td>23.58</td>
      <td>4524301143267</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>2016-03-25 02:05:42</td>
      <td>20.04</td>
      <td>5729327140644</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>2016-01-25 01:39:16</td>
      <td>59.43</td>
      <td>8088329954312</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>2016-08-03 21:19:11</td>
      <td>47.67</td>
      <td>9201708664049</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-11-19 06:59:31</td>
      <td>18.37</td>
      <td>5897895798960</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>2016-10-20 16:42:54</td>
      <td>37.75</td>
      <td>4356781814784</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-10-15 03:53:06</td>
      <td>32.50</td>
      <td>2758038144583</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>2016-05-18 02:00:30</td>
      <td>48.67</td>
      <td>2049161404256</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>2016-08-08 14:02:35</td>
      <td>24.97</td>
      <td>2872494724827</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-10-28 09:52:15</td>
      <td>25.34</td>
      <td>6706101910500</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>2016-07-19 09:35:59</td>
      <td>31.09</td>
      <td>2959749591417</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-11-11 16:24:16</td>
      <td>22.99</td>
      <td>3454326063039</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>2016-08-29 02:36:06</td>
      <td>18.83</td>
      <td>7368222134792</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>2016-06-22 07:45:30</td>
      <td>34.54</td>
      <td>684950063164</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>2016-06-07 11:43:43</td>
      <td>56.02</td>
      <td>311733202150</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>2016-02-10 00:50:04</td>
      <td>34.69</td>
      <td>9595491362610</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>2016-03-14 01:55:32</td>
      <td>38.80</td>
      <td>9205811495606</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>2016-01-26 01:06:41</td>
      <td>34.92</td>
      <td>4165974278063</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>2016-09-28 07:30:55</td>
      <td>12.55</td>
      <td>4336212615821</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>2016-04-21 10:20:09</td>
      <td>16.50</td>
      <td>5702608059064</td>
    </tr>
  </tbody>
</table>
<p>2375 rows × 3 columns</p>
</div>



```python
numridesbycity = pd.DataFrame(df_ride.groupby(['city'])['ride_id'].count())

maxrides = numridesbycity['ride_id'].max()

import math

def roundup(x):
    return int(math.ceil(x / 10.0)) * 10


plt.xlim(0,roundup(maxrides))
numridesbycity

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
      <th>ride_id</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Alvarezhaven</th>
      <td>31</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>26</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>9</td>
    </tr>
    <tr>
      <th>Antoniomouth</th>
      <td>22</td>
    </tr>
    <tr>
      <th>Aprilchester</th>
      <td>19</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>31</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Carrollbury</th>
      <td>10</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>29</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>12</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>11</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>21</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>25</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>13</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>22</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>28</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>19</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>11</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>10</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>7</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>27</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>8</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>19</td>
    </tr>
    <tr>
      <th>Floresberg</th>
      <td>10</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>24</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>9</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>4</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>6</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>31</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>12</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>18</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>18</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>19</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>28</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>10</td>
    </tr>
    <tr>
      <th>Kimberlychester</th>
      <td>27</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>6</td>
    </tr>
    <tr>
      <th>Kyleton</th>
      <td>16</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>17</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>25</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>25</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>22</td>
    </tr>
    <tr>
      <th>Lake Stevenbury</th>
      <td>21</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>23</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>28</td>
    </tr>
    <tr>
      <th>Manuelchester</th>
      <td>1</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>9</td>
    </tr>
    <tr>
      <th>Maryside</th>
      <td>21</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>4</td>
    </tr>
    <tr>
      <th>Mooreview</th>
      <td>21</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>22</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>28</td>
    </tr>
    <tr>
      <th>New Brandonborough</th>
      <td>14</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>22</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>13</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>28</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>25</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>17</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>4</td>
    </tr>
    <tr>
      <th>New Lynn</th>
      <td>13</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>20</td>
    </tr>
    <tr>
      <th>New Michelleberg</th>
      <td>11</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>23</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>26</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>9</td>
    </tr>
    <tr>
      <th>North Tracyfort</th>
      <td>10</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>10</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>13</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>20</td>
    </tr>
    <tr>
      <th>Port Alexandria</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>32</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>34</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>18</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>22</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>21</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>22</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>27</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>24</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>23</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>20</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>23</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>27</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>27</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>6</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>27</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>21</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>5</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>19</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>16</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>12</td>
    </tr>
    <tr>
      <th>South Josephville</th>
      <td>24</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>32</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>22</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>26</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>5</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>30</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>34</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>24</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>13</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>26</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>23</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>15</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>16</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>20</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>30</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>24</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>29</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>12</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>21</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>7</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>29</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>14</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>17</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>31</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>18</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>19</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>11</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>31</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>19</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>20</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>24</td>
    </tr>
  </tbody>
</table>
</div>




```python
avgfarebycity = pd.DataFrame(df_ride.groupby(['city'])['fare'].mean())
maxavgfare = avgfarebycity['fare'].max()
minavgfare = avgfarebycity['fare'].min()
pd.set_option('display.max_rows', 500)
plt.ylim(minavgfare-2,roundup(maxavgfare))
avgfarebycity


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
      <th>fare</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Alvarezhaven</th>
      <td>23.928710</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>20.609615</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>37.315556</td>
    </tr>
    <tr>
      <th>Antoniomouth</th>
      <td>23.625000</td>
    </tr>
    <tr>
      <th>Aprilchester</th>
      <td>21.981579</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>25.106452</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>33.711333</td>
    </tr>
    <tr>
      <th>Carrollbury</th>
      <td>36.606000</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>25.395517</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>31.051667</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>34.591818</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>22.978095</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>21.497200</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>31.416154</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>26.169091</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>24.478214</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>32.599474</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>33.660909</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>39.053000</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>33.244286</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>26.876667</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>30.043750</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>25.478947</td>
    </tr>
    <tr>
      <th>Floresberg</th>
      <td>32.310000</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>23.034583</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>32.002222</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>21.482500</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>32.006667</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>24.779355</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>27.831667</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>33.165556</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>28.752778</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>24.169474</td>
    </tr>
    <tr>
      <th>Kelseyland</th>
      <td>21.806429</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>36.928000</td>
    </tr>
    <tr>
      <th>Kimberlychester</th>
      <td>22.947037</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>34.980000</td>
    </tr>
    <tr>
      <th>Kyleton</th>
      <td>31.167500</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>29.791176</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>27.334800</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>25.349600</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>26.610000</td>
    </tr>
    <tr>
      <th>Lake Stevenbury</th>
      <td>24.657619</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>22.225217</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>28.428929</td>
    </tr>
    <tr>
      <th>Manuelchester</th>
      <td>49.620000</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>30.498889</td>
    </tr>
    <tr>
      <th>Maryside</th>
      <td>26.844286</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>43.532500</td>
    </tr>
    <tr>
      <th>Mooreview</th>
      <td>29.520476</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>26.861818</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>24.966786</td>
    </tr>
    <tr>
      <th>New Brandonborough</th>
      <td>31.902857</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>24.157727</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>31.034615</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>27.084286</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>24.130000</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>32.810588</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>35.042500</td>
    </tr>
    <tr>
      <th>New Lynn</th>
      <td>28.454615</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>28.473500</td>
    </tr>
    <tr>
      <th>New Michelleberg</th>
      <td>24.971818</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>34.069130</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>25.899615</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>32.386667</td>
    </tr>
    <tr>
      <th>North Tracyfort</th>
      <td>26.856000</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>38.146000</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>25.549333</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>31.144615</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>23.307500</td>
    </tr>
    <tr>
      <th>Port Alexandria</th>
      <td>26.316667</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>28.242000</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>31.806562</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>25.882941</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>31.193889</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>26.367727</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>22.329524</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>26.720000</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>27.047407</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>23.346667</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>21.332609</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>31.866500</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>22.486087</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>23.105926</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>23.490000</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>33.862000</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>34.828333</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>22.788889</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>24.598571</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>28.698000</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>31.345789</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>29.798750</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>38.983333</td>
    </tr>
    <tr>
      <th>South Josephville</th>
      <td>26.823750</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>27.087500</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>26.031364</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>26.516667</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>23.681154</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>31.948000</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>21.614000</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>27.464706</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>30.308333</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>28.510000</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>24.207308</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>27.220870</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>21.474667</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>29.721250</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>19.523000</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>24.157667</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>25.436250</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>22.330345</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>27.013333</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>21.072857</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>21.528571</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>24.280000</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>33.799286</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>33.278235</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>24.875484</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>22.368333</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>29.609474</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>34.278182</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>26.990323</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>22.676842</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>27.205500</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>28.301667</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_city['avg_fare']=avgfarebycity['fare']
df_city['ride_count']=numridesbycity['ride_id']
df_city

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
      <th>driver_count</th>
      <th>type</th>
      <th>avg_fare</th>
      <th>ride_count</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Kelseyland</th>
      <td>63</td>
      <td>Urban</td>
      <td>21.806429</td>
      <td>28</td>
    </tr>
    <tr>
      <th>Nguyenbury</th>
      <td>8</td>
      <td>Urban</td>
      <td>25.899615</td>
      <td>26</td>
    </tr>
    <tr>
      <th>East Douglas</th>
      <td>12</td>
      <td>Urban</td>
      <td>26.169091</td>
      <td>22</td>
    </tr>
    <tr>
      <th>West Dawnfurt</th>
      <td>34</td>
      <td>Urban</td>
      <td>22.330345</td>
      <td>29</td>
    </tr>
    <tr>
      <th>Rodriguezburgh</th>
      <td>52</td>
      <td>Urban</td>
      <td>21.332609</td>
      <td>23</td>
    </tr>
    <tr>
      <th>South Josephville</th>
      <td>4</td>
      <td>Urban</td>
      <td>26.823750</td>
      <td>24</td>
    </tr>
    <tr>
      <th>West Sydneyhaven</th>
      <td>70</td>
      <td>Urban</td>
      <td>22.368333</td>
      <td>18</td>
    </tr>
    <tr>
      <th>Travisville</th>
      <td>37</td>
      <td>Urban</td>
      <td>27.220870</td>
      <td>23</td>
    </tr>
    <tr>
      <th>Torresshire</th>
      <td>70</td>
      <td>Urban</td>
      <td>24.207308</td>
      <td>26</td>
    </tr>
    <tr>
      <th>Lisaville</th>
      <td>66</td>
      <td>Urban</td>
      <td>28.428929</td>
      <td>28</td>
    </tr>
    <tr>
      <th>Mooreview</th>
      <td>34</td>
      <td>Urban</td>
      <td>29.520476</td>
      <td>21</td>
    </tr>
    <tr>
      <th>Smithhaven</th>
      <td>67</td>
      <td>Urban</td>
      <td>22.788889</td>
      <td>27</td>
    </tr>
    <tr>
      <th>Carrollfort</th>
      <td>55</td>
      <td>Urban</td>
      <td>25.395517</td>
      <td>29</td>
    </tr>
    <tr>
      <th>Port Josephfurt</th>
      <td>28</td>
      <td>Urban</td>
      <td>26.367727</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Lake Jeffreyland</th>
      <td>15</td>
      <td>Urban</td>
      <td>27.334800</td>
      <td>25</td>
    </tr>
    <tr>
      <th>South Louis</th>
      <td>12</td>
      <td>Urban</td>
      <td>27.087500</td>
      <td>32</td>
    </tr>
    <tr>
      <th>West Peter</th>
      <td>61</td>
      <td>Urban</td>
      <td>24.875484</td>
      <td>31</td>
    </tr>
    <tr>
      <th>Kimberlychester</th>
      <td>13</td>
      <td>Urban</td>
      <td>22.947037</td>
      <td>27</td>
    </tr>
    <tr>
      <th>Alyssaberg</th>
      <td>67</td>
      <td>Urban</td>
      <td>20.609615</td>
      <td>26</td>
    </tr>
    <tr>
      <th>Sarabury</th>
      <td>46</td>
      <td>Urban</td>
      <td>23.490000</td>
      <td>27</td>
    </tr>
    <tr>
      <th>Yolandafurt</th>
      <td>7</td>
      <td>Urban</td>
      <td>27.205500</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Edwardsbury</th>
      <td>11</td>
      <td>Urban</td>
      <td>26.876667</td>
      <td>27</td>
    </tr>
    <tr>
      <th>New Andreamouth</th>
      <td>42</td>
      <td>Urban</td>
      <td>24.966786</td>
      <td>28</td>
    </tr>
    <tr>
      <th>New David</th>
      <td>31</td>
      <td>Urban</td>
      <td>27.084286</td>
      <td>28</td>
    </tr>
    <tr>
      <th>Arnoldview</th>
      <td>41</td>
      <td>Urban</td>
      <td>25.106452</td>
      <td>31</td>
    </tr>
    <tr>
      <th>Williamshire</th>
      <td>70</td>
      <td>Urban</td>
      <td>26.990323</td>
      <td>31</td>
    </tr>
    <tr>
      <th>Lisatown</th>
      <td>47</td>
      <td>Urban</td>
      <td>22.225217</td>
      <td>23</td>
    </tr>
    <tr>
      <th>New Aaron</th>
      <td>60</td>
      <td>Urban</td>
      <td>26.861818</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Swansonbury</th>
      <td>64</td>
      <td>Urban</td>
      <td>27.464706</td>
      <td>34</td>
    </tr>
    <tr>
      <th>Fosterside</th>
      <td>69</td>
      <td>Urban</td>
      <td>23.034583</td>
      <td>24</td>
    </tr>
    <tr>
      <th>New Jeffrey</th>
      <td>58</td>
      <td>Urban</td>
      <td>24.130000</td>
      <td>25</td>
    </tr>
    <tr>
      <th>West Brittanyton</th>
      <td>9</td>
      <td>Urban</td>
      <td>25.436250</td>
      <td>24</td>
    </tr>
    <tr>
      <th>Wiseborough</th>
      <td>55</td>
      <td>Urban</td>
      <td>22.676842</td>
      <td>19</td>
    </tr>
    <tr>
      <th>New Maryport</th>
      <td>26</td>
      <td>Urban</td>
      <td>28.473500</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Lake Stevenbury</th>
      <td>63</td>
      <td>Urban</td>
      <td>24.657619</td>
      <td>21</td>
    </tr>
    <tr>
      <th>New Christine</th>
      <td>22</td>
      <td>Urban</td>
      <td>24.157727</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Spencertown</th>
      <td>68</td>
      <td>Urban</td>
      <td>23.681154</td>
      <td>26</td>
    </tr>
    <tr>
      <th>Russellport</th>
      <td>9</td>
      <td>Urban</td>
      <td>22.486087</td>
      <td>23</td>
    </tr>
    <tr>
      <th>Maryside</th>
      <td>20</td>
      <td>Urban</td>
      <td>26.844286</td>
      <td>21</td>
    </tr>
    <tr>
      <th>West Alexis</th>
      <td>47</td>
      <td>Urban</td>
      <td>19.523000</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Port Samantha</th>
      <td>55</td>
      <td>Urban</td>
      <td>27.047407</td>
      <td>27</td>
    </tr>
    <tr>
      <th>Eriktown</th>
      <td>15</td>
      <td>Urban</td>
      <td>25.478947</td>
      <td>19</td>
    </tr>
    <tr>
      <th>Pamelahaven</th>
      <td>30</td>
      <td>Urban</td>
      <td>25.549333</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Aprilchester</th>
      <td>49</td>
      <td>Urban</td>
      <td>21.981579</td>
      <td>19</td>
    </tr>
    <tr>
      <th>South Roy</th>
      <td>35</td>
      <td>Urban</td>
      <td>26.031364</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Pearsonberg</th>
      <td>43</td>
      <td>Urban</td>
      <td>23.307500</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Sandymouth</th>
      <td>11</td>
      <td>Urban</td>
      <td>23.105926</td>
      <td>27</td>
    </tr>
    <tr>
      <th>East Erin</th>
      <td>43</td>
      <td>Urban</td>
      <td>24.478214</td>
      <td>28</td>
    </tr>
    <tr>
      <th>Port Johnstad</th>
      <td>22</td>
      <td>Urban</td>
      <td>25.882941</td>
      <td>34</td>
    </tr>
    <tr>
      <th>Vickimouth</th>
      <td>13</td>
      <td>Urban</td>
      <td>21.474667</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Jacobfort</th>
      <td>52</td>
      <td>Urban</td>
      <td>24.779355</td>
      <td>31</td>
    </tr>
    <tr>
      <th>South Bryanstad</th>
      <td>73</td>
      <td>Urban</td>
      <td>24.598571</td>
      <td>21</td>
    </tr>
    <tr>
      <th>West Oscar</th>
      <td>11</td>
      <td>Urban</td>
      <td>24.280000</td>
      <td>29</td>
    </tr>
    <tr>
      <th>Antoniomouth</th>
      <td>21</td>
      <td>Urban</td>
      <td>23.625000</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Stewartview</th>
      <td>49</td>
      <td>Urban</td>
      <td>21.614000</td>
      <td>30</td>
    </tr>
    <tr>
      <th>West Brandy</th>
      <td>12</td>
      <td>Urban</td>
      <td>24.157667</td>
      <td>30</td>
    </tr>
    <tr>
      <th>Davidtown</th>
      <td>73</td>
      <td>Urban</td>
      <td>22.978095</td>
      <td>21</td>
    </tr>
    <tr>
      <th>Kellershire</th>
      <td>51</td>
      <td>Urban</td>
      <td>24.169474</td>
      <td>19</td>
    </tr>
    <tr>
      <th>Zimmermanmouth</th>
      <td>45</td>
      <td>Urban</td>
      <td>28.301667</td>
      <td>24</td>
    </tr>
    <tr>
      <th>Port Martinberg</th>
      <td>44</td>
      <td>Urban</td>
      <td>22.329524</td>
      <td>21</td>
    </tr>
    <tr>
      <th>Lake Sarashire</th>
      <td>8</td>
      <td>Urban</td>
      <td>26.610000</td>
      <td>22</td>
    </tr>
    <tr>
      <th>Prattfurt</th>
      <td>43</td>
      <td>Urban</td>
      <td>23.346667</td>
      <td>24</td>
    </tr>
    <tr>
      <th>Davistown</th>
      <td>25</td>
      <td>Urban</td>
      <td>21.497200</td>
      <td>25</td>
    </tr>
    <tr>
      <th>West Jefferyfurt</th>
      <td>65</td>
      <td>Urban</td>
      <td>21.072857</td>
      <td>21</td>
    </tr>
    <tr>
      <th>Lake Jennaton</th>
      <td>65</td>
      <td>Urban</td>
      <td>25.349600</td>
      <td>25</td>
    </tr>
    <tr>
      <th>Alvarezhaven</th>
      <td>21</td>
      <td>Urban</td>
      <td>23.928710</td>
      <td>31</td>
    </tr>
    <tr>
      <th>Carrollbury</th>
      <td>4</td>
      <td>Suburban</td>
      <td>36.606000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>Williamchester</th>
      <td>26</td>
      <td>Suburban</td>
      <td>34.278182</td>
      <td>11</td>
    </tr>
    <tr>
      <th>New Michelleberg</th>
      <td>9</td>
      <td>Suburban</td>
      <td>24.971818</td>
      <td>11</td>
    </tr>
    <tr>
      <th>West Evan</th>
      <td>4</td>
      <td>Suburban</td>
      <td>27.013333</td>
      <td>12</td>
    </tr>
    <tr>
      <th>South Gracechester</th>
      <td>19</td>
      <td>Suburban</td>
      <td>31.345789</td>
      <td>19</td>
    </tr>
    <tr>
      <th>East Jenniferchester</th>
      <td>22</td>
      <td>Suburban</td>
      <td>32.599474</td>
      <td>19</td>
    </tr>
    <tr>
      <th>West Paulport</th>
      <td>5</td>
      <td>Suburban</td>
      <td>33.278235</td>
      <td>17</td>
    </tr>
    <tr>
      <th>New Brandonborough</th>
      <td>9</td>
      <td>Suburban</td>
      <td>31.902857</td>
      <td>14</td>
    </tr>
    <tr>
      <th>Floresberg</th>
      <td>7</td>
      <td>Suburban</td>
      <td>32.310000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>Lake Brenda</th>
      <td>24</td>
      <td>Suburban</td>
      <td>29.791176</td>
      <td>17</td>
    </tr>
    <tr>
      <th>Kyleton</th>
      <td>12</td>
      <td>Suburban</td>
      <td>31.167500</td>
      <td>16</td>
    </tr>
    <tr>
      <th>Thomastown</th>
      <td>1</td>
      <td>Suburban</td>
      <td>30.308333</td>
      <td>24</td>
    </tr>
    <tr>
      <th>South Shannonborough</th>
      <td>9</td>
      <td>Suburban</td>
      <td>26.516667</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Jeffreyton</th>
      <td>8</td>
      <td>Suburban</td>
      <td>33.165556</td>
      <td>18</td>
    </tr>
    <tr>
      <th>Port Michelleview</th>
      <td>16</td>
      <td>Suburban</td>
      <td>26.720000</td>
      <td>22</td>
    </tr>
    <tr>
      <th>West Pamelaborough</th>
      <td>27</td>
      <td>Suburban</td>
      <td>33.799286</td>
      <td>14</td>
    </tr>
    <tr>
      <th>Sarahview</th>
      <td>18</td>
      <td>Suburban</td>
      <td>33.862000</td>
      <td>15</td>
    </tr>
    <tr>
      <th>New Cindyborough</th>
      <td>20</td>
      <td>Suburban</td>
      <td>31.034615</td>
      <td>13</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>15</td>
      <td>Suburban</td>
      <td>31.806562</td>
      <td>32</td>
    </tr>
    <tr>
      <th>New Samanthaside</th>
      <td>16</td>
      <td>Suburban</td>
      <td>34.069130</td>
      <td>23</td>
    </tr>
    <tr>
      <th>Paulfort</th>
      <td>13</td>
      <td>Suburban</td>
      <td>31.144615</td>
      <td>13</td>
    </tr>
    <tr>
      <th>Jasonfort</th>
      <td>25</td>
      <td>Suburban</td>
      <td>27.831667</td>
      <td>12</td>
    </tr>
    <tr>
      <th>North Tara</th>
      <td>14</td>
      <td>Suburban</td>
      <td>32.386667</td>
      <td>9</td>
    </tr>
    <tr>
      <th>East Cherylfurt</th>
      <td>9</td>
      <td>Suburban</td>
      <td>31.416154</td>
      <td>13</td>
    </tr>
    <tr>
      <th>Rodriguezview</th>
      <td>10</td>
      <td>Suburban</td>
      <td>31.866500</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Tiffanyton</th>
      <td>21</td>
      <td>Suburban</td>
      <td>28.510000</td>
      <td>13</td>
    </tr>
    <tr>
      <th>Port Alexandria</th>
      <td>27</td>
      <td>Suburban</td>
      <td>26.316667</td>
      <td>15</td>
    </tr>
    <tr>
      <th>South Jennifer</th>
      <td>6</td>
      <td>Suburban</td>
      <td>29.798750</td>
      <td>16</td>
    </tr>
    <tr>
      <th>Anitamouth</th>
      <td>16</td>
      <td>Suburban</td>
      <td>37.315556</td>
      <td>9</td>
    </tr>
    <tr>
      <th>Conwaymouth</th>
      <td>18</td>
      <td>Suburban</td>
      <td>34.591818</td>
      <td>11</td>
    </tr>
    <tr>
      <th>New Lynn</th>
      <td>20</td>
      <td>Suburban</td>
      <td>28.454615</td>
      <td>13</td>
    </tr>
    <tr>
      <th>Port Jose</th>
      <td>11</td>
      <td>Suburban</td>
      <td>31.193889</td>
      <td>18</td>
    </tr>
    <tr>
      <th>Johnland</th>
      <td>13</td>
      <td>Suburban</td>
      <td>28.752778</td>
      <td>18</td>
    </tr>
    <tr>
      <th>West Tony</th>
      <td>17</td>
      <td>Suburban</td>
      <td>29.609474</td>
      <td>19</td>
    </tr>
    <tr>
      <th>Port James</th>
      <td>3</td>
      <td>Suburban</td>
      <td>31.806562</td>
      <td>32</td>
    </tr>
    <tr>
      <th>Campbellport</th>
      <td>26</td>
      <td>Suburban</td>
      <td>33.711333</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Port Guytown</th>
      <td>26</td>
      <td>Suburban</td>
      <td>28.242000</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Webstertown</th>
      <td>26</td>
      <td>Suburban</td>
      <td>29.721250</td>
      <td>16</td>
    </tr>
    <tr>
      <th>Clarkstad</th>
      <td>21</td>
      <td>Suburban</td>
      <td>31.051667</td>
      <td>12</td>
    </tr>
    <tr>
      <th>North Tracyfort</th>
      <td>18</td>
      <td>Suburban</td>
      <td>26.856000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>Martinmouth</th>
      <td>5</td>
      <td>Suburban</td>
      <td>30.498889</td>
      <td>9</td>
    </tr>
    <tr>
      <th>New Jessicamouth</th>
      <td>22</td>
      <td>Suburban</td>
      <td>32.810588</td>
      <td>17</td>
    </tr>
    <tr>
      <th>South Elizabethmouth</th>
      <td>3</td>
      <td>Rural</td>
      <td>28.698000</td>
      <td>5</td>
    </tr>
    <tr>
      <th>East Troybury</th>
      <td>3</td>
      <td>Rural</td>
      <td>33.244286</td>
      <td>7</td>
    </tr>
    <tr>
      <th>Kinghaven</th>
      <td>3</td>
      <td>Rural</td>
      <td>34.980000</td>
      <td>6</td>
    </tr>
    <tr>
      <th>New Johnbury</th>
      <td>6</td>
      <td>Rural</td>
      <td>35.042500</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Erikport</th>
      <td>3</td>
      <td>Rural</td>
      <td>30.043750</td>
      <td>8</td>
    </tr>
    <tr>
      <th>Jacksonfort</th>
      <td>6</td>
      <td>Rural</td>
      <td>32.006667</td>
      <td>6</td>
    </tr>
    <tr>
      <th>Shelbyhaven</th>
      <td>9</td>
      <td>Rural</td>
      <td>34.828333</td>
      <td>6</td>
    </tr>
    <tr>
      <th>Matthewside</th>
      <td>4</td>
      <td>Rural</td>
      <td>43.532500</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Kennethburgh</th>
      <td>3</td>
      <td>Rural</td>
      <td>36.928000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>South Joseph</th>
      <td>3</td>
      <td>Rural</td>
      <td>38.983333</td>
      <td>12</td>
    </tr>
    <tr>
      <th>Manuelchester</th>
      <td>7</td>
      <td>Rural</td>
      <td>49.620000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Stevensport</th>
      <td>6</td>
      <td>Rural</td>
      <td>31.948000</td>
      <td>5</td>
    </tr>
    <tr>
      <th>North Whitney</th>
      <td>10</td>
      <td>Rural</td>
      <td>38.146000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>East Stephen</th>
      <td>6</td>
      <td>Rural</td>
      <td>39.053000</td>
      <td>10</td>
    </tr>
    <tr>
      <th>East Leslie</th>
      <td>9</td>
      <td>Rural</td>
      <td>33.660909</td>
      <td>11</td>
    </tr>
    <tr>
      <th>Hernandezshire</th>
      <td>10</td>
      <td>Rural</td>
      <td>32.002222</td>
      <td>9</td>
    </tr>
    <tr>
      <th>Horneland</th>
      <td>8</td>
      <td>Rural</td>
      <td>21.482500</td>
      <td>4</td>
    </tr>
    <tr>
      <th>West Kevintown</th>
      <td>5</td>
      <td>Rural</td>
      <td>21.528571</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.title("Pyber Ride Sharing Data (2016)")
plt.xlabel("Total Number of Rides (Per City)")
plt.ylabel("Average Fare($)")
sbn.set_style()

col = np.where(df_city['type']=="Urban",'coral',np.where(df_city['type']=="Suburban",'lightblue','gold'))
plt.scatter(df_city['ride_count'], df_city['avg_fare'], df_city['driver_count'],marker="o",facecolors=col, edgecolors="black",)


plt.legend(df_city['type'])
plt.show()
```


![png](output_6_0.png)


# Observable trends:
    1) The more densely populated the city, the more drivers there in that city
    2) The average fare is generally higher in rural areas, probably because destinations are farther away
    3) The number of rides per city is inversely correlated with average fare
    
