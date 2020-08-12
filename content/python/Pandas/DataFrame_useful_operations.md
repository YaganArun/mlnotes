---
title: "Useful operations on a DataFrame"
author: "Yagan Arun"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
cars = [['Audi' , 10] , ['Apple' , None] , ['Lambhorghini',10] , ['Bens',9] , ['Samsung',None] , ['Google',None]]
df = pd.DataFrame(data = cars , columns = ['Cars' , 'Rating'])
```


```python
df
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
      <th>Cars</th>
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
    <tr>
      <th>5</th>
      <td>Google</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Operation 1 : finding columns in a dataframe
df.columns
```




    Index(['Cars', 'Rating'], dtype='object')




```python

```
