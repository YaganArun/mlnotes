---
title: "DataFrame apply using custom function"
author: "Yagan Arun"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
data = ['audi is awsome ' , 'Maruthi is best' , 'Benz sucks' , 'Lambhoghini mind blowing'] 
df = pd.DataFrame(data , columns=['feedback'])
```


```python
def custom_length(sent):
    return len(sent)
    
```


```python
df['feedback_chars'] = df['feedback'].apply(custom_length)  
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
      <th>feedback</th>
      <th>feedback_chars</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>audi is awsome</td>
      <td>15</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Maruthi is best</td>
      <td>15</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Benz sucks</td>
      <td>10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Lambhoghini mind blowing</td>
      <td>24</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc
```




    <pandas.core.indexing._iLocIndexer at 0x7fa381132d10>




```python

```
