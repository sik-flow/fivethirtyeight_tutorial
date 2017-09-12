

```python
import pandas as pd
```


```python
direct_link = 'http://www.randalolson.com/wp-content/uploads/percent-bachelors-degrees-women-usa.csv'
women_majors = pd.read_csv(direct_link)
```


```python
women_majors.head()
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
      <th>Year</th>
      <th>Agriculture</th>
      <th>Architecture</th>
      <th>Art and Performance</th>
      <th>Biology</th>
      <th>Business</th>
      <th>Communications and Journalism</th>
      <th>Computer Science</th>
      <th>Education</th>
      <th>Engineering</th>
      <th>English</th>
      <th>Foreign Languages</th>
      <th>Health Professions</th>
      <th>Math and Statistics</th>
      <th>Physical Sciences</th>
      <th>Psychology</th>
      <th>Public Administration</th>
      <th>Social Sciences and History</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1970</td>
      <td>4.229798</td>
      <td>11.921005</td>
      <td>59.7</td>
      <td>29.088363</td>
      <td>9.064439</td>
      <td>35.3</td>
      <td>13.6</td>
      <td>74.535328</td>
      <td>0.8</td>
      <td>65.570923</td>
      <td>73.8</td>
      <td>77.1</td>
      <td>38.0</td>
      <td>13.8</td>
      <td>44.4</td>
      <td>68.4</td>
      <td>36.8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1971</td>
      <td>5.452797</td>
      <td>12.003106</td>
      <td>59.9</td>
      <td>29.394403</td>
      <td>9.503187</td>
      <td>35.5</td>
      <td>13.6</td>
      <td>74.149204</td>
      <td>1.0</td>
      <td>64.556485</td>
      <td>73.9</td>
      <td>75.5</td>
      <td>39.0</td>
      <td>14.9</td>
      <td>46.2</td>
      <td>65.5</td>
      <td>36.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1972</td>
      <td>7.420710</td>
      <td>13.214594</td>
      <td>60.4</td>
      <td>29.810221</td>
      <td>10.558962</td>
      <td>36.6</td>
      <td>14.9</td>
      <td>73.554520</td>
      <td>1.2</td>
      <td>63.664263</td>
      <td>74.6</td>
      <td>76.9</td>
      <td>40.2</td>
      <td>14.8</td>
      <td>47.6</td>
      <td>62.6</td>
      <td>36.1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1973</td>
      <td>9.653602</td>
      <td>14.791613</td>
      <td>60.2</td>
      <td>31.147915</td>
      <td>12.804602</td>
      <td>38.4</td>
      <td>16.4</td>
      <td>73.501814</td>
      <td>1.6</td>
      <td>62.941502</td>
      <td>74.9</td>
      <td>77.4</td>
      <td>40.9</td>
      <td>16.5</td>
      <td>50.4</td>
      <td>64.3</td>
      <td>36.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1974</td>
      <td>14.074623</td>
      <td>17.444688</td>
      <td>61.9</td>
      <td>32.996183</td>
      <td>16.204850</td>
      <td>40.5</td>
      <td>18.9</td>
      <td>73.336811</td>
      <td>2.2</td>
      <td>62.413412</td>
      <td>75.3</td>
      <td>77.9</td>
      <td>41.8</td>
      <td>18.2</td>
      <td>52.6</td>
      <td>66.1</td>
      <td>37.3</td>
    </tr>
  </tbody>
</table>
</div>




```python
under_20 = women_majors.loc[0, women_majors.loc[0] < 20]
under_20
```




    Agriculture           4.229798
    Architecture         11.921005
    Business              9.064439
    Computer Science     13.600000
    Engineering           0.800000
    Physical Sciences    13.800000
    Name: 0, dtype: float64




```python
women_majors.loc[0,:]
```




    Year                             1970.000000
    Agriculture                         4.229798
    Architecture                       11.921005
    Art and Performance                59.700000
    Biology                            29.088363
    Business                            9.064439
    Communications and Journalism      35.300000
    Computer Science                   13.600000
    Education                          74.535328
    Engineering                         0.800000
    English                            65.570923
    Foreign Languages                  73.800000
    Health Professions                 77.100000
    Math and Statistics                38.000000
    Physical Sciences                  13.800000
    Psychology                         44.400000
    Public Administration              68.400000
    Social Sciences and History        36.800000
    Name: 0, dtype: float64




```python
%matplotlib inline
under_20_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12, 8))
print ('Type:', type(under_20_graph))
```

    Type: <class 'matplotlib.axes._subplots.AxesSubplot'>



![png](fivethirtyeight_files/fivethirtyeight_5_1.png)



```python
import matplotlib.style as style
style.available
```




    ['_classic_test',
     'bmh',
     'classic',
     'dark_background',
     'fivethirtyeight',
     'ggplot',
     'grayscale',
     'seaborn-bright',
     'seaborn-colorblind',
     'seaborn-dark-palette',
     'seaborn-dark',
     'seaborn-darkgrid',
     'seaborn-deep',
     'seaborn-muted',
     'seaborn-notebook',
     'seaborn-paper',
     'seaborn-pastel',
     'seaborn-poster',
     'seaborn-talk',
     'seaborn-ticks',
     'seaborn-white',
     'seaborn-whitegrid',
     'seaborn']




```python
style.use('fivethirtyeight')
women_majors.plot(x = 'Year', y = under_20.index, figsize = (12, 8))
```




    <matplotlib.axes._subplots.AxesSubplot at 0x10e85b160>




![png](fivethirtyeight_files/fivethirtyeight_7_1.png)



```python
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12, 8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
```


![png](fivethirtyeight_files/fivethirtyeight_8_0.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)

# Customizing the tick labels of the y-axis
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
print('The tick labels of the y-axis:', fte_graph.get_yticks()) # -10 and 60 are not visible on the graph
```

    The tick labels of the y-axis: [-10.   0.  10.  20.  30.  40.  50.  60.]



![png](fivethirtyeight_files/fivethirtyeight_9_1.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])

# Generate a bolded horizontal line at y \ 0
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
```




    <matplotlib.lines.Line2D at 0x10f3575c0>




![png](fivethirtyeight_files/fivethirtyeight_10_1.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)

# Add an extra vertical line by tweaking the range of the x-axis
fte_graph.set_xlim(left = 1969, right = 2011)
```




    (1969, 2011)




![png](fivethirtyeight_files/fivethirtyeight_11_1.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
fte_graph.set_xlim(left = 1969, right = 2011)

# Remove the label of the x-axis
fte_graph.xaxis.label.set_visible(False)

# The signature bar
fte_graph.text(x = 1965.8, y = -7,
    s = '   ©DATAQUEST                                                                                 Source: National Center for Education Statistics   ',
    fontsize = 14, color = '#f0f0f0', backgroundcolor = 'grey')
```




    <matplotlib.text.Text at 0x1107c9780>




![png](fivethirtyeight_files/fivethirtyeight_12_1.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
fte_graph.xaxis.label.set_visible(False)
fte_graph.set_xlim(left = 1969, right = 2011)

# The other signature bar
fte_graph.text(x = 1967.1, y = -6.5,
    s = '________________________________________________________________________________________________________________',
    color = 'grey', alpha = .7)

fte_graph.text(x = 1966.1, y = -9,
    s = '   ©DATAQUEST                                                                               Source: National Center for Education Statistics   ',
    fontsize = 14, color = 'grey', alpha = .7)
```




    <matplotlib.text.Text at 0x110789da0>




![png](fivethirtyeight_files/fivethirtyeight_13_1.png)



```python
# The previous code
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8))
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
fte_graph.xaxis.label.set_visible(False)
fte_graph.set_xlim(left = 1969, right = 2011)
fte_graph.text(x = 1965.8, y = -7,
    s = '   ©DATAQUEST                                                                                 Source: National Center for Education Statistics   ',
    fontsize = 14, color = '#f0f0f0', backgroundcolor = 'grey')


# Adding a title and a subtitle
fte_graph.text(x = 1966.65, y = 62.7, s = "The gender gap is transitory - even for extreme cases",
               fontsize = 26, weight = 'bold', alpha = .75)
fte_graph.text(x = 1966.65, y = 57, 
               s = 'Percentage of Bachelors conferred to women from 1970 to 2011 in the US for\nextreme cases where the percentage was less than 20% in 1970',
              fontsize = 19, alpha = .85)
```




    <matplotlib.text.Text at 0x111149ac8>




![png](fivethirtyeight_files/fivethirtyeight_14_1.png)



```python
# Colorblind-friendly colors
colors = [[0,0,0], [230/255,159/255,0], [86/255,180/255,233/255], [0,158/255,115/255], 
          [213/255,94/255,0], [0,114/255,178/255]]

# The previous code we modify
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8), color = colors)

# The previous code that remains the same
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
fte_graph.xaxis.label.set_visible(False)
fte_graph.set_xlim(left = 1969, right = 2011)
fte_graph.text(x = 1965.8, y = -7,
    s = '   ©DATAQUEST                                                                                 Source: National Center for Education Statistics   ',
    fontsize = 14, color = '#f0f0f0', backgroundcolor = 'grey')
fte_graph.text(x = 1966.65, y = 62.7, s = "The gender gap is transitory - even for extreme cases",
               fontsize = 26, weight = 'bold', alpha = .75)
fte_graph.text(x = 1966.65, y = 57, 
               s = 'Percentage of Bachelors conferred to women from 1970 to 2011 in the US for\nextreme cases where the percentage was less than 20% in 1970',
              fontsize = 19, alpha = .85)
```




    <matplotlib.text.Text at 0x1113a92b0>




![png](fivethirtyeight_files/fivethirtyeight_15_1.png)



```python
# The previous code we modify
fte_graph = women_majors.plot(x = 'Year', y = under_20.index, figsize = (12,8), color = colors, legend = False)

# The previous code that remains unchanged
fte_graph.tick_params(axis = 'both', which = 'major', labelsize = 18)
fte_graph.set_yticklabels(labels = [-10, '0   ', '10   ', '20   ', '30   ', '40   ', '50%'])
fte_graph.axhline(y = 0, color = 'black', linewidth = 1.3, alpha = .7)
fte_graph.xaxis.label.set_visible(False)
fte_graph.set_xlim(left = 1969, right = 2011)
fte_graph.text(x = 1965.8, y = -7,
    s = '   ©DATAQUEST                                                                                 Source: National Center for Education Statistics   ',
    fontsize = 14, color = '#f0f0f0', backgroundcolor = 'grey')
fte_graph.text(x = 1966.65, y = 62.7, s = "The gender gap is transitory - even for extreme cases",
               fontsize = 26, weight = 'bold', alpha = .75)
fte_graph.text(x = 1966.65, y = 57, 
               s = 'Percentage of Bachelors conferred to women from 1970 to 2011 in the US for\nextreme cases where the percentage was less than 20% in 1970',
              fontsize = 19, alpha = .85)

# Add colored labels
fte_graph.text(x = 1994, y = 44, s = 'Agriculture', color = colors[0], weight = 'bold', rotation = 33,
              backgroundcolor = '#f0f0f0')
fte_graph.text(x = 1985, y = 42.2, s = 'Architecture', color = colors[1], weight = 'bold', rotation = 18,
              backgroundcolor = '#f0f0f0')
fte_graph.text(x = 2004, y = 51, s = 'Business', color = colors[2], weight = 'bold', rotation = -5, 
               backgroundcolor = '#f0f0f0')
fte_graph.text(x = 2001, y = 30, s = 'Computer Science', color = colors[3], weight = 'bold', rotation = -42.5,
              backgroundcolor = '#f0f0f0')
fte_graph.text(x = 1987, y = 11.5, s = 'Engineering', color = colors[4], weight = 'bold',
              backgroundcolor = '#f0f0f0')
fte_graph.text(x = 1976, y = 25, s = 'Physical Sciences', color = colors[5], weight = 'bold', rotation = 27,
              backgroundcolor = '#f0f0f0')
```




    <matplotlib.text.Text at 0x111449d30>




![png](fivethirtyeight_files/fivethirtyeight_16_1.png)

