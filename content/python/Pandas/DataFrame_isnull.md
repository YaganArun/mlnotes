---
title: "To find null in a DataFrame"
author: "Yagan Arun"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
cars = [['Audi' , 10] , ['Apple' , None] , ['Lambhorghini',10] , ['Bens',9] , ['Samsung',None]]
```


```python
import pandas as pd
custom = pd.DataFrame(data=cars , columns=['Car','Rating'])
```


```python
custom
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Car</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Audi</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Apple</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Lambhorghini</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bens</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Samsung</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
custom.isnull() #easy with small datasets
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Car</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>True</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
custom.isnull().sum() #gives the count of null for each colums in data set
```




    Car       0
    Rating    2
    dtype: int64




```python
custom.isnull().sum().max() # gives the max number of null values
```




    2




```python

```
